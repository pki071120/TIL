# useMemo와 useCallback의 차이점

## useMemo, useCallback?
<b>[ 메모이제이션 (memoization) ]</b>  
-`메모이제이션`이란, 기존 연산값을 어딘가에 저장하고 동일한 값이 들어오면 재활용 하는 기법  
-중복 연산을 피할 수 있기에 메모리를 조금 더 쓰더라도 `애플리케이션의 성능을 최적화`할 수 있다.  
<br>
<b>[ useMemo ]</b>  
-React 컴포넌트에서 계산 비용이 큰 연산을 최적화하는데 사용되는 hook.
-이전의 계산값을 기억하고 해당 값이 변경되지 않는다면 이전 값을 재사용.  
=> `메모이제이션된 값`을 반환

``` jsx
useMemo(() => fn, deps);
```
>useMemo는 deps가 변한다면, () => fn이라는 함수를 실행후 함수의 변환 값을 반환한다.
### ex

``` jsx
import React, { useState, useCallback, useMemo } from "react";

export default function App() {
  const [ex1, setEx1] = useState(0);
  const [ex2, setEx2] = useState(0);

  useMemo(() => {console.log(ex1)}, [ex1]);

  return (
    <>
      <button onClick={() => setEx1((curr1) => (curr1 + 1))}>x</button>
      <button onClick={() => setEx2((curr2) => (curr2 + 1))}>y</button>
    </>
  );
}
```
> 버튼 x를 클릭하면 'ex'라는 상태값이 변화한다.

``` jsx
useMemo(() => {console.log(ex)},[ex])
```
위 코드에서 deps는 [ex1]이기에 ex1이 변할 때만 `() => {console.log(ex)}`가 실행된다.  
=> x버튼을 누를 때만 콘솔 창에 ex값이 출력이 되지만, y버튼을 누르더라도 리렌더링은 되지만 useMemo에는 변화가 없음.

<b>[ useCallback ]</b>  
-React 컴포넌트에서 함수를 메모이제이션하여 성능을 최적화하는데 사용되는 hook.  
-생성된 이정의 함수를 기억하고, 해당 함수를 재사용함.  
=> `메모제이션된 함수`를 반환  

``` jsx
useCallback(fn, deps)
```
useCallback은 deps가 변한다면 fn이라는 새로운 함수를 반환.

``` jsx
import React, { useState, useCallback, useMemo } from "react";

export default function App() {
  const [ex1, setEx1] = useState(0);
  const [ex2, setEx2] = useState(0);

  const useCallbackReturn = useCallback(() => {console.log(ex2)}, [ex1]);

  return (
    <>
      <button onClick={() => setEx1((curr1) => (curr1 + 1))}>x</button>
      <button onClick={() => setEx2((curr2) => (curr2 + 1))}>y</button>
    </>
  );
}
```
>처음 예시와 같은 버튼을 클릭할 시 이벤트가 발생하는 코드.  useCallback은 () => {console.log(ex2)}라는 함수를 반환함.

### useCallback의 순서  
```
1. 처음 컴포넌트 시작시 () => {console.log(0)} 실행  
2. ex1이 변할 때까지 함수는 () => {console.log(0)}  
3. ex1이 변한다면 그때 ex2의 값을 가져오고 () => {console.log(변한 ex2값)}
```
-deps가 변해야 함수 컴포넌트와 상태 값을 공유  
=> 상관없는 상태 값이 변할 때, `불필요하게 함수를 업데이트하는 것을 방지`해 줌.

<b>요약</b>  
- useMemo는 계산 비용이 큰 연산의 결과값을, useCallback은 함수를 메모이제이션하여 재사용 한다.  

-  useMemo는 연산 결과를 반환하고, useCallback은 함수를 변환한다.  

- useMemo는 연산을 최적화하는 데 사용된다.

- useCallback은 함수를 최적화하는데 사용된고, 불필요한 함수 재생성을 방지하는데 사용된다.

- 의존성 배열로 어떤 값이 변경되었을 때에만 값, 함수를 갱신하도록 설정할 수 있다.

- 최적화를 위한 강력한 도구로 사용된고, 애플리케이션의 성능을 향상할 수 있다.