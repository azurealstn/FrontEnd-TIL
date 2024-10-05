# Observer API

| 사실 이런 글보다는 공식문서를 보는 것이 제일 정확하다. 이 글을 작성하는 이유는 내가 공부하기 위해서이니 참고만 하자.

Intersection Observer API는 상위 요소 또는 최상위 문서의 viewport와 대상 요소 사이의 변화를 비동기적으로 관찰할 수 있는 수단을 제공한다.

## Observer 옵션 및 생성

```javascript
const options = {
  rootMargin: "10px",
  threshold: 0.25,
};
const observer = new IntersectionObserver(callback, options);
```

옵션을 통해 좀 더 세밀한 관찰이 가능하다.

- `threshold`: observer의 콜백이 무조건 실행되어야 하는 대상의 가시성 백분율을 나타낸다. [0, 0.25, 0.5, 0.75, 1] 처럼 배열로 여러개 지정할 수도 있고 기본값은 0이다. (1은 100% 완전히 보여질 때이다.) 또한 배열로 여러개 지정할 수도 있다.
- `rootMargin`: observer는 rootMargin을 지정한 여백까지 포함해서 관찰한다.

## Observer 콜백

```javascript
let callback = (entries, observer) => {
  entries.forEach((entry) => {
    // 각 엔트리는 관찰된 하나의 교차 변화을 설명합니다.
    // 대상 요소:
    //   entry.boundingClientRect
    //   entry.intersectionRatio
    //   entry.intersectionRect
    //   entry.isIntersecting
    //   entry.rootBounds
    //   entry.target
    //   entry.time
  });
};
```

콜백함수에서는 entry 파라미터를 가지고 다양한 기능을 활용할 수 있다.

- `entry.boundingClientRect`: 요소의 좌표나 크기 등의 수치를 알 수 있다.
- `entry.intersectionRatio`: target 요소가 관찰자에 의해 얼마만큼 들어왔는지 백분율 (1은 완전히 들어온 것이다.)
- `entry.intersectionRect`: target이 얼마만큼 들어왔는지 정보
- `entry.isIntersecting`: 관찰 대상에 들어왔는지(true) 빠져나갔는지(false)
- `entry.rootBounds`: 부모 요소에 대한 Bounds 정보
- `entry.target`: target 요소
- `entry.time`: 관찰 변화가 일어났을 때 시간
