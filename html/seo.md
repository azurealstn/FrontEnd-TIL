# SEO

SEO는 Search Engine Optimization의 약자로, 검색 엔진 최적화란 뜻이다. 즉, 사용자가 구글 같은 사이트에서 검색했을 때 더 상세하게 정보를 제공해줄 수 있다. 또한 높은 순위를 갖게 되어 첫 페이지 상위에 바로 보여줄 수 있게 많은 트래픽을 유도하고 브랜드 인지도를 향상시키는데 가장 효과적인 방법이다.

따라서 SEO 작업은 굉장히 중요하며, 프론트 개발에서 절대 빠질 수 없는 작업이다. 하나씩 속성을 알아보자.

- `title`: 웹사이트의 제목
- `description`: 웹사이트의 설명
- `author`: 작성자
- `favicon`: favicon 설정

## OG

OG는 Open Graph Data의 약자로 페이스북(메타)에서 만든 것으로 웹사이트 링크를 카톡에 보낼 때 나오는 이미지를 나타낸다.

`og:title`: 제목
`og:type`: 링크의 종류
`og:url`: URL
`og:image`: 사용자에게 보여줄 이미지

## 코드보기

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <!-- SEO -->
    <title>It&#39;'s Portfolio</title>
    <meta name="description" content="공부를 위한 포트폴리오" />
    <meta name="author" content="Mike" />

    <!-- Favicon 설정 -->
    <link rel="shortcut icon" href="./images/favicon.ico" type="image/x-icon" />

    <!-- OG (Open Graph Data) -->
    <meta property="og:title" content="포트폴리오" />
    <meta property="og:type" content="website" />
    <meta property="og:url" content="배포후 생성된 URL" />
    <meta property="og:image" content="이미지 URL" />

    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300..800;1,300..800&display=swap"
      rel="stylesheet"
    />

    <!-- Font Awesome -->
    <script
      src="https://kit.fontawesome.com/32f48298df.js"
      crossorigin="anonymous"
    ></script>

    <!-- CSS -->
    <link rel="stylesheet" href="./css/style.css" />

    <!-- JavaScript -->
    <script src="./src/main.js" defer></script>
  </head>
  <body></body>
</html>
```
