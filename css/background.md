# background

```css
.box1 {
  background-image: url("https://media.swncdn.com/cms/BST/67912-gettyimages-817147678-kieferpix.1200w.tn.webp");
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}
```

```css
.box2 {
  background: center/cover no-repeat
    url("https://media.swncdn.com/cms/BST/67912-gettyimages-817147678-kieferpix.1200w.tn.webp");
}
```

- `background-image`: 이미지 리소스를 가져온다.
- `background-repeat`: 이미지를 반복할 것인지 결정한다.
- `background-position`: 이미지를 어디에 정렬시킬 것인지 지정한다.
- `background-size`: 이미지 사이즈를 정한다.
  - `cover`: 사이즈가 반응형으로 조정된다. (많이 사용한다.)
  - `contain`: 원래 사이즈로 고정된다. 반응형이 아니라 많이 사용하진 않는다.

## object-fit

img 태그나 video 태그와 같은 대체 요소의 콘텐츠 크기를 어떤 방식으로 조절할 것인지 설정하는 속성이다.

```css
object-fit: cover;
```

- 이미지의 비율이 안맞을 때 사용한다.

## filter

background-color를 지정한 색깔로 설정하되, 다른 박스에서는 해당 박스보다는 조금 연한 색깔로 만들고 싶다면 filter를 사용하면 좋다.

```css
.box {
  padding: 1rem;
  background-color: var(--color-primary);
  filter: brightness(150%);
}
```

## button

보통 button은 기본 그대로 사용하지 않고 모든 스타일을 제거하고 새로 css를 작성한다. 그래서 default를 모두 제거하기 위한 css 작성을 해주어야 한다.

```css
button {
  background-color: transparent;
  outline: 0;
  border: 0;
}
```

- 또한 button 색상 등은 부모에서 상속되지 않는다는 점을 기억하자.
