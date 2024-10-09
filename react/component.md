# React 컴포넌트

react의 중요한 특징 중 하나인 컴포넌트는 재활용하여 사용할 수 있다.

```javascript
const HookExam = () => {
  return <div>hookexam</div>;
};

export default HookExam;
```

- 컴포넌트 이름은 반드시 첫글자를 대문자로 적어주어야 React가 컴포넌트라는 것을 인지할 수 있다.

```javascript
import HookExam from "./components/HookExam";

function App() {
  return (
    <>
      <HookExam />
    </>
  );
}
```

- 실제 사용할 때는 컴포넌트를 import하여 가져와서 `<HookExam />`와 같이 렌더링할 수 있다.
