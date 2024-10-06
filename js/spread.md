# Spread 연산자

Spread 연산자를 사용하면 배열을 쉽게 복사할 수 있다. spread 뜻 그대로 퍼트리는 것을 말한다. 즉, `...arr` 문법을 통해 퍼트리는 것이다.

## 배열

```javascript
const arr = [1, 2, 3, 4, 5];
const arrCopy = [...arr];
console.log("arr", arr);
console.log("arrCopy", arrCopy);
```

아래 코드처럼 값을 복사하는 것 동시에 추가할 수도 있다.

```javascript
const arrCopy2 = [...arr, 6, 7];
console.log(arrCopy2);
```

| 하지만 주의할 점은 Spread 연산자로 복사하게 되면 참조값만 복사되기 때문에 얕은 복사가 된다. (깊은복사 X)

## 객체

```javascript
const person = {
  name: "Mike",
  age: 30,
};
const personCopy = { ...person };
console.log(person);
console.log(personCopy);
```

- 객체도 Spread 연산자를 활용할 수 있다.

## Rest 연산자

나머지 매개변수라고도 불리는 rest 연산자는 spread와 반대로 값들을 묶어준다.

```javascript
const person = {
  name: "Mike",
  age: 30,
  hobby: "pc game",
};

// const { ...rest, name } = person; // Error!
const { name, ...rest } = person;
console.log(rest.name); // Mike
console.log(rest.age); // 30
console.log(rest.hobby); // pc game
```

- 구조분해할당에서 rest 문법을 사용하여 변수를 묶을 수 있다.
- 주의할 점은 rest 문법은 맨 마지막에 써주어야 한다는 점이다.

```javascript
const arr = [1, 2, 3, 4, 5];
const [a, b, ...rest] = arr;
console.log(a); // 1
console.log(b); // 2
console.log(rest); // [3, 4, 5] 배열
```

- 배열로 마찬가지이다.

| 정리하면 spread 연산자는 배열(혹은 객체)을 퍼트려서 인수로 전달할 때 사용하고, rest 연산자는 배열(혹은 객체)을 매개변수를 전달받을 때 사용한다.
