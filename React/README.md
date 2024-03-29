# React
Meta에서 개발한 오픈 소스 자바스크립트 라이브러리이다.  
2022-10-16일 기준 버전은 18.2.0이 나와있으며 react-dom은 17버전까지 지원한다.  
react-dom 대신 createRoot를 사용하게 된다.
버전 번호는 x.y.z 형태로, 치명적인 버그를 수정할 때는 z 번호를 바꾸고,  
새로운 기능을 출시하거나 치명적이지 않은 버그를 수정할 때는 y 번호를 바꾸고,  
호환성이 유지되지 않는 변경이 있을 때는 x 번호를 바꾸어 배포한다고 한다.  

CDN추가 react, react-dom  
> https://ko.reactjs.org/docs/add-react-to-a-website.html#gatsby-focus-wrapper  
React JS - 어플리케이션이 인터랙티브하도록 만들어주는 library. 엔진과 같다.  
React-dom - library 또는 package. 모든 react element들을 HTML body에 둘 수 있도록 해줌.  

---

### React.createElement(div, props, child)  
1. 여러 props를 넣을 경우 {}로 감싸서 넣는다.
2. 여러 child를 넣을 경우 []로 감싸서 넣는다.
3. eventListener를 넣고 싶은 경우 
```javaScript
props에 onClick: () => console.log("I'm clicked")
```
의 형식으로 넣는다. 단, event값 앞에 on <-을 넣어줘야 ReactJS에서 알아듣는다.  

---

### ReactDOM.render(보낼 변수, HTML의 위치)  
ReactDOM.render() - react element를 가지고 HTML로 만들어 배치한다는 것. 즉, 사용자에게 보여준다는 의미  

# JSX
자바스크립트를 확장한 문법,보통의 HTML과 비슷하다.  

>위의 React.createElement를 쓰는 예시
>```javaScript
>const element = React.createElement(
>  'h1',
>  {className: 'greeting'},
>  'Hello, world!'
>);
>```
>JSX
>```javaScript
>const element = (
>  <h1 className="greeting">
>    Hello, world!
>  </h1>
>);
>```
>
JSX로 표현하는것이 훨씬 익숙하고 간편하다.

단, JSX를 쓰기위해서는 React.createElement의 문법으로 변환해주는 변환기를 설치해야 한다.  

---

### Babel standalone
https://unpkg.com/@babel/standalone/babel.min.js (JSX로 적은 코드를 브라우저가 이해할 수 있는 형태로 바꿔준다)  
자바스크립트 src에 정의해주고 함수나 변수를 쓸 스크립트를 <script type="text/babel">로 바꿔준다.

---

### 규칙

1. 직접 만든 컴포넌트의 첫 글자는 반드시 대문자여야 한다.
2. 소문자면 React랑 JSX는 HTML 태그라고 인식한다.
3. 직접 만든 컴포넌트들은 전부 함수로 만들어 줘야 한다.

Ex)
```javaScript
1. div의 id를 가져오기
const root = document.getElementById("root");

2-1. 일반적인 함수(Function)
function Title() {
  return (
    <h3 id="title" onMouseEnter={() => console.log("mouse enter")}>
    Hello i'm a title
    </h3>
  );
}

2-2. 화살표 함수(ArrowFunction)
const Button = () => (
  <button 
    style={{
    backgroundColor: "tomato",
    }}
    onClick={() => console.log("im clicked")}
  >
    Click me
  </button>
);

3. 만들어진 컴포넌트를 다른 컴포넌트 안에 넣는 방법
const Container = () => (
  <div>
    <Title/>
    <Button/>
  </div>
);

4. render를 통해 html으로 보내기
ReactDOM.render(<Container/>, root);
```
점점 보기 편리해지고 있다.
  
---

# 리 렌더링
방식에는 여러 방법이 있다.  
무식한 방법으로는 아래의 예제가 있다.  
```HTML
<body>
    <div id="root"></div>
</body>
```
```JavaScript
<script src="https://unpkg.com/react@17.0.2/umd/react.production.min.js" crossorigin></script>
<script src="https://unpkg.com/react-dom@17.0.2/umd/react-dom.production.min.js" crossorigin></script>
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>

<script type="text/babel">     
  //div id를 가져옴
  const root = document.getElementById("root");
  let counter = 0;

  function countUp() {
    counter = counter +1;
      render();
    }

  function render() {
    ReactDOM.render(<Container/>, root);
  }

  const Container = () => (
    <div>
      <h3>Total clicks: {counter}</h3>
      <button onClick={countUp}>Click me</button>
    </div>
  );

  // render로 html으로 보냄
  render();
</script>
```
이 방법은 HTML페이지를 렌더링 할때 계속적으로 함수를 이용하여 렌더링 해줘야한다.  
하나의 함수라면 괜찮겠지만 많은 함수들을 렌더링 한다면 render();와 같은 함수를 줄줄히 적어줘야 한다.  

---

### React.useState
```javaScript
const [data, modifier] = React.useState();
```
useState는 배열을 하나 준다. [data, data값을 바꿀때 사용할 function]  
modifier 함수는 값을 하나 받는데 그 값으로 업데이트하고 리렌더링을 해준다.  
즉, ReactDOM.render를 계속해서 함수쪽에 정의해주지 않아도 렌더링을 할 수 있다.  
