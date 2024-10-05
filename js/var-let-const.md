# var vs let vs const

변수를 선언할 때 사용하는 var, let, const 차이에 대해 알아보자.

## var

```javascript
name = "Mike";
var name;
```

- var로 변수를 선언하면 변수 선언하기도 전에 값을 할당할 수 있다.
- 그 이유는 `var hoisting` 떄문이다.
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
