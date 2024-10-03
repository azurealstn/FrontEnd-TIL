# BEM

BEM은 Block Element Modifier의 약자로 해당 세가지로 구성된 CSS 이름을 짓는 것을 말한다. 그리고 각각 `__`와 `--`로 구분한다.

```css
/* block__element--modifier */
.card__title;
.card__title--dark;
.card--dark;

.button;
```

- `card`라는 block 안에 element의 modifier을 정해줄 수 있다.
- 다만, 무조건적으로 `card`라는 block 안에 element .. 이런식으로 꼭 이름지을 필요없이 공통으로 사용하는 버튼이라면 그냥 `.button`을 사용한다.
- 또한 `card`라는 block 상위에 또다른 컨테이너인 `cards`가 있다해도 `cards__card__title` 처럼 복잡하게 사용할 필요없이 그냥 `card__title`로 사용한다.
