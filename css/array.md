# 정렬

정렬할 수 있는 여러가지 방법들을 알아보자.

| block 정렬

```css
margin: auto;
```

| inline 정렬

```css
text-align: center;
```

| text 정렬

```css
text-align: center;
height: 100%;
line-height: 100px;
```

- line-height: 부모 박스의 높이로 지정한다.
- 사실 이 방법보다는 flex box를 사용하면 좋다.

| translate 정렬

```css
postion: relative;
top: 50%;
left: 50%;
transform: translate(-50%, -50%);
```

| flex 정렬

```css
display: flex;
align-items: center;
justify-content: center;
```
