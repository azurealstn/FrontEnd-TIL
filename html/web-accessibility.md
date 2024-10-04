# 웹 접근성

```html
<a class="home" href="#home" title="go to home">
  <i class="fa-solid fa-arrow-up"></i>
</a>
```

- 위 코드와 같이 a 태그안에 의미없는 태그가 있을 때는 웹접근성을 고려하는 것이 좋다.
- 그래서 스크린 리더가 읽을만한 의미있는 문구를 만들어주기 위해 a 태그에 title 속성을 써준다.

```html
<button class="toggle" aria-label="menu toggle">
  <i class="fa-solid fa-bars"></i>
</button>
```

- a 태그와 마찬가지로 button 태그안에 의미없는 태그가 있기 때문에 웹접근성을 역시 고려하는 것이 좋다.
- button에는 aria-label 속성을 사용해주면 된다.
