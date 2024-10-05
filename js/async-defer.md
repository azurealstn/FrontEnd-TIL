# script 불러오기

script를 불러오는 방법은 여러가지가 있다.

## 1. head에 포함

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <script src="main.js"></script>
  </head>
  <body></body>
</html>
```

- 스크립트는 위에서는 실행되기 때문에 body DOM을 생성하기도 전에 script를 실행해버리면 DOM 요소를 가져올 때 에러가 발생한다.
- 또한 script가 많다가 리소스를 많이 잡아먹기 때문에 HTML을 띄우는데 오래걸린다.

## 2. body 끝에 포함

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <!-- ... -->
    <script src="main.js"></script>
  </body>
</html>
```

- 사용자가 HTML을 먼저 볼 수 있다는 장점이 있지만 script 리소스가 크고 script에 매우 의존적이라면 역시나 많이 기달려야 한다.

## 3. async

```html
<script src="main.js" async></script>
```

- async는 HTML DOM을 생성과 동시에 script 리소스를 다운로드 받는다. 그런데 script 리소스 준비가 되면 HTML DOM 생성을 멈추고 script 먼저 실행되기 때문에 역시나 head에 포함한 것처럼 DOM 요소를 제대로 못가져올 수 있다.
- 또한 script를 불러오는데 순서에 의존적이라면 async는 사용하면 안된다.

## 4. defer

```html
<script src="main.js" defer></script>
```

- defer은 HTML DOM을 생성과 동시에 script 리소스를 다운로드 받는다. 그런 다음에 HTML DOM을 모두 생성한 다음에서야 script 리소스를 실행하기 때문에 문제가 없다.
- defer은 script를 불러오는데 순서대로 불러오기 때문에 상관없다.
