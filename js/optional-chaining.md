# Optional Chaining

```javascript
const person = {
  name: "Mike",
  age: 30,
};
// console.log(person.hobby.title); // error!

console.log(person?.name); // Mike
console.log(person?.age); // 30
console.log(person?.hobby?.title); // undefined!
```

Optional Chaining을 사용하면 손쉽게 Null 처리가 가능하다. (Kotlin 같은 언어도 Null 처리를 쉽게 할 수 있다.)
