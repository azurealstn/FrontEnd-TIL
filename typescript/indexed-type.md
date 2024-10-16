# 인덱스드 엑세스 타입

객체, 배열, 튜플 타입에서 특정 프로퍼티 혹은 요소의 타입을 추출하는 타입을 말한다.

```javascript
interface Post {
  title: string;
  content: string;
  author: {
    id: number,
    name: string,
    age: number,
  };
}

function printAuthorInfo(author: { id: number, name: string, age: number }) {
  console.log(`${author.name} - ${author.id}`);
}
```

`printAuthorInfo` 함수에서 `author` 파라미터의 타입을 정의하려면 어떻게 해야할까? 위 코드처럼 일일이 객체 안에 프로퍼티들을 정의하면 불편하다. 그래서 타입스크립트는 인덱스드 엑세스 타입을 지원한다.

```javascript
interface Post {
  title: string;
  content: string;
  author: {
    id: number,
    name: string,
    age: number,
  };
}

function printAuthorInfo(author: Post["author"]) {
  console.log(`${author.name} - ${author.id}`);
}
```

`Post["author"]` 처럼 사용하면 일일이 프로퍼티를 적지 않아도 된다. 여기서 인덱스를 `[]` 안에 있는 string literal 타입을 인덱스라고 한다. (주의할 점은 `"author"` 타입을 변수에 담아서 넘기면 안된다.)
