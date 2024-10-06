# this

Java에서 this는 자기 자신을 뜻하는데 JavaScript도 마찬가지다. 하지만 JavaScript에서의 this는 함수 호출방식에 따라 this에 바인딩되는 값이 달라지는 희한한(?) 현상을 알아보자.

## 전역공간

```javascript
// 전역에서의 this -> window
console.log(this);
```

## 일반 함수 호출

```javascript
// 엄격모드 -> 일반 함수에서의 this -> undefined
// 엄격모드X -> 일반 함수에서의 this -> window
function funcA() {
  console.log(this);
}
funcA();
```

- this는 window 객체가 되는데, 콜백함수도 마찬가지로 window 객체가 된다.

## 메서드 호출

```javascript
const person = {
  name: "Mike",
  age: 30,
  sayHello: function () {
    console.log(this);
  },
};
person.sayHello();
```

- 메서드 호출시에의 this는 person 객체가 된다.

## 생성자 함수 호출

```javascript
function Person(name, age) {
  console.log(this);
  this.name = name;
  this.age = age;
}

const person = new Person("Mike", 30);
```

- 생성할 객체가 this가 된다.

## 화살표 함수 호출

```javascript
function Counter() {
  this.count = 0;
  setInterval(() => {
    this.count++;
    console.log(this.count);
  }, 2000);
}
const counter = new Counter();
```

- 화살표 함수 호출시 this는 함수가 어디에 선언되었는가를 확인하고, 함수 내부에 선언된 상위 스코프를 바라본다.
