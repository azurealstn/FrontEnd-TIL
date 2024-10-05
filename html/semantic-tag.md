# 시맨틱 태그

시맨틱 태그는 의미있는 태그로, HTML5부터 생겼으며, 사용하는 것을 권장한다.

![semantic](./images/semantic.png)

- 위 사진처럼 웹사이트의 전체적인 구조를 시맨틱 태그를 사용하여 의미있게 구성하는 것이 중요하다.

## 시맨틱 태그의 장점

- SEO (Seach Engine Optimization)
- 웹 접근성 (Web Accessibility)
- 유지보수성

## article vs section

| article

- article은 페이지를 독립적으로 보여줬을 때 문제가 없다면 사용한다. 즉, main 안에 있는 내용들과 상관없이 독립적으로 고유한 정보를 나타낼 때 사용한다.

| section

- sectino은 독립적으로 보여주는 article과는 달리 "연관 있는 정보들"을 보여줄 때 사용한다.

## i vs em

둘 다 기울기의 효과를 준다. 다만 em 태그가 좀 더 강조하고 싶을 때 사용한다. i 태그는 그냥 시각적으로 보여준다.

## b vs strong

strong 태그가 좀 더 강조하고 싶을 때 사용한다. b 태그는 그냥 시각적으로 보여준다.

## ol vs ul vs dl

- ol: 순서가 중요할 때
- ul: 순서가 없는 경우 (단순 목록화)
- ul: 단어의 정의와 설명 목록

## img 태그 vs background-image(CSS)

- img 태그: 문서의 이미지가 중요할 때
- background-image(CSS): 이미지가 스타일링 목적인 경우

## button vs a

- button: 사용자의 특정한 액션이 필요한 경우 (ex. Login..)
- a: 어디론가 이동할 경우 (ex. 페이지 이동)

## table vs css

- table: 데이터가 정말 중요해서 행과 열로 표현해야 할 때
- CSS: 요즘은 Flex나 Grid 활용
