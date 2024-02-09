# useRef?
useRef는 `저장공간 또는 DOM요소에 접근하기 위해 사용되는 React Hook`이다.  
React를 사용하는 프로젝트에서도 가끔씩 `DOM을 직접 선택해야 하는 상황이 필요` => useRef라는 hook을 사용함


# 사용 예시
## 변수 관리
```jsx
import { useState, useRef } from "react";

const [value1, setValue1] = useState(0);
const value2 = useRef(0);
let value3 = 0;

function v1Up(){
  setValue1(current => current+1)
  console.log(value1);
}

function v2Up(){
  ++value2.current;
    console.log(value2);
}

function v3Up(){
  ++value3;
    console.log(value3);
}

return (
  <>
    <div>val1 = {value1}</div>
    <div>val2 = {value2.current}</div>
    <div>val3 = {value3}</div>
    <br>
    <button onClick={v1Up}>V1 up</button>
    <button onClick={v2Up}>V2 up</button>
    <button onClick={v3Up}>V3 up</button>
  </>
)
```
`useState`를 사용해 값을 저장한 value1, `useRef`를 사용해 값을 저장한 value2, `변수`를 통해 값을 저장한 value3이 있다.   
V2 up버튼을 눌렀을때 `value2는 콘솔창에는 값이 올라간 상태로 출력`되지만 화면에는 `렌더링 되지 않는것`을 볼 수 있다. 하지만 V1 up 버튼을 눌렀을때 `렌더링 되면서 값이 올라간 value2값이 화면에 출력`이 된다.  
=> 이같은 useRef는 화면이 몇번 렌더링 되었는지 알 수 있도록 코드를 작성하는데 사용될 수 있다.