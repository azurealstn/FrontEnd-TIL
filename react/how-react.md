# React App 구동원리

리액트를 실행시키면 `http:localhost:5173`으로 접속할 수 있게되는데 어떻게 접속할 수가 있을까?

## 웹서버

Vite 도구를 통해 생성한 React App에는 웹서버가 내장되어 있다. `npm run dev`를 명령어를 실행시키면 내장되어 있던 웹서버를 가동시킨 것이다.

그래서 서버를 실행시키면 `main.jsx` 파일에서 createRoot 함수의 인수로 root 요소를 가져와서 App 컴포넌트를 렌더링하여 화면이 보여지게 된다.
