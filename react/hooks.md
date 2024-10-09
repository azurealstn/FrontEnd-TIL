# React Hooks

React Hook은 클래스 컴포넌트의 기능들을 함수 컴포넌트에서도 사용할 있게 만든 메서드들을 말한다.

useRef와 useState와 같은 메서드도 모두 React Hook이고, `use`라는 접두사가 붙이는 특징이 있으며, 사용자가 직접 Hooks를 만들 수 있도록 커스텀 훅이 가능하다.

React Hook은 반드시 컴포넌트 내부에서만 사용해야 한다. 그래야 React가 훅인지 판별할 수 있다.

React Hook은 조건문이나 반복문에서 선언할 수 없다.

React Hook은 나만의 훅인 커스텀 훅을 만들 수 있다. 커스텀 훅을 만드는 방법은 함수 앞에 use 라는 키워드를 붙이면 React가 알아서 커스텀 훅을 인지한다. 이러한 커스텀 훅은 별도의 hooks라는 폴더에서 관리한다.