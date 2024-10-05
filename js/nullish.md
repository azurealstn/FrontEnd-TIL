# Nullish Coalescing Operator

```javascript
const num = 0;
const print = num || "zero";
console.log(print);
```

- 위 코드에서 num이 0이 출력되길 기대했지만 문자가 출력됐다.

```javascript
const num1 = 0;
const print1 = num1 ?? "zero";
console.log(print1); // 0

const num2 = null;
const print2 = num2 ?? "zero";
console.log(print2); // zero
```

- 그래서 위와같이 `??` 연산자를 사용하면 값이 있을 경우에만 출력하게 된다.
- null이나 undefined의 경우에는 zero가 출력된다.
