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

연산자		
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
https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadingElement  
console.dir(document)  
dir의 object에서 on이 붙은 것들은 event이다.   
모든 event는 js가 listen이 가능하다.   

---

HTML element를 가져와서, addEventListener function을 실행("이벤트", 펑션)  
title.addEventListener("click", handleTitleClick); 괄호를 넣지 않는다.  

```javaScript
const title = document.querySelector(".hello h1");

function handleTitleClick() {
    title.style.color = "blue";
}

```