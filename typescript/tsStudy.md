# TS (typescript)
### : 변수의 타입을 지정  
사용법
``` ts
let val:number //변수명뒤에 :(콜론)쓰고 타입을 작성해주면 된다.
let val2: number | string = 5// 타입 뒤에 |(or)을 추가하여 타입의 허용 범위를 늘릴 수 있다.
val1 = 5
val1 = "hi typescript" //오류발생

val2 = "hello typescript"
```
| 종류 | 특징 | 
| :-- | :-- |
| string | 문자열 값을 가진다. |
| number | int, float, double 타입은 없고, JS의 number 자료형 그대로 사용한다. 10진수 이외의 리터럴도 지원. |
| boolean | 참, 거짓 값을 가진다. |
| null, undefined | 모든 타입의 하위 타입으로 치부된다. | 
| any | 모든 타입의 값을 허용한다. |
| (type)[] | 타입의 배열임을 나타낸다. |
## TS 함수 사용법
``` ts
function addNum(a:number, b:number):number{
  console.log(a+b) // 10
  return a+b;
}

addNum(3, 7);
```
매개변수의 타입을 지정하고 어떠한 타입을 반환시킬 것인지도 지정한다.

## TS 컴파일 방법
브라우저는 ts파일을 이해하지 못하기 때문에 tsc라는 명령어를 사용하여 js파일을 만들고 그 js파일을 컴파일 한다.

## tsconfig
tsc를 이용하여 js파일을 만들때 세부사항(js버전, js파일 폴더 등등 )

## TS 프로젝트 생성
```
npx create-react-app (프로젝트 이름) --template typescript
```
