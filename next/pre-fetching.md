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
