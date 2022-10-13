# JavaScript

리액트 네이티브 = 안드로이드 IOS 앱을 만들 수 있게 해준다.    
일렉트론 = HTML CSS 자바스크립트로 VScode, 트위치,페북 등을 만들수 있다.   
이제는 자바스크립트로 백앤드도 가능하다.    

VScode에서 다중선택    
Ctrl + Shift + L    

---

HTML에서 CSS와 JavaScript를 가져와서 사용한다.      

CSS는 헤드쪽에  
```javaScript
<link rel="stylesheet" href="style.css">     
```
JavaScript는   
```javaScript
<script src="script.js"> </script>   
```
---

변수값의 암묵적인 규칙 공백   
very_long_variable_name(뱀모양, 파이썬)    
veryLongVariableName(낙타모양, 자바)   


# 변수(variable)의 종류     
처음에는 var로 통일 되었었다. 하지만 업데이트를 통해 let과 const가 탄생      
var는 어떠한 규칙도 가지고 있지 않는 변수이다.      
업데이트가 허용 되어야 하는 변수의 경우 let을 사용      
바뀌지 않는 상수 값을 적용해야 하는 변수의 경우 const를 활용     

let 재선언 금지, 재할당 가능      
const 재선언 금지, 재할당 금지      
var 재선언 가능, 재할당 가능      

---
```javaScript
const 변수명 = null;   
let 변수명2;   

console.log(변수명);   
console.log(변수명2);    

null :  "비어있음"를 의도적으로 표현한 것    
undefined : 변수가 메모리에 존재하지만 값이 정의되지 않음    
NaN (Not a Number) : 숫자가 아님     

두가지의 변수 보기 (, 콤마 이용)    
console.log(변수명, 변수명2);   
```
true (1), false (0)    

파이썬에서는 None,True,False로 표현    

---


# Arrays(배열) 설정   
```javaScript
const 변수명 = [값1, 값2, 값3];   

배열의 index를 찾아 확인 방법   
console.log(변수명[0]);    

기존 배열에 항목 추가    
변수명.push(값);     
```
---


# object(오브젝트) 설정   
```javaScript
const objectName = {    
    속성1: "값",   
    속성2: 0,   
    속성3: true,    
};    

오브젝트안의 속성을 찾아 확인 방법   
console.log(objectName.속성1);    
console.log(objectName["속성1"]);   

오브젝트안에 속성 추가 및 수정   

추가    
objectName.속성명 = "값";   

수정    
objectName.속성2 = objectName.속성2 + 10;   
objectName.속성3 = false;   
```
*constant는 바꿀 수 없는게 아닌가?*    
const로 지정된 오브젝트 안의 무언가를 업데이트 할 때는 문제없지만   
objectName(박스)자체를 바꾸려 하면 오류     

---


# function(함수)

function은 코드를 캡슐화해서, 실행을 여러 번 할 수 있게 해준다. (메서드)     
```javaScript
사용방법      
function 함수명(a, b) {      
	console.log("firstNumber = " + a + ", secondNumber = " + b);    
}   

함수명(1, 2);    
함수명 뒤의 괄호 안의 변수들이 function의 함수명 뒤의 변수들로 차례대로 들어간다.   

const 변수명 = {   
    name: "Kim",    
    hello: function(otherPersonsName) {   
        console.log("hello " + otherPersonsName);   
    },    
}   

변수명.hello("Dongju");    
식으로 응용도 가능    
```

---

prompt()   

두가지의 파라미터를 받는다.   
하나는 (message)문자, 다른 하나는 default   
사용자 들에게 값을 가져올 때 썼다고 하지만 매우 오래된 방법이라고 한다.   
prompt를 안쓰는 이유 : message가 별로 안예쁨, css를 적용할 수 없다.   
	
---

연산자 정리  

typeof 값 = 타입을 보는 방법  
parseInt("15"); = 스트링 타입을 인트 타입으로 바꿔준다.  
isNaN(); = 인트 타입인지 아닌지 알려준다. 인트를 넣으면 false  
||(OR) &&(AND)   
== 동등연산자, 값만 같으면 true   
=== 일치연산자, 값과 타입이 모두 같으면 true   

---


# Document

모든 것들은 document로 부터 시작한다.   
Console에 document를 치면 html을 보여준다. 
```javaScript
console.dir(document)로 html의 정보들을 자바스크립트로 가져올 수 있다. *(object형식) 
```
즉 JavaScript는 HTML에 이미 연결되어 있다.   

element.innerText;   
이 속성은 element 안의 text 값들만을 가져옵니다.   

element.innerHTML;   
innerText와는 달리 innerHTML은 element 안의 HTML이나 XML을 가져옵니다.   

---

```javaScript
getElementById : (하나의 element를 가져올때 쓴다)  
const id = document.getElementById("ID");   

getElementsByClassName : (많은 element를 가져올때 쓴다(array를 반환))   
const className = document.getElementsByClassName("className");   

getElementsByTagName : (타입을 이용하여 element를 가져올때 쓴다(array를 반환))   
const tag = document.getElementsByTagName("h1");   

---

querySelector : CSS selector방식으로 element를 가져올 수 있다. (단 하나의 첫번째 element를 return 해준다)   
const title = document.querySelector(".hello h1");

querySelectorAll : 모든 element를 가져오고 싶은 경우(array를 반환)   
const titleAll = document.querySelectorAll(".hello h1");

---  

querySelector와 getElementById의 차이점 (하위요소 가져오는 유무)
const title = document.querySelector("#hello form");
const title = document.getElementById("hello");
```

---


# Event  
listen하고 싶은 event를 찾는 가장 좋은 방법 https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadingElement  

console.dir(document)  
dir의 object에서 on이 붙은 것들은 event이다.   
모든 event는 js가 listen이 가능하다.   

event를 사용하는 데에는 두가지 방법이 있다.  

---

방법1 

>HTML element를 가져와서, addEventListener function을 실행("이벤트", 펑션)  
>```javaScript
>title.addEventListener("click", handleTitleClick); 괄호를 넣지 않는다  
>
>const title = document.querySelector(".hello h1");
>
>function handleTitleClick() {
>    title.style.color = "blue";
>}
>
>```

방법2

>```javaScript
>title.onclick = handlehandleTitleClick;
>
>const title = document.querySelector(".hello h1");
>
>function handleTitleClick() {
>    title.style.color = "blue";
>}
>```
>onclick와 addEventListener의 차이점  
>addEventListene를 쓰면 removeEventListener를 통해서 event listener를 제거 가능하다.  

---

Window

```javaScript
window.addEventListener("copy", handleWindowCopy);

function handleWindowCopy() {
    alert("copier!");
}
```
document에서 body,head,title 은 중요해서 언제든  
ex) document.body 로 가져올수있지만  
div나 h1 등 element 들은 querySelector getElementById등으로 찾아야한다.  
ex) document.querySelector(“h1”);  

---


# toggle

toggle이란?  
토큰이 존재한다면 토큰을 제거, 존재하지 않는다면 토큰을 추가한다.  

---

>HTML에서는 이런 문장이 있다고 하고  
>```HTML
><h1>click me!</h1>
>```
>CSS에서는 이런 문장이 있다고 하자.  
>```CSS
>.clicked {
>    color: tomato;
>}
>```
>그러면 자바스크립트에서  
>```javaScript
>function handleTitleClick() {
>    const clickedClass = "clicked";
>    if(h1.classList.contains(clickedClass)) {
>        h1.classList.remove(clickedClass);
>    } else {
>    h1.classList.add(clickedClass);
>    }
>}
>
>h1.addEventListener("click", handleTitleClick);
>```
>이렇게 구현할 수 있다. 
>
>classList : 우리가 class들의 목록으로 작업할 수 있게끔 허용해준다. 
>contains() : class가 HTML element의 class에 포함되어 있는지 여부  
>remove() : 제거  
>add() : 추가  

---

toggle을 쓴다면 한문장으로 정리 가능하다.   
```javaScript
function handleTitleClick() {
    h1.classList.toggle("clicked");
}

h1.addEventListener("click", handleTitleClick);
```

---

preventDefault (브라우저가 기본 동작을 실행하지 못하게 막기)  
preventDefault함수를 기본적으로 갖고 있음  

# 템플릿 리터널

```javaScript
"Hello" + username; ===`Hello${username}`;  
```
벡터( ` )표시와 달러( $ )표시를 이용하면 된다.  

---

# 로컬 스토리지

local storage는 browser에서 제공하는 DB로 key:value로 데이터를 저장한다.  
보는 방법은 f12(검사)->application쪽에 있다.  
localstorage.setItem(,)  
localstorage.getItem()  
localstorage.removeItem()  

# interval
시간적인 간격, 두가지의 아규먼트를 받는다.

---
setInterval(실행할 함수, 실행할 함수의 주기/ms)
```javaScript
function interval_TEST() {
	console.log("hello");
}
setInterval(interval_TEST, 5000);
```
5초 주기로 interval_TEST의 함수가 실행된다.

---

반복이 아닌 한번만 실행하고 싶을 경우  
setTimeout(실행할 함수, 실행할 함수의 주기/ms)을 쓰면 된다.

# Date
```javaScript
function getClock() {
    const date = new Date();
    clock.innerText = `${date.getHours()}:${date.getMinutes()}:${date.getSeconds()}`;
}

getClock();
setInterval(getClock, 1000);
```

# padStart, padEnd
스트링에 쓸 수 있는 펑션  
"문자열".padStart(문자열길이, "문자열길이가 아닐경우 앞쪽에 추가할 문자")  
"문자열".padEnd(문자열길이, "문자열길이가 아닐경우 뒤쪽에 추가할 문자")  

Date쪽의 코딩으로 시계를 만들면 01:20:03식으로 표현되지 않고 1:20:3으로 표현될 것이다.  
이것을 두자리의 문자열로 깔끔하게 만들기 위해서 padStart나 padEnd를 쓰면 쉽게 가능하다.  

```javaScript
function getClock() {
    const date = new Date();
    const hours = String(date.getHours()).padStart(2, "0");
    const minutes = String(date.getMinutes()).padStart(2, "0");
    const seconds = String(date.getSeconds()).padStart(2, "0");

    clock.innerText = `${hours}:${minutes}:${seconds}`;
}

getClock();
setInterval(getClock, 1000);
```

# random

Math.random() 랜덤함수  
Math.round() 반올림  
Math.ceil() 올림  
Math.floor() 내림  

ex)
```javaScript
10개의 객체가 들어있는 배열같은 경우는 Math.floor(Math.random()*10)의 방식으로 쓴다.
```
위의 방식은 배열이 추가될때마다 숫자를 바꿔줘야하니 배열명.length를 쓰는것이 좋다.

---

정리
```javaScript
const array_list = [
	{
		hello: "hello",
		javaScript: "javaScript"
	},
	{
		hello2:"hello2",
		javaScript2:"javaScript2"
	},
];
console.log(Math.floor(Math.random()*array_list.length));
```

# 자바스크립트에서 HTML 코드 만들기

document.createElement(" ") 요소 추가  
document.body.appenChild( ) 바디 맨뒤 추가  
document.body.prepend( ) 바디 맨앞 추가  
document.body.insertBefore(삽입할 노드, 기준이 될 노드) 기준이 되는 노드 앞에 추가  

---
```javaScript
const hello = document.createElement( "h1" )
// <h1></h1> 코드 생성
```
```javaScript
hello.innerHTML = "hello";
// hello안에 텍스트 추가
```
```javaScript
document.body.appendChild(hello);
// <h1>태그 코드를 가진 hello라는 변수가 body태그 내부 맨 끝에 생성된다.
```
---
참고로 console.dir(hello);로 여러 속성들을 확인 후 추가할 수도 있다.  
ex)  
```javaScript
hello.classList.add("addClassName");
```

# 배운것들 총 정리

input[type="text"]에 타이핑 후 엔터를 치면 JavaScript에 있는 toDoForm.addEventListener("submit", handleToDoSubmit);에 의해서 handleToDoSubmit으로 간다.  

HTML
```html
<form id="todo-form">
   <input type="text" placeholder="Write a To Do and Press" required />
</form>
<ul id="todo-list"></ul>
```

JavaScript
```javaScript
const toDoForm = document.getElementById("todo-form");
const toDoInput = document.querySelector("#todo-form input");
const toDoList = document.getElementById("todo-list");

let toDos = [];

function paintToDo(newTodo) {
    const li = document.createElement("li");
    const span = document.createElement("span");
    const button = document.createElement("button");

    // li의 고유번호 부여
    li.id = newTodo.id;
    
    // li안에 <span></span> 생성
    li.appendChild(span);
    
    // span안에 input에 쓴 newTodo.text 넣기
    span.innerHTML = newTodo.text;

    // 버튼생성
    button.innerHTML = "Delete";
    
    // 버튼 누를시 deleteButton펑션 이동
    button.addEventListener("click", deleteButton);

    // li에 버튼 생성
    li.appendChild(button);
    
    // 만들어진 li를 뷰에 생성
    toDoList.appendChild(li);
}

// 버튼 누를시 삭제
function deleteButton(event) {
    // 버튼의 부모를 찾고 그것을 li변수에 저장
    const li = event.target.parentElement;
    // 버튼의 부모 삭제(li)
    li.remove(); 
    // 로컬스토리지 id와 버튼의 id를 비교하여 필터링 후 toDos(배열)에 저장 [필터는 True만 리턴한다.]
    toDos = toDos.filter((toDo) => toDo.id !== parseInt(li.id));
    // 로컬스토리지에 저장
    saveToDos(); 
}

// 로컬스토리지에 저장
function saveToDos() {
    localStorage.setItem("todos",JSON.stringify(toDos));
}

// 메인 펑션
function handleToDoSubmit(event) {
    // 이벤트 막기
    event.preventDefault();
    // 인풋타입에 쓴 value를 newTodo에 저장
    const newTodo = toDoInput.value;
    // HTML의 인풋타입에 쓴 value를 초기화
    toDoInput.value = "";
    // 오브젝트 생성(인풋타입에 쓴 value, 랜덤숫자)
    const newTodoObj = {
        text:newTodo,
        id: Date.now()
    }
    // toDos(배열)에 newTodoObj(오브젝트) push
    toDos.push(newTodoObj);
    // HTML에 li, span(newTodo.text), button생성
    paintToDo(newTodoObj);
    // 로컬스토리지에 저장
    saveToDos();
}
toDoForm.addEventListener("submit", handleToDoSubmit);


// 로컬스토리지 확인 및 배열 
const savedToDos = localStorage.getItem("todos");
if(savedToDos !== null) {
    const parsedToDos = JSON.parse(savedToDos);
    toDos = parsedToDos;
    parsedToDos.forEach(paintToDo);
}
```

### localStorage.setItem("todos",toDos); 가 아닌 JSON.stringify를 쓰는 이유
localStorage는 단순 텍스트로만 저장되기 때문에 JSON.stringify로 array처럼 생긴 string으로 저장한다.  
이유는 JSON.parse()를 통해 string data type을 array로 바꿀 수 있기에 인덱스 값을 이용해 value를 가져올 수 있다.  

```javaScript
const savedToDos = localStorage.getItem("todos");

if(savedToDos !== null) {
    const parsedToDos = JSON.parse(savedToDos);
    toDos = parsedToDos;
    parsedToDos.forEach(paintToDo);
}
```
### 포이치를 쓰는 두가지 방법  
```javaScript
기존방법
parsedToDos.forEach(HelloFE);
function HelloFE(item) {
    console.log(item);
}

새로운방법
parsedToDos.forEach((item) => console.log(item)); 
```
위의 두 가지는 동일하다.  
새로운 방법의 item이름명은 임의지정하면 된다.

### 필터
```javaScript
const hello = [{text:"lalala"}, {text:"lelele"}, {text:"lololo"}];

(방법1)
function superFilter(item) { return item.text !== "lelele" };
hello.filter(superFilter);

(방법2)
hello.filter((item) => item.text !== "lelele");

리턴값이 true인 text:"lalala"와 text:"lololo"가 남게된다.
```

단, hello의 값이 삭제되는 것은 아니다.  
console.log(hello)를 해 보면 그대로 남아있다.  
저 필터링 한 값을 다른 변수에 넣거나 덮어쓰는 방식으로 쓸 수 있다.  

---

# navigator 함수를 이용해 사용자의 위치를 알아내는 코드 작성.

navigator.geolocation.getCurrentPosition ( ) 라는 코드를 작성해준다.  
이때 getCurrentPosition 은 2개의 argument가 필요하다. 앞쪽에는 True일때 실행될 함수를, 뒤에는 false일때 실행될 함수를 입력한다.  

```javaScript
true 함수가 실행될 때
function true(position){
const lat = position.coords.latitude;
const lon = position.coords.longitude;
console.log("You live in", lat, lon);
}
```
자바스크립트가 position으로 user의 위치를 전달해준다.  
position은 object 이고 위도와 경도 값이 들어있다.  
positon.coords.latitude와 position.coords.longitude 를 변수에 저장하고 보여줄 수 있다.  

---

# Weather API
날씨 API 사이트 및 doc [https://openweathermap.org/current]  
API : 다른 서버와 이야기를 할 수 있는 방법  
구글 확장 앱 : [JSONView](https://chrome.google.com/webstore/detail/jsonview/gmegofmjomhknnokphhckolhcffdaihd/related?hl=ko)  

```javaScript
const weather_url = `https://api.openweathermap.org/data/2.5/weather?lat=${lat}&lon=${lon}&appid=${API_key}`;
이 URL에 자신의 위도와 경도, API를 넣어준다. (벡틱을 사용하면 보기 편하다)
들어가 보면 여러 정보를 볼 수 있다.

[HTML에 가져가기]
fetch(weather_url)
    .then(response => response.json())
    .then(data => {
        const weather = document.querySelector("#weather span:first-child");
        const city = document.querySelector("#weather span:last-child");
        city.innerText = data.name;
        weather.innerText = `${data.weather[0].main} / ${data.main.temp}`;
    });
```
[fetch함수(Promise)]  
fetch() 함수는 첫번째 인자로 URL, 두번째 인자로 옵션 객체를 받고, Promise 타입의 객체를 반환한다.  
반환된 객체는, API 호출이 성공했을 경우에는 응답(response) 객체를 resolve하고, 실패했을 경우에는 예외(error) 객체를 reject한다고 한다.  
```javaScript
fetch(url, options)
  .then((response) => console.log("response:", response))
  .catch((error) => console.log("error:", error));
```

Promise란?  
자바스크립트 비동기 처리에 사용되는 객체, 주로 서버에서 받아온 데이터를 화면에 표시할 때 사용  
당장 뭔가 일어나지 않고 시간이 좀 걸린 뒤에 일어난다.  
서버에 무언가를 물어 봤는데 응답하는 데 5분 걸린다고 하면 응답을 기다려야 한다.  
그래서 URL을 fetch하고 그 다음으로 response를 받아야 한다.  
then : promise 가 종료가 되면 resolve 에 들어간 값을 받을 수 있다.  
catch : reject 된 경우에는 then 으로 받을 경우, 에러가 발생한다, 이 때 catch 를 사용하여 에러를 잡아줄 수 있다.  
