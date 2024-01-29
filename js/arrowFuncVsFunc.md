# Arrow Function과 Function

## 화살표 함수란

ES6에서 새로 추가된 내용으로, 기존 함수 표현식과 비교하면 간결한 표현으로 간단하게 사용가능함.
``` js
function func() {//일반
  console.log("hi");
}

const arrFunc = () => {//화살표
  console.log("arrow hi");
}
``` 

## 차이점

<b>1. this</b>

✔ 일반함수  
- JS에서 모든 함수는 실행될 때마다 함수 내부에 this라는 객체가 추가.
- 함수를 선언할 때 this에 바인딩할 객체가 정적으로 결정되는 것이 아닌, 함수를 호출할 때 `함수가 함수호출방식 따라 this에 바인딩할 객체가 동적으로 결정`됨.  

✔ 화살표 함수  
- 함수 선언시 this에 바인딩할 객체가 정적으로 결정.
- 언제나 상위 스코프의 this를 가리킴.

``` js
function func() {
  this.name = "화살표";
  return {
    name: "일반",
    speak: function () {
      console.log(this.name);
    },
  };
}

function arrFunc() {
  this.name = "화살표";
  return {
    name: "일반",
    speak: () => {
      console.log(this.name);
    },
  };
}

const fun1 = new fun();
fun1.speak(); // 일반

const fun2 = new arrFun();
fun2.speak(); // 화살표
```

<b>2. 생성자 함수로 사용 가능 여부</b>  
- 일반 함수 : ⭕
- 화살표 함수 : ❌ => `prototype 프로퍼티`를 가지고 있지 않기 때문

<b>3. arguments 사용</b>  
- 일반 함수 : ⭕
- 화살표 함수 : ❌ => arguments변수가 전달되지 않음

``` js
// 일반 함수

function func() {
  console.log(arguments); // Arguments(4) [1, 2, 3, 4, callee: ƒ, Symbol(Symbol.iterator): ƒ]
}

fucn(1,2,3,4);

// 화살표 함수

const arrFunc = () => {
  console.log(arguments); // Uncaught ReferenceError: arguments is not defined
}

arrFunc(1,2,3,4);
```
