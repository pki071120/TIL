# useReducer란
: 상태관리를 위한 훅.  
- useState와는 다른 상태관리가 가능.
- 컴포넌트의 상태 업데이트 로직을 컴포넌트에서 분리시킬 수 있음.

# 구성요소
``` jsx
const reducer = (state,action) => {

}
const initialState = {

}

function App(){
  const [state,dispatchFn] = useReducer(reducer, initialState);

  //~~~
}
```
- useReducer : `reducer 함수`와 초기값 `initialState`를 인자로 받음.  
- reducer : 상태가 바뀌는 곳, state와 action을 매겨변수로 받음
- initialState : `초기 상태를 저장`해놓은 것.  
- action : 상태의 `변화를 지정`. 
- state : 현재의 상태 저장. 
- dispatchFn : 컴포넌트 안에서 쓰임, reducer에서 특정 동작을 수행할 수 있도록 명령, 인자를 넘기는 역할.

## #예제 Counter
```jsx 
import React,{useReducer} from 'react';

const reducer = (state,action) => {
  if(action === 'plus'){
    return state+1;
  }
  else if(action === 'minus'){
    return state-1;
  }
}

export function App(props) {
  const [count, dispatch] = useReducer(reducer,0);

  const onPlus = () => {
    dispatch('plus')
  }

  const onMinus = () =>{
    dispatch('minus')
  }

  return (
    <div className='App'>
      <h1>Count: {count}</h1>
      <button onClick={onPlus}>+</button>
      <button onClick={onMinus}>-</button>
    </div>
  );
}

// Log to console
console.log('Hello console')
```