# 타입 단언

타입 단언은 개발자가 해당 타입에 대해 확신이 있을 때 사용하는 타입 지정 방식이다. 타입 단언을 사용하면 타입스크립트를 컴파일 할 때 특별히 타입을 체크하지 않고, 데이터의 구조도 신경쓰지 않게 된다.

```javascript
type Person = {
  name: string;
  age: number;
};

let person = {} as Person;
person.name = "Mike";
person.age = 30;
```

타입 단언은 타입스크립트 컴파일러보다 개발자가 더 해당 타입을 잘 알고 있을 때 사용해야 한다. (즉, 조심해야 한다..)

## Non Null 단언

```javascript
type Post = {
  title: string;
  author?: string; // 선택적 프로퍼티
};

let post: Post = {
  title: "게시글",
  author: "Mike",
};

const len: number = post.author!.length;
```

- 코드 맨아래에 `post.author!.length` 처럼 `!` 기호를 쓰면 Option Chaining이라 undefined 값이 될 수도 있지만 무조건 Null이 아니라는 것을 명시한다는 의미의 기호이다.
