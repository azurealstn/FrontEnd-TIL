# TypeScript 설치 및 설정

TypeScript를 어떻게 설치하고 설정하는지 알아보자.

## 설치

```javascript
npm init // 패키지 초기화

npm i @types/node // node.js 내장 함수

npm i -g typescript // TypeScript 컴파일러

tsx src/index.ts // 실행
```

## 설정

```javascript
tsc --init // 설정 파일 생성
```

#### tsconfig.json

```json
{
  "compilerOptions": {
    "skipLibCheck": true,
    "target": "ESNext",
    "module": "ESNext",
    "outDir": "dist",
    "strict": true,
    "moduleDetection": "force"
  },
  "include": ["src"]
}
```

- skipLibCheck: 불필요한 타입 정의 파일의 타입 검사 생략
- include: 일일이 파일마다 컴파일 안해도 src 폴더 안에 있는 ts 파일들을 모두 컴파일 한다.
  - 실행: tsc 입력
- compilerOptions: 컴파일하는 JavaScript 버전을 설정할 수 있다.
  - ES5: ES5로 컴파일
  - ESNext: 최신버전
- module: 모듈시스템 설정
- outDir: 컴파일된 파일이 생성되는 폴더
- strict: 엄격한 타입 검사
- moduleDetection: TypeScript의 모든 파일은 전역 파일로 간주되어 변수가 공유된다. 그래서 독립된 파일로 만드려면 값을 "force"로 설정한다.
