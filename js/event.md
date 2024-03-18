# event
특정 트리거로 인해 사건을 발생시키는 것

## 종류
#### 1. 마우스 이벤트
---
|event|detail|
|:--:|:--:|
click | 마우스를 클릭했을 때 
dbclick | 마우스를 더블클릭했을 때
mouseover | 포인터를 요소에 가져다 댔을 때
mouseout | 포인터를 요소에서 뗐을 때
mousedown | 마우스를 눌렀을 때
mouseup | 마우스를 떼었을 때
mousemove | 포인터가 움직였을 때
contextmenu | 마우스 우클릭을 했을 때 나오는 메뉴가 나오기 전

#### 2. 키이벤트
---
|event|detail|
|:--:|:--:|
keydown | 키를 눌렀을 때 
keyup | 키를 떼었을 때
keypress | 키를 누루고 있는 상태일 때

#### 3. 폼 이벤트
---
|event|detail|
|:--:|:--:|
focus | 요소에 포커스가 되었을 때 
blur | 요소에 포컷스가 벗어났을 때
change | 값이 변경 되었을 때
submit | 제출을 할 때
reset | 초기화를 했을 때
select | input 안의 내용을 드래그하여 선택했을 때

#### 4. 기타 이벤트
---
|event|detail|
|:--:|:--:|
load | 페이지 로딩이 완료되었을 때 
abort | 키를 떼었을 때
unload | 페이지가 다른 곳으로 이동될 때
resize | 요소의 사이즈에 변화가 생겼을 때
scroll | 스크롤바를 움직일 때

## 이벤트 연결
`'이벤트 핸들러'` : 이벤트 발생 시 발생된 이벤트에 대응하여 처리하는 것  
'이벤트 핸들러'는 앞에 `on`을 붙여서 동작 처리

#### 1. 인라인 방식
``` html
<button onclick="alert('클릭')" value="버튼"/>
<button onclick="view()" value="버튼">

<script>
  fucntion view(){
    alert("클릭");
  }
</script>
```

#### 2. 고전 방식
``` html
/ S1 /
<script>
  var bt = document.getElementById("bt");
  bt.onclick = function(){
    alert("클릭");
  }
</script>


/ S2 /
<script>
  var bt = document.getElementById("bt");
  function view() {
    alert("클릭했습니다!!!");
  }   
  bt.onclick = view;
  /*
  bt.onclick = function() {
    view();
  }
  */
</script>
```

※ `<script></script>`를 head태그 내부에서 작성할 경우  
위의 코드를 예시로 document에는 클래스가 bt인 버튼이 없는데 bt를 선을 한 것이기에 오류 발생 => onload를 사용하여 페이지가 로딩이 완료 되었을 때 실행이 될 수 있도록 이벤트를 작성해야함.