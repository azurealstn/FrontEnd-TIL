# 클래스

타입스크립트의 클래스는 자바스크립트의 클래스와 매우 비슷하다.

```javascript
class Student {
  // 필드
  name: string;
  grade: string;
  age: number;

  // 생성자
  constructor(name: string, grade: string, age: number) {
    this.name = name;
    this.grade = grade;
    this.age = age;
  }

  // 메서드
  study() {
    console.log("Study Hard!");
  }
}

const studentA = new Student("Mike", "A+", 30);
const studentB: Student = {
  name: "James",
  grade: "B+",
  age: 29,
  study: function () {
    console.log("My Work!");
  },
};
```

- `new` 키워드를 사용하여 클래스의 인스턴스 생성할 수 있다.
- `Student` 클래스를 타입으로도 사용할 수 있다.
