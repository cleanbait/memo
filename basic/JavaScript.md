# JavaScript

리액트 네이티브 = 안드로이드 IOS 앱을 만들 수 있게 해준다.    
일렉트론 = HTML CSS 자바스크립트로 VScode, 트위치,페북 등을 만들수 있다.   
이제는 자바스크립트로 백앤드도 가능하다.    

VScode에서 다중선택    
Ctrl + Shift + L    

---

HTML에서 CSS와 JavaScript를 가져와서 사용한다.      

CSS는 헤드쪽에     
link rel="stylesheet" href="style.css"     

JavaScript는     
script src="script.js" /script   

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

const 변수명 = null;   
let 변수명2;   

console.log(변수명);   
console.log(변수명2);    

null :  "비어있음"를 의도적으로 표현한 것    
undefined : 변수가 메모리에 존재하지만 값이 정의되지 않음    
NaN (Not a Number) : 숫자가 아님     

두가지의 변수 보기 (, 콤마 이용)    
console.log(변수명, 변수명2);   

true (1), false (0)    

파이썬에서는 None,True,False로 표현    

---

# Arrays(배열) 설정   
const 변수명 = [값1, 값2, 값3];   

배열의 index를 찾아 확인 방법   
console.log(변수명[0]);    

기존 배열에 항목 추가    
변수명.push(값);     

---

# object(오브젝트) 설정   
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

*constant는 바꿀 수 없는게 아닌가?    
const로 지정된 오브젝트 안의 무언가를 업데이트 할 때는 문제없지만   
objectName(박스)자체를 바꾸려 하면 오류     

---

# function(함수)

function은 코드를 캡슐화해서, 실행을 여러 번 할 수 있게 해준다. (메서드)     

사용방법      
function 함수명(a, b) {      
	console.log("firstNumber = " + a + ", secondNumber = " + b);    
}   

함수명(1, 2);    
*함수명 뒤의 괄호 안의 변수들이 function의 함수명 뒤의 변수들로 차례대로 들어간다.   

const 변수명 = {   
    name: "Kim",    
    hello: function(otherPersonsName) {   
        console.log("hello " + otherPersonsName);   
    },    
}   

변수명.hello("Dongju");    

식으로 응용도 가능    

---

2.9부터 
