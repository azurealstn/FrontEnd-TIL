# 함수

JavaScript에서 함수는 `first-class-function`이다. 즉, 함수를 변수에 할당할수도 있고, 파라미터를 값을 넘길 수 있다. (처음 JavaScript 배울 때 여기서 충격 받았던 기억이..)

## 함수 선언식

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

## 생성자 함수

생성자 함수(Constructor Function)는 일반적인 함수와 기술적인 차이가 없다. 다만 사용하는 키워드가 있다.

```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
}

const person = new Person("Mike", 30);
console.log(person);
```

- 첫번째로 함수의 이름에 첫문자는 대문자이다.
- 객체를 생성할 때는 `new` 키워드를 사용한다.
- 생성자 함수를 사용하면 중복 코드를 줄일 수 있다는 장점이 있다.
