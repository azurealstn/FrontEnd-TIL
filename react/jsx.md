# JSX

JSX는 JavaScript Extensions의 약자로 확장된 자바스크립트의 문법을 말한다. 해당 문법은 JavaScript와 HTML을 혼합하여 사용할 수 있다.

```javascript
const Main = () => {
  return <div>Main Component</div>;
};
```

- 위 코드는 JSX를 사용한 문법으로 return 할 때 렌더링될 HTML을 쓰면 된다.
- 이 문법을 사용하지 않고 순수 JavaScript로만 한다면 createElement와 같은 함수를 사용하여 코드가 굉장히 길어질 수 있다.
- 닫는 태그가 꼭 있어야 한다.
- 최상위 태그는 반드시 하나여야 한다.
