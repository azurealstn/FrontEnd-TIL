# API Routes

API Routes란 Next.js 앱에서 API를 구축할 수 있도록 만들어주는 기능이다. 그래서 이 기능을 이용하면 마치 백엔드 API 서버가 하는 일과 동일하게 간단한 API를 구축해서 클라이언트로부터 요청을 받아 데이터베이스에서 데이터를 꺼내온다거나 또 다른 서드파티에 데이터를 불러와서 전달을 한다거나 이러한 일련의 동작들을 만들 수 있다.

## API

`/src/pages/api` 경로에 API가 관리된다. 해당 경로에 api 파일들을 만들면 api routes로써 사용된다.

> 하지만 자주 사용되는 기능은 아니다..
