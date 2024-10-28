# Redux Action

Redux Action은 Redux State에 변화를 주기 위한 행동을 말한다. Redux Action은 JavaScript의 객체 형태로 type이라는 프로퍼티를 사용하고 있다.

## Action Creator

Action 객체를 생성하는 역할을 하는 JavaScript의 함수이다.

## redux-actions

FSA (Flux Standard Action)는 사람에게 친화적인 Flux Action 객체 표준이다.

redux-actions 라이브러리는 Redux를 위한 Flux Standard Action 도구이다. redux-actions를 사용하면 Redux에서 쉽게 FSA를 적용할 수 있다.

#### createActions

Action Creator를 생성하는 함수

#### handleActions

Action에 대한 Reducer를 생성하는 함수

#### combineActions

Action Type 또는 Action Creator들을 하나로 합쳐주는 함수
