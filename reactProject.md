## CRA의 초기 폴더 구조
- node_modules<br>

-- 현재 프로젝트에 포함된 라이브러리들이 설치되어 있는 폴더.  
-- 깃과 같은 저장소에 올릴 때는 함께 올리지 않음.

- public<br>
-- index.html과 같은 정적 파일이 포함되는 곳.<br>
-- 컴파일이 필요없는 파일들이 위치하는 폴더.

- src<br>
-- 거의 모든 파일들이 이 폴더 내부에서 작성됨.<br>
-- 폴더내의 파일들은 명령어에 따라 JS로 컴파일이 진행됨.

- .gitignore<br>
깃에 포함하고 싶지 않은파일의 이름 혹은 폴더등을 입력하는 파일.

- package.json<br>
-- 프로젝트에 관련된 기본적인 내용과 라이브러리들의 목록이 포함되어 있음.<br>
=> 누군가 프로젝트를 클론할 때 이 package.json에 적혀있는 라이브러리의 목록을 기준으로 npm에서 설치하게 됨.

- README.md<br>
-- 프로젝트의 설명을 작성하는 곳<br>
-- 가장 먼저 띄워짐.

## src 내부 폴더구조
- components<br>
-- 재사용 가능한 컴포넌트들이 위치하는 폴더.<br>
-- 이 폴더 내부에서 하위폴더로 추가로 분류하는 경우가 많음.
- assets<br>
-- 이미지, 폰트와 같은 파일들이 저장되는 폴더<br>
-- public에 직접 넣는 경우도 있는데 둘의 차이는 컴파일시에 필요한지의 여부임.<br> ex) `index.html`에서 사용하여 컴파일 단계 불필요 => public, 컴포넌트 내부에서 사용하여 컴파일 단계 필요 => assets
- hooks<br>
-- 커스텀 훅이 위치하는 폴더.
- pages  
-- react router등을 이용하여 라우팅을 적용할 때 페이지 컴포넌트를 이 폴더에 위치시킴.
- constants<br>
-- 공통적으로 사용되는 상수들을 정의한 파일들이 위치하는 폴더.
- config <br>
-- config 파일이 많지 않은 경우 보통 최상위에 위치시켜놓지만 여러개의 config 파일이 있을 경우 폴더로 분리하기도 합니다.
- styles<br>
-- css 파일들이 포함되는 폴더입니다.
- services<br>
-- api관련 로직의 모튤 파일, auth와 같은 인증과 관련된 파일이 포함됨.
- utils<br>
-- 정규표현식 패턴, 공통함수 등 공통으로 사용하는 유틸 파일들이 위치하는 폴더.
- contexts<br>
-- contextAPI를 사용할 때 관련 파일들이 위치하는곳으로 상태관리를 위해 contextAPI대신 redux를 사용 할 경우 폴더 이름을 `store`로 사용하기도 함.
- App.js<br>

- index.js<br>