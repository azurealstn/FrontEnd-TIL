# 브라우저 높이를 활용하는 방법

웹사이트를 만들 때 특정 요소를 브라우저 높이에 따라 보여주고 안보여주고 싶을 떄는 중요한 것이 결국 브라우저 높이를 구하는 것이 관건이다. (혹은 스크롤 될 때마다 브라우저 높이를 구할 수도 있다.) 어떻게 구하는지 알아보자.

## 요소의 높이 구하는 법

```javascript
const element = document.querySelector(".element");
const elementHeight = element.getBoundingClientRect().height;
```

- `Element.getBoundingClientRect()` 메서드는 요소의 크기나 위치 정보를 제공하는 `DOMRect` 객체를 반환한다.
- 다른 방법으로는 `element.offsetHeight` 속성을 사용하면 높이를 가져올 수 있다. (단, 정수 반환)

## 스크롤될 때 브라우저 높이 구하는 법

```javascript
document.addEventListener("scroll", () => {
  console.log(scrollY);
});
```

- 스크롤될 때마다 처음 Y좌표인 0에서 떨어진만큼의 높이가 측정된다.
