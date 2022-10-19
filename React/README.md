# React
Meta에서 개발한 오픈 소스 자바스크립트 라이브러리이다.  
2022-10-16일 기준 버전은 18.2.0이 나와있으며 react-dom은 17버전까지 지원한다.  
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

위의 React.createElement를 쓰는 예시
```javaScript
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);
```
JSX
```javaScript
const element = (
  <h1 className="greeting">
    Hello, world!
  </h1>
);
```
JSX이 훨씬 익숙하고 간편하다.

그래서 JSX를 쓰기위해서는 React.createElement의 문법으로 변환해주는 변환기를 설치해야 한다.  

---

### Babel standalone
https://unpkg.com/@babel/standalone/babel.min.js  
자바스크립트 src에 정의해주고
함수나 변수를 쓸 스크립트를 <script type="text/babel">로 바꿔준다.
