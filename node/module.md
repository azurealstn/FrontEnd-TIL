# 모듈시스템

| 모듈이란?

만약 쇼핑몰 사이트의 회원관리 기능, 장바구니 기능, 결제 기능 등 모든 기능들을 하나의 JS 파일에 작성하게 되면 유지보수나 성능이 많이 떨어질 것이다. 그래서 각 기능별로 파일로 관리하는 것이 일반적이다. 여기서 모듈은 각 기능별로 분리된 파일을 말한다.

그래서 모듈시스템이란 이러한 모듈들을 다루는 다양한 기능을 제공하는 시스템이다.

## 종류

JavaScript에는 다양한 모듈시스템을 제공한다.

- Common JS (CJS)
- ES Module (ESM)
- AMD
- UMD
- ..

위에서 대표적으로 CJS와 ESM이 사용된다.

## Common JS (CJS)

```javascript
export { add, sub };

module.exports = {
  add,
  sub,
};
```

- add와 sub 함수를 다른 파일에서 사용할 수 있도록 모듈화한다.

```javascript
const { add, sub } = require("./math.js");
```

- 실제 사용은 `require` 함수를 사용하여 불러올 수 있다.

## ES Module (ESM)

다음은 ES Module을 사용하기 위해 `package.json` 파일에 아래처럼 설정해주어야 한다. 또한 ES Module과 Common JS (CJS)를 함께 사용할 수 없다.

```json
"type": "module", // 설정
"dependencies": {
  ...
}
```

| 내보내기

```javascript
export function add(a, b) {
  return a + b;
}

export function sub(a, b) {
  return a - b;
}

export default function multiply(a, b) {
  return a * b;
}
```

- `export` 키워드를 사용한다.
- 또한 `export default` 키워드를 사용하여 해당 모듈(파일)의 대표 함수로써 딱 하나만 있다.

| 불러오기

```javascript
import { add, sub } from "./math.js";
import multiply from "./math.js";
```

- `import` 키워드를 사용한다.
- `export default`로 선언된 함수는 `{}` 없이 바로 불러올 수 있다.

ES Module 시스템이 확실히 직관적이고, 사용하기 편하다는 장점이 있다.
