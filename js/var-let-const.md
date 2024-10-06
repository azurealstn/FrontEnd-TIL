# var vs let vs const

변수를 선언할 때 사용하는 var, let, const 차이에 대해 알아보자.

## var

```javascript
console.log(age);
var age = 30;

// hoisting 후
var age;
console.log(age); // undefined
age = 30;
```

- var로 변수를 선언하면 변수 선언하기도 전에 값을 할당할 수 있다. 또한 출력도 가능하다.
- 그 이유는 `var hoisting` 떄문이다.
- hoisting이 일어나면 위 코드와 같이 실행된다.
- var는 scope를 철저히 무시한다.
- 따라서 var를 사용하지 말자.

| hoisting이란, 변수를 맨 위로 끌어올리는 것을 말한다.

## let

- var 대신 scope를 지키면서 변수를 먼저 선언해야하는 제약을 줄 수 있는 let을 사용해야 한다.

## const

- 그리고 let보다 자주 사용하는 const가 있는데 값을 변경할 수 없다.
- 다같이 프로그램을 개발할 때는 항상 제약이 있어야 하는데 값을 변경할 여지를 주면 의도치 않은 변경이 생길 수 있다. 따라서 왠만하면 const로 선언하자.
  - 마치 Java에서 Setter 사용을 지양하는 것과 비슷하다.
- 만약 값을 변경해야 한다면 전역변수가 아닌 지역변수를 선언하자.

| TDZ (Temporal Dead Zone)
| 그렇다면 let과 const는 호이스팅이 안일어날까?
| 답은 let과 const도 호이스팅이 일어난다. 그렇다면 어떻게 에러가 난걸까?
| let과 const도 var처럼 호이스팅이 일어나고, var로 선언하게 되면 메모리 공간이 미리 생성이 되는데 let과 const는 메모리 공간에 확보되지 않기 때문에 이러한 공간을 TDZ라고 한다. 따라서 메모리가 없기 때문에 선언되기도 전에 할당할 수도 출력할 수도 없는 것이다.
