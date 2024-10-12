# 대수 타입

대수 타입은 여러 개의 타입을 합성해서 새롭게 만들어낸 타입이다. (이전에 기본 타입에서 잠깐 알아보았다.) 또한 대수 타입은 합집합과 교집합 타입이 존재한다.

## 합집합 - Union 타입

```javascript
// Union 타입
// 변수
let a: string | number | boolean;
a = 1;
a = "Hello";
a = true;

// 배열
let arr: (number | string | boolean)[] = [1, "Hello", true];

// 객체
type Person = {
  name: string,
  age: number,
};

type Hobby = {
  name: string,
  desc: string,
};

type Union1 = Person | Hobby;

let union1: Union1 = {
  name: "Mike",
  age: 30,
  desc: "게임하기",
};
```

## 교집합 - Intersection 타입

```javascript
// 교집합 - Intersection 타입
let variable: number & string; // never 타입

// 객체
type Person = {
  name: string,
  age: number,
};

type Hobby = {
  name: string,
  desc: string,
};

type Intersection = Person & Hobby;
let intersection1: Intersection = {
  name: "Mike",
  age: 30,
  desc: "게임하기",
};
```
