# 조건부 타입

조건부 타입은 어떠한 조건에 따라서 타입이 결정되는 타입을 말한다.

```javascript
type A = number extends string ? string : number;
```

number 타입이 string 타입의 하위타입이면 string 타입을 아니면 number 타입을 사용한다. 이러한 조건부 타입은 보통 제네릭과 같이 사용한다.

```javascript
type StringNumberSwitch<T> = T extends number ? string : number;

let varA: StringNumberSwitch<number> // string
let varB: StringNumberSwitch<string> // number
```

위의 조건부 타입은 T 타입에 따라서 타입이 결정된다.

## infer

infer는 조건부 타입에서 미리 정의되지 않은 타입을 유연하게 정의할 수 있게 도와주는 문법이다. 즉, 조건부 타입 내에서 타입을 추론할 수 있다.

```javascript
type FuncA = () => string;
type FuncB = () => number;

type ReturnType<T> = T extends () => infer R ? R : never;

type A = ReturnType<FuncA>; // string
type B = ReturnType<FuncB>; // number
```

infer R 문법을 사용하면 조건식이 참이 되도록 추론한다. 그래서 FuncA는 string, FuncB는 number 타입으로 추론하게 된다.
