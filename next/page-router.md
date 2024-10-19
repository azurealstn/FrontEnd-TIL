# 페이지 라우터 (Page Router)

페이지 라우터(Page Router)는 React Router처럼 페이지 라우팅 기능을 제공한다. `pages` 폴더의 구조를 기반으로 페이지 라우팅이 제공된다.

## Pages 폴더

pages 폴더에는 페이지 라우팅할 파일을 관리한다.

#### \_app.tsx

pages 폴더에 있는 \_app.tsx 파일은 리액트의 `app.tsx`와 동일한 역할을 한다. 즉, 루프 컴포넌트로써 역할을 수행한다. (모든 페이지 컴포넌트들의 부모 컴포넌트)

- Component: 페이지 역할을 하는 컴포넌트
- pageProps: Component에 전달될 Props 객체

#### \_document.tsx

pages 폴더에 있는 \_document.tsx 파일은 모든 페이지에 공통적으로 적용되어야 하는 HTML 코드를 설정하는 컴포넌트이다. 기존의 리액트에서 `index.html`과 동일한 역할을 수행한다.

## query string

쿼리 스트링 값은 `useRouter`라는 훅을 사용하여 가져올 수 있다.

```javascript
import { useRouter } from "next/router";

export default function Page() {
  const router = useRouter();
  const { q } = router.query;
  return <h1>Search {q}</h1>;
}
```

## path variable

![page-router1](./images/page-router1.png)

위 그림과 같이 파일을 `[id].tsx`로 만들면 `[id]`에 경로 값이 렌더링된다.

```javascript
import { useRouter } from "next/router";

export default function Page() {
  const router = useRouter();
  const { id } = router.query;

  return <h1>Book {id}</h1>;
}
```
