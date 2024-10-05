# Immutable Data Types vs Mutable Data Types

- Immutable Data Types: primitive types, frozen objects
  - Immutable Data Type은 값을 변경할 수 없는 타입을 말한다.

```javascript
let name = "Mike";
name = "Hello";
```

위 코드에서 String 타입인 변수 name값을 변경했는데 이 때 메모리에 할당할 때 기존 메모리에 있는 값을 바꾸는 것이 아닌 새로운 메모리에 값을 넣는다. 즉 불변성을 유지할 수 있게 된다.

- Mutable Data Type: all objects
  - 반면에 Mutable Data Type은 값을 변경할 수 있는데 Object로 선언된 내부 property 값들을 변경할 수 있다.
  - 다만, Object 자체 즉 주소값은 변경할 수 없다는 점을 알아두자.
