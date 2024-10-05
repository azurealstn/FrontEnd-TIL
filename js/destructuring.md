# 구조분해할당

## Object

```javascript
const person = {
  name: "Mike",
  age: 30,
};

const name = person.name;
const age = person.age;
```

- 변수에 할당하려면 `const name = person.name;` 처럼 각각 할당해주어야 했다.

```javascript
const person = {
  name: "Mike",
  age: 30,
};

const { name, age } = person;
```

- 하지만 한 줄로 name과 age 변수를 모두 받을 수 있다.

## Array

```javascript
const array = [1, 2, 3];
const [a, b, c] = array;
```

- 참고로 배열도 구조분해할당으로 받을 수 있다.
