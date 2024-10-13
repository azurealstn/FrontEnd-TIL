# 제네릭

제네릭이란 데이터 타입을 일반화하는 것으로, 클래스나 메서드에서 사용할 데이터의 타입을 컴파일할 때 지정하는 방식이다. 이는 클래스 내부에서 지정하는 것이 아닌 외부 사용자에 의해 지정되는 것을 뜻한다. 즉, 제네릭을 사용하면 컴파일 시에 미리 타입이 지정된다.

## 타입변수

```javascript
// 제네릭 함수
function func<T>(value: T): T {
  return value;
}

let num = func(10);
```

- 타입 변수는 사용자가 외부에서 지정할 수 있도록 `T`로 지정하면 나중에 타입을 추론한다.

## 확장하는 타입

```javascript
function getLength<T extends { length: number }>(data: T) {
  return data.length;
}

let var1 = getLength("123");
let var2 = getLength([1, 2, 3]);
let var3 = getLength({ length: 10 });
```

- 제네릭에 `extends` 키워드로 확장하면 `length` 프로퍼티는 반드시 가지고 있어야 한다는 의미이다.
- string과 배열은 length를 가지고 있으니 에러가 발생하지 않는다.
- 즉, 확장하는 타입은 해당 프로퍼티를 반드시 가지고 있어야 한다는 제약이 있다.

## 제네릭 인터페이스

```javascript
interface KeyPair<K, V> {
  key: K;
  value: V;
}

let keyPair: KeyPair<string, number> = {
  key: "Key",
  value: 0,
};
```

- Key와 Value를 저장하는 KeyPair 인터페이스를 정의하였고, 타입 변수 K와 V를 사용하였다.
- 구현부에서는 타입 변수에 K와 V의 타입을 제대로 명시해주어야 한다.

## 인덱스 시그니처 활용

```javascript
interface Map<V> {
  [key: string]: V;
}

let stringMap: Map<string> = {
  key: "value",
};
```
