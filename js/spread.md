# Spread 연산자

Spread 연산자를 사용하면 배열을 쉽게 복사할 수 있다.

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
