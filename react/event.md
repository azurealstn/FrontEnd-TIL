# 이벤트 처리

사용자가 버튼을 클릭하거나 입력창에 입력한다거나 어떠한 이벤트가 발생했을 때 그것들을 처리하는 것을 말한다.

```javascript
const Button = ({ text }) => {
  return (
    <button
      onClick={(event) => {
        console.log(text);
      }}
    ></button>
  );
};

export default Button;
```

- onClick 속성을 사용하여 함수를 전달하면 된다. (함수 호출이 아닌 함수 자체를 전달해야 된다.)
- 또한 바닐라 자바스크립트에서 사용헀던 것처럼 이벤트가 발생했을 때 파라미터로 이벤트 객체(event)를 받을 수 있다.
- 참고로 각 브라우저마다 이 event 객체를 사용하는 방식이 조금씩 다른데 리액트는 합성 이벤트 객체를 사용하여 각기 다른 브라우저 규격을 포맷팅해준다.
