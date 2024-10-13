# 함수 타입

함수 타입을 사용하는 여러가지 방법을 알아보자

```javascript
// 함수 타입 정의
function func(a: number, b: number): number {
  return a + b;
}

// 화살표 함수
const add = (a: number, b: number): number => a + b;
```

### rest 파라미터

```javascript
function getSum(...rest: number[]): number {
  let sum: number = 0;
  rest.forEach((it) => (sum += it));
  return sum;
}

getSum(1, 2, 3);
```

- 물론 타입을 쓰지 않아도 타입을 추론하여 생략할 수 있다.

## 함수 타입 표현식

함수 별칭을 이용해서 만든 것을 함수 타입 표현식이라 한다.

```javascript
// 함수 별칭 -> 함수 타입 표현식
type Add = (a: number, b: number) => number;
const add: Add = (a, b) => a + b;
```

## 호출 시그니처

```javascript
// 호출 시그니처 (콜 시그니처)
type Operation = {
  (a: number, b: number): number,
};
const add2: Operation = (a, b) => a + b;
```

- 호출 시그니처를 사용해도 앞서 함수 타입 표현식을 정의한 것과 같이 사용할 수 있다.

## 함수 오버로딩

함수 오버로딩은 함수를 매개변수의 개수나 타입에 따라 여러가지 버전으로 정의하는 방법을 말한다.

```javascript
// 함수 오버로딩
// 버전들 -> 오버로드 시그니처
function add(a: number, b:number): number;
function add(a: number, b: number, c: number): number;

// 실제 구현부 -> 구현 시그니처
function add(a: number, b:number): number {
  return a + b;
}

const result1 = add(1, 2);
const result2 = add(1, 2, 3);
```

- 가장 먼저 오버로드 시그니처를 만들고, 구현부인 구현 시그니처를 구현해야 한다.
