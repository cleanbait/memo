# HTML
<pre>
1. 텍스트<text>

b, strong    글자를 굵게 해주는 태그
h            텍스트크기 1~6
p            단락을 나눠줌
br           라인을 바꿔줌
hr           수평선
i, em        이탤릭체
pre          줄바꿈과 띄어쓰기 적용
span         영역을 묶는용도
ul li        순서가 없는 목록
ol li        순서가 있는 목록


2. 테이블 <table>

table       표를 만듦 (tr, td th)
caption     표의 제목
thead       상단
tbody       내용
tfoot       하단
colgroup    열을 묶어줌 (col)

테이블 속성 = colspan, rowspan 합치기


3. 링크<link>

a      태그    클릭하면 화면 링크타게해줌
map    태그    img태그에 usermap(#)속성을 설정 후 area태그로 지정
img    태그    src속성을 이용하여 링크

href   속성 : 링크할 문서나 주소를입력 (#이름) 후 링크할 곳에 (id="이름")으로 링크설정
target 속성 : 링크가 이동할 위치를 지정 _black 새창 | _self 기본값
coods  속성 : 왼쪽위->오른쪽밑 좌표설정
shape  속성 : 형태


4. 폼 <form> 4가지 속성

method 속성 : 사용자가 입력한 데이터를 서버로 전송하는 방식 ("get과 post"가 있다)
get  // 주소창에 사용자가 전송한 데이터가 쿼리스트링 방식(key, value)으로 전송, 주소창에 데이터가 표시 (최대 4096byte까지 전송)
post // 전송데이터의 길이 제한이 없고 입력한 내용이 표시되지 않는다. (보안이 요구될때, 개인정보라던가)
name   속성 : 폼의 이름을 지정
action 속성 : 폼 태그의 내용을 전송할 위치 지정 (서버의 주소)
target 속성 : 링크가 이동할 위치를 지정 _black 새창 | _self 기본값



fieldset  태그    폼을 하나의 영역으로 묶어주며 외각선을 그려줌
legent    태그    fieldset의 제목
textarea  태그    텍스트를 입력할 수 있는 입력 창 (rows 세로, cols 가로 속성을 이용하여 초기 크기지정)
select    태그    option태그를 이용하여 선택 할 수 있게 창을 만듬.  value속성 입력가능
selected는 기본 선택 값 (size(화면에 표시될 드롭다운 메뉴의 갯수),  multiple(다중선택) 속성이 있다)

label     태그    사용자 편의성 태그이며 이 태그로 감싸주면 글자를 눌러도 선택가능


5. 인풋 <input>

타입 속성들
text     : 일반적인거 ★
password : 안보이게 해줌
hidden   : 숨겨진요소 네임 벨류 설정시 ★
search   : 검색창 같은곳에 쓰는건데 텍스트와 다른점은 x버튼이 생겨서 초기화하기 편함
tel      : 전화번호 넣는거
url      : 도메인주소
email    : e메일주소
datetime : 날짜
datetime-local : 날짜선택 및 현재시간
date     : 년월일
month    : 년월
week     : 년~번째주
time     : 시간입력
number   : 숫자입력
range    : 조절바
radio    : 단일버튼 (네임을 맞춰줘야 한다.)
checkbox : 다중버튼 (네임을 독립적으로 맞춰줘야 한다.)
file     : 파일 여는 창
submit   : 검색버튼 ★
reset    : 다 없어짐 ★
button   : 누를 수 있는 버튼 생성 ★

placeholder : 창에 사용자 편의 텍스트 설정
readonly    : 읽을수만 있고 사용자가 수정못함
value       : 서버에게 주는 값
autofocus   : 자동 커서 기능
name        : 인풋 이름설정
</pre>
# CSS
<pre>
1. 선택자 = 태그, id, class, 가상선택자 등이 있다. || 선택자 { 스타일속성 : 속성값 ; }

* {}            전체선택자
#ID값 {}        id= 아이디선택자 (ID값 받음)
태그명 {}       태그선택자 (태그 이름 받음)
.클래스값 {}    class= 클래스선택자 (클래스값 받음)
선택자간 띄움    하위선택자 (부모 하위요소 모든것)
선택자간 >       자식선택자 (부모 > 자식요소 딱 1개만)

=========================================================

태그에 넣을 수 있는 속성값들

글자관련 속성값들
text-align       텍스트 문단 정렬방식 (렢 랖 저스팊 센타)
font-size        폰트크기 px랑 em이 있다. (1em -> 16px)이며 px은 모니터 크기에 따라 상대적
color            글자색 #RGB와 일반설정이 있다.
font-family      폰트 뭘로할건지
list-style-type  ul li이나 ol li 쓸때 쓰는거 앞에 모양 어떻게 할건지

이미지,블록,창 관련 속성값들
background-color    요소의 색깔
background-image    요소의 이미지링크
background-repeat   요소의 반복여부
background-size     요소의 크기설정 px과 %로 조절
width               가로
height              세로
border-color        요소의 테두리 색깔
border-style        요소의 테두리 스타일
border-width        요소의 테두리 크기
border-radius       요소의 테두리 모서리 다듬기
margin              테두리 밖의 여백
padding             테두리 안의 여백
display             요소를 어떻게 보여줄건지 (block 세로, inline 가로)
float               요소 위치설정

★position    (요소 안 요소들의 배치)

position : static | relative | absolute | fixed
static   :  요소를 문서 흐름에 맞추어 배치
relative :  이전 요소(부모)에 연결하여 위치 조정
absolute :  원하는 위치에 배치 (부모를 기준)
fixed    :  고정된 위치에 배치 (브라우저 기준)

스테틱(기본값)을 제외한 나머지 속성들은 top, left, bottom, right를 써서 위치 지정 가능
</pre>

# jQuery

<pre>
$(selector).action();

$ 는 jQuery 를 [ 실행 ] 하는것을 말한다.
(selector) 는 [ HTML 요소 ] 를 말한다.
action() 는 [ 요소에서 실행할 명령 ] 을 말한다.
</pre>
<pre>
전체 선택자("*")           : HTML 문서 내의 모든 태그를 선택
태그이름 선택자("태그이름") : 지정한 태그이름에 해당하는 태그를 가져온다.
아이디 선택자("#아이디")   : id 속성에 해당하는 태그 객체를 가져온다.
클래스 선택자(".클래스")   : class 속성에 해당하는 태그 객체를 가져온다.
</pre>
<pre>
태그에 설정되어 있는 속성을 선택하기 ( 선택자 다음[] )
[속성]         : 속성을 가지고 있는 태그 선택
[속성 = 값]    : 값과 일치하는 태그를 선택
[속성 != 값]   : 값과 일치하지 않는 태그를 선택
[속성 ^= 값]   : 값으로 시작하는 태그를 선택
[속성 $= 값]   : 값으로 끝나는 태그를 선택 
[속성 |= 값]   : 속성의 값과 일치or시작하고 하이픈으로 연결된 태그를 선택
[속성 ~= 값]   : 딱 값만을 단어로 가지고 있는 태그를 선택
[속성 *= 값]   : 값을 포함하는 태그를 선택
</pre>
<pre>
- 첫 번째 태그 선택하기 ( 선택자 다음 : ) -

:first          : 선택자에 해당하는 태그 중 가장 처음 태그가 선택
:first-child    : 선택자에 해당하는 태그 중 각 영역별 첫 번째 태그가 선택. 처음 태그가 선택자에 해당하지 않으면 선택되지 않는다.
:first-of-type  : 선택자에 해당하는 태그 중 각 영역별 처음 태그가 선택

- 마지막 태그 선택하기 -
:last           : 선택자에 해당하는 태그 중 가장 마지막 태그가 선택
:last-child     : 각 영역별 마지막 태그가 선택. 마지막 태그가 선택자에 해당하지 않으면 선택되지 않는다.
:last-of-type   : 선택자에 해당하는 태그 중 각 영역별 마지막 태그가 선택

:odd            : 인덱스 번호(0부터 시작)가 홀수인 태그 선택
:even           : 인덱스 번호(0부터 시작)가 짝수인 태그 선택

:only-child     : 영역 내에서 선택자에 해당하는 태그가 하나일 경우 선택
:only-of-type   : 영역 내에서 선택자에 해당하는 태그가 하나일 경우 선택
</pre>
<pre>
- 태그의 상태에 따라서 선택하기 ( 선택자 다음 : ) -
:header            : h1 ~ h6 태그를 선택
:focus             : 현재 포커스가 주어진 태그를 선택
:contains(문자열)  : 지정된 문자열이 포함된 태그를 선택
:has(선택자)       : 지정된 선택자를 포함하고 있는 태그를 선택
</pre>
<pre>
- 인덱스 번째 태그 선택하기 ( 선택자 다음 : ) -
:eq(index)                 : 인덱스(0부터 시작) 번째 해당하는 태그를 선택
:nth-child(index)          : 각 영역의 인덱스(1부터 시작) 번째 해당하는 태그를 선택. 인덱스 번째 해당하는 태그가 선택자에 없으면 선택되지 않음
:nth-of-type(index)        : 각 영역의 인덱스(1부터 시작) 번째 해당하는 태그를 선택.
:gt(인덱스)                 : 선택자에 해당하는 태그 중 인덱스(0부터 시작) 번째 태그 이후의 태그들이 선택
:lt(인덱스)                 : 선택자에 해당하는 태그 중 인덱스(0부터 시작) 번째 태그 이전의 태그들이 선택
:nth-last-child(인덱스)     : 뒤에서 인덱스(1부터 시작) 번째 까지 태그가 선택된다. 선택자와 다르면 선택되지 않는다.
:nth-last-of-type(인덱스)   : 뒤에서 인덱스(1부터 시작) 번째 까지 태그가 선택된다.

:not(선택자)                : 선택자에 해당하지 않는 태그들을 선택
</pre>
<pre>
- form 선택 -

:input       : input태그 선택
:text        : type 속성이 text인 input태그를 선택
:password    : type 속성이 password인 input태그를 선택
:radio       : type 속성이 radio인 input태그를 선택
:checkbox    : type 속성이 checkbox인 input태그를 선택
:submit      : type 속성이 submit인 input태그를 선택
:reset       : type 속성이 reset인 input태그를 선택
:button      : type 속성이 button인 input태그를 선택
:image       : type 속성이 image인 input태그를 선택
:file        : type 속성이 file인 input태그를 선택
:enabled     : 활성화된 input 태그 선택
:disabled    : 비활성화된 input 태그 선택
:selected    : select 태그 내 option 태그 중 선택된 태그를 선택
:checked     : checkbox 또는 radio 태그에서 현재 checked 된 태그를 선택
</pre>
# jQuery 이벤트
<pre>
- 이벤트 (소문자로만 셋팅(대문자 안됨)) -

click       : 클릭하고 뗏을 때
dblclick    : 더블클릭
mouseenter  : 마우스 커서가 들어왔을 때
mouseleave  : 마우스 커서가 나갔을 때
mousedown   : 마우스를 클릭 했을 때
mouseup     : 마우스를 똇 했을 때
hover       : 마우스 커서가 들어 왔을 때, 커서가 나갔을 때
focus       : 포커스가 들어왔을 때
blur        : 포커스가 나갔을 때
on          : 이벤트를 설정하는 함수
off         : 설정된 이벤트를 제거
one         : 이벤트를 설정하고 이벤트 발생 후에 자동으로 제거
</pre>
<pre>
- DOM -
after     : html 코드나 태그를 태그 다음에 삽입한다.
before    : html 코드나 태그를 태그 앞에 삽입한다.
append    : html 코드나 태그를 태그 내부의 뒤에 삽입
prepend   : html 코드나 태그를 태그 내부의 앞에 삽입
attr()    : 태그의 속성을 제어
prop()    : 태그의 속성을 제어
html()    : 태그 내부의 html 코드를 제어
remove    : 태그를 제거한다.
empty     : 태그 내의 모든 태그를 제거한다.
text()    : 문서 태그 사이의 문자를 제어
val()     : input 태그의 value 속성을 제어
</pre>
<pre>
animate : 지정된 css 속성을 애니메이션 효과를 지정한다.
</pre>
