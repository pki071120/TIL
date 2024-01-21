# 정규식 (Regular Experssion)
## ✔ 정규식이란
: 문자열에서 `특정 문자 조합을 찾기 위한 패턴`. JS에서는 RegExp의 exec(), test()메서드를 사용할 수 있다.

## ✔ 정규 표현식 만들기
``` js
const re = /ab+c/;
```
1. 정규 표현식 리터럴. 위와 같이 슬래시로 패턴을 감싸서 작성함.  
- 스크립트를 불러올 때 컴파일 되므로, 바뀔 일이 없는 패턴의 경우 리터럴을 사용하면 성능이 향상될 수 있다.
``` js
const re = new RegExp("ab+c");
```
2. `RegExp`객체의 생성자 호출.
- 정규 표현식이 런타임에 컴파일된다. 바뀔 수 있는 패턴이나, 사용자 입력 등 외부 출처에서 가져오는 패턴의 경우 이렇게 사용함.
## ✔ 플래그
- 정규 표현식의 옵션이므로 선택적으로 사용 가능.  
- 순서와 상관없이 하나 이상의 플래그를 동시에 설정 가능.
- 플래그를 사용하지 않는 경우, 문자열 내 검색 대상이 1개 이상이더라도 첫번째 조건 대상만을 검색하고 종료.
> 🚩 대표적인 플래그  
i (ignore case) : 대소문자를 구별하지 않고 검색함.  
g (global) : 문자열 내의 모든 패턴을 검색함.  
m (multi line) : 문자열의 행이 바뀌더라도 검색은 계속함.
## ✔ 패턴
매칭하여 검색하고 싶은 문자열을 지정.  
따옴표는 생략하고 선언한다.  
  
정규 표현식 패턴을 작성할 때는 일반 문자와 특수 문자를 사용할 수 있는데, 일반 문자는 리터럴 문자 / 특수 문자는 메타 문자로 표현한다.
> <b>리터럴 문자 (정규 문자)</b> : 일반 문자, \0, \n, \t, \v, \f, \r, \xhh, \uhhhh, \cX
> <b>메타 문자 (정규 표현식의 구문 문자)</b> : ^ $ \ . * + ? () [] {} |_

## ✔ 메타 문자
패턴을 만들 때 사용할 수 있는 특정  패턴을 기술하는 문자.  
조금더 복잡하고 다양한 케이스의 경우를 다룰 때 사용되는 것.  
  
<br>
❗ <b>메타문자 : 매칭 패턴</b>

| 패턴 |  의미 |
| :-- | :-- |
|a-zA-Z | 영어 알파벳(-으로 범위 지정) |
|ㄱ-ㅎ가-힣| 한국 문자(-으로 범위 지정)|
|0-9|숫자(-으로 범위 지정)|
|.|모든 문자열(숫자, 한글, 영어, 특수기호, 공백 모두 !단, 줄바꿈X)|
|\d|숫자|
|\D|숫자가 아닌 것|
|\w|영어 알파벳, 숫자, 언더스코어(_)|
|\W|\w가 아닌 것|
|\s|space 공백|
|\S|space 공백이 아닌 것|
|\특수기호|특수기호|  

<br>
❗ <b>메타문자 : 매칭 패턴</b>

| 기호 | 의미 |
| :-- | :-- |
|[] | 괄호안의 문자들 중 하나 |
|[^문자]| 괄호안의 문자를 제외한 것|
|^문자열|특정 문자열로 시작(괄호 없음!)|
|문자열$|특정 문자열로 끝남|
|()|그룹 검색 및 분류(match메서드에서 그룹별로 묶어줌)|
|(?: 패턴)|그룹 검색(분류X)|
|\b|단어의 처음/끝|
|\B|단어의 처음/끝이 아님|  

<br>
❗ <b>메타문자 : 매칭 패턴</b>

| 기호 | 의미 |
| :-- | :-- |
|? | 최대 한번(없음 or 1개) |
|* | (없음거나 있음): 여러개 포함|
|+|최소 1개(1개 or 여러개) |
|{n}|n개|
|{Min,}|최소 Min개 이상|
|{Min, Max}|최소 Min개 이상, 최대 Max개 이하|  

### RegExp 생성자 함수 방식

``` js
const regexp = new RegExp(/^abc/i);
```
- 생성자 함수 방식은 바뀔 수 있는 패턴이나, 사용자 입력 등 외부 출처에서 가져오는 패턴의 경우에 사용하는 것이 좋다.
---
## ✔ 정규표현식의 method
JS에서는 정규 표현식도 객체로서 메서드의 사용이 가능함.

### 1) 정규식 RegExp.prototype의 메서드
❗ <b>exec</b>
``` js
console.log(/5/.exec("RegExp Study Start"));
// 결과값 : ["S", index:7, input:"RegExp Study Start"]
```
- 대상을 검색하여 조건에 부합하는 결과를 배열로 반환.
- 단 조건에 부합하는 결과가 1개 이상이라도 무조건 부합하는 결과의 첫번째 값을 반환

❗ <b>test</b>
``` js
console.log(/S/.test("RegExp Study"));
// 결과값 : true
```
- 대상의 매치 여부를 boolean값(true / false)로 반환한다.

### 2) 문자열 String.prototype의 메서드
❗ <b>match</b>
``` js
console.log('RegExp Study'.match(/Study/));
// 결과값 : ["Study", index:7, input:"RegExp Study"]
```
- 정규식 조건에 부합하는 문자열을 배열 형태로 반환.  
- 조건에 부합하는 문자열이 없으면 null 반환.

❗ <b>search</b>
``` js
console.log('RegExp Study'.search(/Study/));
// 결과값 : 6
```
- 정규식 조건에 부합하는 문자열의 index 번호를 반환해준다.  
- 조건에 부합하는 문자열이 없으면 null을 반환.

❗ <b>replace</b>
``` js
console.log('RegExp Study'.replace("Study","Test"));
// 결과값 : RegExp Test
```
- 조건에 부합하는 문자열을 찾고, 그 문자열을 다른 문자열로 변환.

❗ <b>split</b>
``` js
console.log('RegExp Study'.split(" "));
```
- 조건에 부합하는 값을 기준으로 대상을 자른후, 배열로 저장.
- split할 대상에 아무런 입력도 하지 않을 시(여백도 포함), 대상을 하나의 배열로 변환.

## 정규 표현식의 활용
1. 웹사이트 주소
``` js
const urlRegexp =
/^((http:\/\/www\.)|(www\.)|(http:\/\/))[a-zA-Z0-9._-]+\.[a-zA-Z .]{2,5}$/;

console.log(urlRegexp.test("www.domain.com")); //true
console.log(urlRegexp.test("http://www.domain.com")); //true
console.log(urlRegexp.test("http://domain.com")); //true
console.log(urlRegexp.test("www.domain.co.cc")); //true
```
2. 전화번호
- 일반 전화
``` js
const localPhone = /^(0(2|3[1-3]|4[1-4]|5[1-5]|6[1-4])-)(\d{3,4}-)(\d{4})$/;

console.log(localPhone.test("02-345-6789")); //true
```
- 휴대폰 전화
``` js
const cellPhone = /^(?:(010)|(01[1|6|7|8|9]))-\d{3,4}-(\d{4})$/;

console.log(cellPhone.test("010-123-4567")); //true
```
3. 이메일 주소
``` js
const cellPhone = /^(?:(010)|(01[1|6|7|8|9]))-\d{3,4}-(\d{4})$/;

console.log(cellPhone.test("010-123-4567")); //true
```
4. 아이디/비밀번호 사용 가능 검사
``` js
const email = /[0-9a-zA-Z]([-_.]?[0-9a-zA-Z])*@[0-9a-zA-Z]([-_.]?[0-9a-zA-Z])*.[a-zA-Z]$/i;

console.log(email.test("hello5@email.com")); // true
```

자료 출처 : https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Regular_expressions, https://velog.io/@purplew/Javascript-%EC%A0%95%EA%B7%9C%ED%91%9C%ED%98%84%EC%8B%9D