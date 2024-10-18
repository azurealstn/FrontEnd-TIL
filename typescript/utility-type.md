# 유틸리티 타입

유틸리티 타입은 제네릭, 맵드 타입, 조건부 타입 등의 타입 조작 기능을 이용해 실무에서 자주 사용되는 타입을 미리 만들어 놓은 것이다.

## 맵드 타입 기반의 유틸리티 타입

#### Partial<T>

특정 객체 타입의 모든 프로퍼티를 선택적 프로퍼티로 바꿔주는 타입이다.

```javascript
interface Post {
  title: string
  content: string
  tags: string[]
}

const draft: Partial<Post> = {
  title: "제목",
  content: "내용"
}
```

Partial<T> 타입을 사용하면 Post 타입의 프로퍼티들을 모두 선택적 프로퍼티로 만들 수 있다.

#### Required<T>

Partial<T> 타입과는 반대로 특정 객체 타입의 모든 프로퍼티를 필수 프로퍼티로 바꿔주는 타입이다.

```javascript
interface Post {
  title: string;
  content: string;
  tags: string[];
}

const draft: Required<Post> = {
  title: "제목",
  content: "내용",
  tags: ["Hello", "Hi"],
};
```

Required<T> 타입을 사용하면 모든 프로퍼티를 사용하도록 해야한다.

#### Readonly<T>

Readonly<T> 타입은 특정 객체 타입에서 모든 프로퍼티를 읽기 전용 프로퍼티로 만들어주는 타입이다.

```javascript
interface Post {
  title: string;
  content: string;
  tags: string[];
}

const draft: Readonly<Post> = {
  title: "제목",
  content: "내용",
  tags: ["Hello", "Hi"],
};

// draft.content = "123" -> 수정 불가!
```

#### Pick<T, K>

Pick<T, K> 타입은 객체 타입으로부터 특정 프로퍼티만 딱 골라내는 타입이다.

```javascript
interface Post {
  title: string;
  content: string;
  tags: string[];
}

const legacyPost: Pick<Post, "title" | "content"> = {
  title: "제목",
  content: "내용",
};
```

`Pick<Post, 'title' | 'content'>` 처럼 사용하면 `title`과 `content` 프로퍼티만 사용할 수 있다.

#### Omit<T, K>

Omit<T, K> 타입은 객체 타입으로부터 특정 프로퍼티를 제거하는 타입이다.

```javascript
interface Post {
  title: string;
  content: string;
  tags: string[];
}

const noTitlePost: Omit<Post, "title"> = {
  content: "내용",
  tags: ["Hello", "Hi"],
};
```

`Omit<Post, "title">` 처럼 제거할 타입을 명시해주면 된다.

#### Record<K, V>

Record<K, V> 타입은 객체 타입을 만들어주는 유틸리티 타입으로 실무에서 굉장히 많이 사용한다.

```javascript
type ThumbnailLegacy = {
  large: {
    url: string,
  },
  medium: {
    url: string,
  },
  small: {
    url: string,
  },
};

type Thumbnail = Record<"large" | "medium" | "small", { url: string }>;
```

ThumbnailLegacy 타입처럼 프로퍼티를 정의하는 것은 반복적인 일이 된다. 따라서 Thumbnail 처럼 Recode 타입을 사용하면 프로퍼티를 쉽게 정의할 수 있다.

## 조건부 타입 기반의 유틸리티 타입

#### Exclude<T, U>

Exclude<T, U> 타입은 T에서 U를 제거하는 타입이다.

```javascript
type A = Exclude<string | boolean, boolean>;
```

`Exclude<string | boolean, boolean>` 타입은 string | boolean 타입에서 boolean 타입을 제거한 string 타입이 된다.

#### Extract<T, U>

Exclude<T, U>와는 반대로 T에서 U를 추출하는 타입이다.

```javascript
type A = Extract<string | boolean, boolean>;
```

이번에는 결과가 boolean 타입이 된다.

#### ReturnType

ReturnType은 함수의 반환값 타입을 추출하는 타입을 말한다.

```javascript
function funcA() {
  return "hello";
}

type ReturnA = ReturnType<typeof funcA>; // string
```

ReturnType을 사용하면 함수의 타입을 손쉽게 추출할 수 있다.
