# keyframes

애니메이션을 주고 싶을 때 사용한다.

```css
.box {
  width: 100px;
  height: 100px;
  margin: 20px;
  background-color: chocolate;
  animation: 3s infinite slidein;
}
@keyframes slidein {
  0% {
    border-radius: 0%;
    background-color: blue;
  }
  50% {
    background-color: lightblue;
  }
  100% {
    border-radius: 100%;
    background-color: white;
  }
}
```
