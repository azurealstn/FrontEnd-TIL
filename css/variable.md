# CSS 변수

CSS에서도 변수를 사용할 수 있다. 변수를 사용하는 이유는 css 변경이 일어났을 때 일일이 다 고치는 것이 아니라 변수 하나만 고치면 모두 적용될 수 있도록 하기 위해서다.

```css
:root {
  --background-color: darkslategrey;
}
```

- 변수를 정의한다.
- 변수는 `--`로 시작해야 한다.

```css
background-color: var(--background-color);
```

- 실제 변수 사용
