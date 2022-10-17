# 1. JDK
1.1 오라클 홈페이지에서 JDK 설치 
---
https://www.oracle.com/kr/java/technologies/downloads/#java8-windows
![JDK설치](https://user-images.githubusercontent.com/93306929/196065775-64b8d801-1e5e-4e8e-bbac-e9ee8ccb36b5.png)

1.2 환경변수 설정
---
![환경변수](https://user-images.githubusercontent.com/93306929/196065781-1c6a9a4b-d8df-4870-a9d2-e355b0ec6624.png)

![환경변수2](https://user-images.githubusercontent.com/93306929/196065783-e8a44c96-e341-4f83-b2c0-90a55951c28f.png)

1.3 Path편집
---
새로 만들기 %JAVA_HOME%\bin;  
![환경변수3](https://user-images.githubusercontent.com/93306929/196065864-abea496e-66ec-4690-86ca-340715cf34d8.png)

1.4 확인해보기
---
CMD 창에서 java -version  
![굳](https://user-images.githubusercontent.com/93306929/196066009-552aba9f-986c-49d1-a73f-90d2dacbcb23.png)

---

# 2. 이클립스
2.1 이클립스 홈페이지에서 설치
---
https://www.eclipse.org/downloads/  
![이클립스](https://user-images.githubusercontent.com/93306929/196066239-fd780a28-3616-4d39-87e5-e9d8245ab162.png)

2.2 이클립스 IDE설치
---
![이클2](https://user-images.githubusercontent.com/93306929/196066682-bcbbe3f7-3984-4d6a-a0db-a5a38cb461b9.png)

---

# 3. STS
3.1 스프링 홈페이지에서 설치 (반디집 이용)
---
https://spring.io/tools  
![스프링](https://user-images.githubusercontent.com/93306929/196066506-74254f9f-623d-41c0-80c7-8b3ef74e26f3.png)

3.2 Spring Legacy Project
---
STS 4부터는 SPRING Boot만을 지원하기 때문에 JSP를 지원하지 않고  
아직 현업에서 많이 사용되는 Spring Legacy Project를 생성할 수 없기 때문에 추가 설치가 필요하다.  
![뉴 소프트웨어](https://user-images.githubusercontent.com/93306929/196067436-b1fe0b97-92a5-4f40-afbb-53990a209462.png)
![뉴 소프트웨어2](https://user-images.githubusercontent.com/93306929/196067445-4110a8eb-1cbf-4f60-9d99-813d891aa647.png)

[Windows] > [Preferences] > [Web] 탭이 생기게 된다.

3.2.1 Spring Tools 3 Add-On 설치
---
마켓  
![마켓1](https://user-images.githubusercontent.com/93306929/196067753-601adf7c-c7c2-4f0f-9762-32a5f2ecf92e.png)  

add-on설치  
![마켓2](https://user-images.githubusercontent.com/93306929/196067765-4484252d-1251-473a-855b-2340be795c3c.png)  

3.3 초기 셋팅

JDK 설정
Window -> preferences -> java -> installed JREs -> JDK 경로 설정
톰캣 설정
Window -> preferences -> Server -> Runtime Environments -> 아파치 톰캣 설정 (아파치 홈페이지에서 9버전 이상 다운받기)
UTF-8 설정
Window -> preferences -> web -> html,css,jsp (UTF-8)
웹 브라우저 설정
Window -> preferences -> General -> Web Browser -> Chrome
