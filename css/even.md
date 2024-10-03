# 순서 바꾸기

일렬로된 요소 3개 중에서 가운데꺼만 오른쪽으로 만들기 위해서는 CSS로 수정이 가능하다.

```css
.box:nth-child(even) .box__img {
  order: 1;
}
```

- box:nth-child(even): even을 써주면 짝수만 찾는다.
- order: 0부터 시작한다.
