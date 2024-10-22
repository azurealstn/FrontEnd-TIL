# 프리페칭

프리페칭(Pre-fetching)이란 현재 보고 있는 페이지에서 사용자가 링크들을 통해서 이동할 수 있는 현재 연결되어 있는 모든 페이지들을 사전에 불러와 놓는 기능이다. 즉, 현재 사용자가 보고 있는 페이지 내에서 이동할 가능성이 있는 모든 페이지들을 사전에 미리 다 불러놓는 기능이다. 이렇게 하는 이유는 빠른 페이지 이동을 위한 목적이 있다.

Next는 서버에서 JS 번들링 파일을 클라이언트로 전달하는데 이 때 요청한 페이지에 필요한 JS 번들링 파일만 전달한다. 그 이유는 한번에 모든 JS 번들 파일을 전달하면 용량이 너무 크기 떄문에 부하가 걸린다. 그래서 이번에는 빠른 페이지 이동을 위해 연결된 모든 페이지의 JS 번들 파일들을 사전에 불러오는 작업이 필요한 것이다. 이러면 SSR이지만 CSR처럼 빠르게 이동이 가능하다.

요청한 페이지에 Link 컴포넌트를 사용한 페이지들만 프리페칭이 진행되고, 프로그래매틱으로 링크를 설정한 경우에는 프리페칭이 안되는데 이 때는 useEffect를 사용할 수 있다.

```javascript
export default function App({ Component, pageProps }: AppProps) {
  const router = useRouter();

  const onClickButton = () => {
    router.push("/test");
  };

  useEffect(() => {
    router.prefetch("/test");
  }, []);
}
```

만약 프리페칭을 하고 싶지 않을 때는? prefetch 속성의 값을 false로 사용한다.

```javascript
<Link href={"/book/1"} prefetch={false}>
  book/1
</Link>
```

## SSR (서버 사이드 렌더링)

가장 기본적인 Next.js의 사전 렌더링 방식으로 요청이 들어올 때 마다 사전 렌더링을 진행한다. 단 SSR의 단점은 서버에서 데이터를 가져올 때 시간이 오래 걸리면 그만큼 사용자는 기달려야 한다.

```javascript
export const getServerSideProps = () => {
  const data = "hello";

  return {
    props: {
      data,
    },
  };
};
```

- getServerSideProps 함수의 역할은 컴포넌트보다 먼저 실행되어서 컴포넌트에 필요한 데이터를 불러오는 기능을 수행한다.
- 또한 getServerSideProps 함수는 서버에서 실행되기 때문에 브라우저의 내장된 객체인 `window` 같은 객체는 사용하지 못한다.

## SSG (정적 사이트 생성)

SSR의 단점을 해결하는 사전 렌더링 방식으로 빌드 타임에 페이지를 미리 사전렌더링을 해둔다. 이는 빌드할 때 미리 JS 번들 파일을 실행하여 렌더링될 HTML을 준비한다. 빌드할 때 미리 다 페칭해 놓기 때문에 실제 운영해서 보여줄 때는 속도가 빠를 수 밖에 없다. 즉, 사전 렌더링에 많은 시간이 소요되는 페이지더라도 사용자의 요청에는 매우 빠른 속도로 응답할 수 있다. 다만 빌드 타임에만 페이지를 응답하기 때문에 매번 똑같은 페이지만 응답한다. 즉, 최신 데이터 반영은 어렵다.

```javascript
export const getStaticProps = async () => {
  // const allBooks = await fetchBooks();
  // const recoBooks = await fetchRandomBooks();
  const [allBooks, recoBooks] = await Promise.all([
    fetchBooks(),
    fetchRandomBooks(),
  ]);

  return {
    props: {
      allBooks,
      recoBooks,
    },
  };
};
```

실제 사용할 때는 getStaticProps 함수를 내보내주면 된다. 역할은 SSR과 동일한다.

## ISR (증분 정적 재생성)

ISR은 Incremental Static Regeneration의 약자로, 단순히 SSG 방식으로 생성된 정적 페이지를 일정 시간을 주기로 다시 생성하는 기술을 말한다. SSG의 최신 데이터 반영은 어렵다는 단점을 해결하여 일정시간을 주기로 페이지를 다시 생성해주는 방식이다.

```javascript
export const getStaticProps = async () => {
  // const allBooks = await fetchBooks();
  // const recoBooks = await fetchRandomBooks();
  const [allBooks, recoBooks] = await Promise.all([
    fetchBooks(),
    fetchRandomBooks(),
  ]);

  return {
    props: {
      allBooks,
      recoBooks,
    },
    revalidate: 3,
  };
};
```

revalidate 속성만 추가해주면 된다. (초단위)

## On-Demand ISR

사용자의 요청이 왔을 때 페이즈를 재생성해야 한다면 ISR은 조금 부족할 수 있다. 그 이유는 요청이 왔지만 60초마다 실행되기 때문에 기다려야 하고, 요청이 오지 않았는데도 매번 60초마다 실행한다면 리소스 낭비가 되기 떄문이다. 그래서 이러한 해결을 위해 On-Demand ISR 방식이 생긴다.

On-Demand ISR은 주문형 재검증으로 요청을 받을 때마다 페이지를 다시 생성하는 기능을 제공한다. (트리거 역할)
