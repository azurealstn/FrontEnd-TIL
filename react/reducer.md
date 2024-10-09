# useReducer

컴포넌트 내부에 새로운 State를 생성하는 리액트 훅이다. 따라서 모든 useState는 useReducer로 대체가 가능하다. 핵심은 상태관리코드를 컴포넌트 외부로 분리시킬 수 있다.

| useState

- 컴포넌트 내부에 상태관리 코드를 작성해야 했다.
- State가 너무 많아지면 유지보수하기 어려워지고 가독성이 떨어진다.
- 따라서 reducer라는 새로운 함수를 컴포넌트 외부에 만들어서 한번에 관리할 수 있도록 한다.
- `count`와 같은 간단한 상태값을 변경시킬 때 사용한다.

| useReducer

- 컴포넌트 외부에 상태관리 코드를 분리할 수 있다.
- CRUD와 같은 내부에 복잡한 구조로 되어있다면 useReducer를 사용하여 가독성을 높인다.

## 사용법

```javascript
import { act, useReducer } from "react";

function reducer(state, action) {
  if (action.type === "INCREASE") {
    return state + action.data;
  } else if (action.type === "DECREASE") {
    return state - action.data;
  }
}

const Exam = () => {
  const [state, dispatch] = useReducer(reducer, 0);

  const onClickPlus = () => {
    dispatch({
      type: "INCREASE",
      data: 1,
    });
  };

  const onClickMinus = () => {
    dispatch({
      type: "DECREASE",
      data: 1,
    });
  };

  return (
    <div>
      <h1>{state}</h1>
      <button onClick={onClickPlus}>+</button>
      <button onClick={onClickMinus}>-</button>
    </div>
  );
};

export default Exam;
```

### 자세히 보기

```javascript
const [state, dispatch] = useReducer(reducer, 0);
```

- dispatch: 상태변화가 있어야 한다는 사실을 알리는, 발송하는 함수
- useReducer의 두번째 인수인 `0`은 State의 초기값이다.

```javascript
function reducer(state, action) {}
```

- reducer(): 상태를 실제로 변화시키는 변환기 역할
- action: action 객체는 dispatch의 인수로 넘긴 type과 data가 있다.

```javascript
dispatch({
  type: "INCREASE",
  data: 1,
});
```

- 상태가 어떻게 변화되기를 기대하는지 인수로 넘겨주어야 한다.
- action 객체
  - type: 어떤 타입인지
  - data: 데이터 값
