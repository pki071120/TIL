# Custom Hook? util function
### ✔ Custom Hook
-  React에서 `Custom Hook`은 상태 로직을 재사용할 수 있도록 하는 기능이다.  
-> 공통적으로 사용되는 상태 로직을 추출하여 하나의 함수로 만들어 사용할 수 있도록 한다.  
-  보통 use라는 접두사를 사용하여 함수의 이름을 정의하며, React의 기본 훅을 이용하여 구현된다.
### ✔ Util Function
- React에서 <u>유틸함수</u>는 일반적으로 리액트에서 자주 사용되는 기능들을 모듈화하여 재사용할 수 있도록 도와주는 함수들이다.  
-> 코드의 중복을 줄이고 유지보수성을 높일수 있다.  
- 프로젝트에서 자주 사용되는 함수들을 모아서 별도의 파일로 관리하는 것이 일반적이다.

### ✔ 유틸 함수와 커스텀 훅의 차이점

``` js
function formatDate(dateString, format) {
  const date = new Date(dateString);
  return date.toLocaleDateString(format);
}
```
> 날짜 문자열을 특정 형식으로 지정하는 유틸 함수

이 함수는 날짜, 형식 문자열을 인수로 사용하고 지정된 형식에 따라 날짜 문자열을 반환함.(날짜 형식이 필요한 응용 프로그램 어디서든 호출 가능)

``` jsx
import { useState, useEffect } from 'react';

function useTimer(initialTime) {
  const [time, setTime] = useState(initialTime);

  useEffect(() => {
    const timer = setInterval(() => {
      setTime((prevTime) => prevTime + 1);
    }, 1000);

    return () => clearInterval(timer);
  }, [initialTime];)

  return time;
}
```
> 초기 시간 값을 인수로 사용하고 매초 시간 값을 업데이트 하여 반환하는 커스텀 훅

다음과 같은 타이머 기능을 제공하기 위해 기능 구성 요소에서 사용할 수 있다.
``` jsx
function Timer() {
  const time = useTimer(0);

  return (
    <div>
      {time}
    </div>
  );
}
```

### ❗ 정리
-`유틸 함수`는 특정 작업을 수행하고 애플리테이션의 여러 부분에서 재사용할 수 있는 `독립 실행형 함수`.  
-입력 인수를 받아 계산을 수행하고 결과를 반환

-`커스텀 훅`은 React hook을 사용하여 구성 요소에 `특정 동작`이나 `기능`을 제공.  
-`재사용`이 가능하도록 설계되어 기능 구성 요소 내에서 호출할 수 있다.

<b>요약</b>  
`유틸 함수`는 애플리케이션의 어느 곳에서나 사용할 수 있는 `독립 실행형 함수`인 반면 `커스텀 훅`은 React hooks를 사용하여 구성 요소에 `특정 동작이나 기능을 제공하는 함수`이다

>출처 : https://growing-jiwoo.tistory.com/m/83