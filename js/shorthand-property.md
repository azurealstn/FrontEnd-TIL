# 속성 단축

```javascript
const name = "Mike";
const age = 30;

const person = {
  name: name,
  age: age,
};
```

- key와 value가 동일한 경우 단축이 가능하다.

```javascript
const name = "Mike";
const age = 30;

const person = {
  name,
  age,
};
```
