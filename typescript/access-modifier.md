# 접근제어자

클래스를 만들 때 특정 필드나 메서드의 접근을 제어할 수 있다.

```javascript
class Student {
  // 필드
  public name: string;
  private grade: string;
  protected age: number;

  // 생성자
  constructor(name: string, grade: string, age: number) {
    this.name = name;
    this.grade = grade;
    this.age = age;
  }

  // 메서드
  study() {
    console.log(`my grade is ${this.grade}`);
  }
}

const studentA = new Student("Mike", "A+", 30);
```

## public

필드나 메서드에 접근제어자를 설정하지 않았다면 기본적으로 `public`으로 설정되어 모든 곳에서 접근할 수 있다.

## private

`private`으로 선언한 클래스 내부에서만 사용할 수 있다.

## protected

파생된 클래스 즉, 상속 받은 클래스에서도 사용하고 싶다면 `protected` 키워드를 사용할 수 있다.
