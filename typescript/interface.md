# 인터페이스

인터페이스는 타입에 이름을 지어주는 문법으로 상호간에 약속된 규칙이라 생각하면 된다. (자바에서 인터페이스는 다형성을 활용해 확장성 있는 설계가 가능했다.)

```javascript
interface Person {
  name: string
  age: number
}

const person: Person = {
  name: "Mike",
  age: 30
}
```

- 타입 별칭을 사용한 것처럼 사용하면 된다.

## 인터페이스 확장

- 인터페이스끼리는 `extedns` 키워드로 상속할 수 있으며, 부모의 프로퍼티들을 사용할 수 있다.
- 클래스에서 인터페이스를 상속받으려면 `implements` 키워드를 사용한다.
