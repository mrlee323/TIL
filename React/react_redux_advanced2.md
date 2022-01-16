# Redux Advanced(2)

## Ducks Pattern
리덕스를 사용할때 편리한 패턴 

```
src/redux
- create.js

src/redux/modules
- module1.js
- module2.js
...
- reducer.js(or index.js)
```
reudx폴더 안에 modules 폴더를 만들어 reducer와 action을 모아서 각각 파일을 만든다. 
filter파일안에는 filter의 리듀서와 action이 같이 있고, todos파일안에는 todos의 리듀서와 action을 같이 넣는 방법이다. 
파일을 만들때 규칙이 있다.

1. 액션을 선언할때 액션명 앞에 프로젝트명과 파일명을 넣어준다
  - ex) redux-start/users/GET_USERS_START
2. 리듀서의 함수명을 reducer로 한다.
  - 예전에는 각파일명과 reducer명이 같았는데 reducer 함수명 reducer로 바꿔준다.
3. 리듀서 함수를 export default로 지정한다 

이렇게 규칙안에서 정리를 하면 액션과 리듀서를 함께 관리할 수있다.
실제 실무에서도 많이 사용하는 패턴이라고 한다. 

ex) todos.js
```js
// 액션 타입 정의
export const ADD_TODO = "redux-start/todos/ADD_TODO" //액션 문자열
export const COMPLETE_TODO = "redux-start/todos/COMPLETE_TODO"

// 액션 생성 함수
// {type : ADD_TODO, text:'할일'}
export function addTodo(text) { //액션 생성함수
  return {
    type: ADD_TODO,
    text 
  }
}
// { type: COMPLETE_TODO, index: 3}
export function commpleteTodo(index) {
  return {
    type: COMPLETE_TODO,
    index
  }
}

// 초기값
const InitialState = []

//리듀서
export default function reducer(previousState = InitialState, action) {

  if(action.type === ADD_TODO){
    return  [...previousState, { text: action.text, done: false }]
  }

  if(action.type === COMPLETE_TODO){
    return previousState.map((todo, index)=>{
      if(index === action.index){
        return{...todo, done:true}
      } 
      return todo
    })
  }

  return previousState
}
```

## react-router-dom과 redux 함께 쓰기
```
npm i react-router-dom
```

```
npm i connected-react-router
```

## redux-saga

## redux-action

