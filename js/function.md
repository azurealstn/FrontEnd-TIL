# 함수

JavaScript에서 함수는 `first-class-function`이다. 즉, 함수를 변수에 할당할수도 있고, 파라미터를 값을 넘길 수 있다. (처음 JavaScript 배울 때 여기서 충격 받았던 기억이..)

## 일반적인 함수

```javascript
sayHello();

function sayHello() {
  console.log("HELLO!");
}
```

- function 키워드를 사용해 함수를 선언한다.
- 함수 역시 Hoisting이 된다.
- 참고로, function 키워드로 생성된 함수만 Hoisting이 된다는 것을 기억하자.

## 함수 표현식

```javascript
// hello(); 사용 불가
const hello = function () {
  // => 익명 함수
  console.log("HELLO!");
};
hello();
```

- 함수 표현식은 변수에 함수를 할당하는 것이다.
- const 변수이기 때문에 hoisting이 불가능하다.
- 함수에 이름이 없는 것을 익명함수라 한다.

## 화살표 함수

```javascript
// hello(); 사용 불가
const hello = () => console.log("HELLO!");
hello();
```

- 화살표 함수는 훨씬 더 간편하게 사용할 수 있다.
- 항상 익명함수이다.

## IIFE

IIFE(Immediately Invoked Function Expression)은 선언과 동시에 함수를 호출하는 것을 말한다.

```javascript
(function sayHello() {
  console.log("HELLO!");
})();
```
