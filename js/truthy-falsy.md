# Truthy와 Falsy

JavaScript의 모든 값은 Truthy하거나 Falsy하다.

| Truthy 값

- Falsy 값을 제외한 모든 값

| Falsy 값

- undefined, null, 0, -0, NaN, "", 0n

## 단락평가

Truthy하거나 Falsy 값을 이용하여 다음 코드처럼 간략히 쓸 수 있다.

```javascript
const name = person && person.name;
console.log(name || "person의 값이 없음");
```
