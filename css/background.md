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
