# 1. 마크다운의 장/단점
## #1.장점
1. 문법이 쉽고 간결하다.
2. 관리가 쉽다.
3. 별도의 도구없이 작성가능하다.
4. 다양한 형태로 변환이 가능하다.
5. 지원 가능한 플랫폼과 프로그램이 다양하다.
6. 텍스트로 저장되기 때문에 용량이 적어 보관이 용이하다.

## #2.단점
1. 표준이 없다.
2. 표준이 없기 때문에 표현하는 도구에 따라서 동작하지 않거나, 다르게 표현 될 수 있다.
3. 모든 HTML 마크업을 대신하지 못하는 한계점.

# 2. 마크다운 문법
## #1. 제목(Header)
1. #뒤에 띄어쓰기를 넣어주는게 권장하는 방법 이다.
2. <h1> ~ <h6> 까지 표현 가능하다.

## #2. 줄바꿈
- 띄어쓰기 2번 또는 <br/>로 표현 가능 하다.

## #3. 수평선
- 하기 코드들은 모두 수평선을 나타낸다. 가시적으로 페이지를 나누는 용도로 많이 사용된다.

## #4. 글자 강조
**굵은 글씨**
*이텔릭*
_이텔릭_
~~취소선~~
<u>밑줄</u>
ex)
This is the **bold** text and this is the *italic* text and <u>let's</u> do ~~strikethrough~~

## #5. 인용문
> 인요문장
>> 중첩된 인용문
>>> 중첩된 인용문2

## #6. 목록
1. 순서가 없는 목록 (*,+,- 지원)

### - bullet list
- 순서가 필요하지 않은 목록
  - 순서가 필요하지 않은 목록
    - 순서가 필요하지 않은 목록
* 순서가 필요하지 않은 목록
  * 순서가 필요하지 않은 목록
    *순서가 필요하지 않은 목록
+ 순서가 필요하지 않은 목록
  + 순서가 필요하지 않은 목록
    + 순서가 필요하지 않은 목록

2. 순서가 있는 목록

  1. 순서가 필요한 목록
    1. 순서가 필요한 목록
    1. 순서가 필요한 목록
  1. 순서가 필요한 목록

  1. 순서가 필요한 목록
    9. 순서가 필요한 목록
    3. 순서가 필요한 목록
  8. 순서가 필요한 목록

3. 혼합 사용하는 예시

- 순서가 필요한 목록
  1.순서가 필요한 목록
  1.순서가 필요한 목록
- 순서가 필요하지 않은 목록2
  1.순서가 필요한 목록
  3.순서가 필요한 목록
  8.순서가 필요한 목록

## #7. 링크
1. 기본방법
[Title](Link)
ex) 여기를 클릭 -> [유튜브](https://youtube.com)

2. 참조 링크 사용 방법
[link keyword][id]
[id]:URL "Optional Title"
ex) 여기를 클릭 -> [유튜브][youtube]
[youtube]:https://youtube.com
ex2 title 옵션사용시 커서를 링크 위로 위치하면, title이 노출된다.)
여기를 클릭 -> [유튜브][youtube]
[youtube]:https://youtube.com "Click here to youtube"

## #8. 이미지
- 링크와 문법이 유사하다. 앞에 !만 추가하면 된다.
1. 기본문법
![대체텍스트](이미지주소)
ex) ![youtube](https://upload.wikimedia.org/wikipedia/commons/thumb/7/72/YouTube_social_white_square_%282017%29.svg/1280px-YouTube_social_white_square_%282017%29.svg.png)
2. 참조 링크 사용 방법
:[대체텍스트][id]
[id]: 이미지주소 "Optional TItle"
ex) :[유튜브][youtube]
[youtube]: https://upload.wikimedia.org/wikipedia/commons/thumb/7/72/YouTube_social_white_square_%282017%29.svg/1280px-YouTube_social_white_square_%282017%29.svg.png "youtube img"
3. 이미지 노출과 동시에 링크처리
[![대체텍스트](이미지주소)](링크주소)
ex) [![youtebe](https://upload.wikimedia.org/wikipedia/commons/thumb/7/72/YouTube_social_white_square_%282017%29.svg/1280px-YouTube_social_white_square_%282017%29.svg.png)](https://youtube.com)

## #9. 표
1. | 기호를 통해 테이블을 표현 가능. (가장 좌측, 우측 생략가능)
2. 헤더와 셀을 구분할 때 3개 이상의 -(하이픈, 대시)가 필요하다.
3. : 기호를 통해 정렬할 수 있다.
ex)
### 표
| Header | value | Description |
| --: | :-- | :--: |
| 정렬 | --: | 우측정렬 |
| 정렬 | :-- | 좌측정렬 |
| 정렬 | :--: | 가운데정렬 |

## #10. 코드
1. 인라인 코드
- 백틱(': 숫자 1번 키 왼쪽에 위치)으로 강조할 내용을 감싸면 된다.
ex) `해당코드`는 강조할 부분 이다.

2. 블럭 코드
-``` html, css, jacascript, bash, plaintext 등등
  - 코드의 종류를 명시 하지 않은 경우
  ex) ```
    <a href="https://youtube.com" title="유튜브로 이동">유튜브로 이동</a>
  ```
  - html
  ex) ``` html
    <a href="https://youtube.com" title="유튜브로 이동">유튜브로 이동</a>  
  ```
  - css
  ex) ``` css
  div{
    background-color:red;
  }
  ```
  - javascript
  ex) ```javascript
  const name = "youtube"
  console.log(name);
  ```
  - bash
  ex) ``` bash
  $ ls -al
  ```
  - 이외 텍스트
  ex) ``` plaintext
  코드 이외의 텍스트들
  ```

## #11. 원시 HTML
1. MarkDown 환경에서는 결국 표현의 한계가 있고, 이런 경우 순수 html문법을 사용할 수 있다.
ex) image를 표현할 때 MarkDown으로는 width지정이 불가능 하다.
```html 
<img width="70" src="" alt="gods" />
```
ex) 링크를 표현할 때 target="_blank" 지정이 불가능 하다.
ex) 밑줄을 표현할 수 없어 <u></u>를 사용하거나 다음과 같이 style을 직접 지정해줘야 한다.
```html
<span style="text-decoration: underline;">유튜브</span> 입니다.
```