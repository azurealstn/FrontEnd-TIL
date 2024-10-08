# Node.js란?

Node.js란 Chrome V8 JavaScript 엔진으로 빌드된 JavaScript 실행 환경 즉, Runtime 환경이다. React 역시 Node.js를 기반으로 돌아가는 라이브러리이다.

```javascript
npm init
```

- 새로운 패키지를 생성한다.

| package.json

패키지를 생성하면 package.json 파일이 생긴다. script나 라이센스, 어떤 의존성들이 있는지 확인할 수 있다. 만약 의존성 라이브러리를 추가한다면 dependencies에 추가된다.

| node_moudles

실제 라이브러리를 설치하게 되면 라이브러리의 코드들을 관리하는 폴더라고 생각하면 된다.

| package-lock.json

- `package.json` 파일보다 더 정확하게 라이브러리들의 버전 등을 포함해서 관리한다.
