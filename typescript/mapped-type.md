# 맵드 타입

기존의 객체 타입으로부터 새로운 객체 타입을 만드는 타입이다.

```javascript
interface User {
  id: number;
  name: string;
  age: number;
}

type PartialUser = {
  [key in "id" | "name" | "age"]: User[key];
};

type BooleanUser = {
  [key in keyof User]: boolean;
};

type ReadonlyUser = {
  readonly [key in keyof User]: User[key];
};

function fetchUser(): ReadonlyUser {
  // ... 가져오는 기능
  return {
    id: 1,
    name: "Mike",
    age: 29,
  };
}

function updateUser(user: User) {
  // ... 수정하는 기능
}
```

`PartialUser` 타입별칭을 보면 프로퍼티가 왼쪽에는 Key가 되고, 오른쪽에는 Value가 된다. 이러한 자료구조 형태를 Map처럼 생겨서 맵드타입이라 한다. 이런식으로 타입을 Map 형태로 사용자가 직접 정의할 수 있다.
