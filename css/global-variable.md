# Global Variable 설정

CSS에서 변수를 선언할 수 있다는 것을 배웠다. 그렇다면 어떤식으로 사용하는지 또 CSS를 공통적으로 사용하는 부분은 어떤 것인지 Global 설정을 해보자.

```css
/* Global */
:root {
  /* App Colors */
  --color-primary: var(--color-black);
  --color-primary-variant: var(--color-gray);
  --color-accent: var(--color-blue);
  --color-accent-variant: var(--color-orange);
  --color-text: var(--color-white);

  /* Colors */
  --color-white: #ffffff;
  --color-black: #050a13;
  --color-blue: #03e8f9;
  --color-orange: #fd6413;
  --color-gray: #1b1e26;

  /* Size */
  --size-max-width: 1200px;
}

* {
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: "Open Sans", sans-serif;
  margin: 0;
}

h1,
h2,
h3,
p,
ul {
  margin: 0;
}

ul {
  list-style: none;
  padding: 0;
}

a {
  text-decoration: none;
  color: var(--color-text);
}

button {
  background-color: transparent;
  outline: 0;
  border: 0;
}

button:focus {
  outline: 1px solid var(--color-accent);
}
```

- Global 설정은 순수 CSS 사용할 때 유용하며, CSS 프레임워크를 사용한다면 Global 설정할 필요없다.
