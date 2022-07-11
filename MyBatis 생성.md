DAO란 Data Access Object의 약어로서 실질적으로 DB에 접근하는 객체를 말한다.
알기쉽게 말하면 DAO는 DB를 사용해 데이터를 조회하고 조작하는 기능을 전담한다.
DAO의 사용 이유는 효율적인 커넥션 관리와 보안성 때문이다.

DB에 대한 접근을 DAO가 담당하도록 하여 데이터베이스 엑세스를 DAO에서만
하게 되면 다수의 원격호출을 통한 오버헤드를 VO나 DTO를 통해 줄일 수 있고
다수의 DB호출문제를 해결할 수 있다. 단순히 읽기만 하는 연산이라 트렌젝션
간의 오버헤드를 감소할 수 있다.

DTO(Data Transfer Object)는 VO(Value Object)로 바꿔 말할 수 있는데
간단하게 컨트롤러, 뷰, 비즈니스 계층, 퍼시스턴스 계층을 말하고 각 계층간의
데이터 교환을 위한 객체이다.

<img src="https://user-images.githubusercontent.com/93306929/178177268-4fbd4294-3091-493a-b44d-e1a223363b2f.png" width="250" height="300"/>

MVC : Model(M),View(V),Controller(C)
순서 C->M->V

UI = View
manager = Controller 및 Medel
VO = 값을 저장하고 있는 클래스 (Person,Student)

M은 데이터와 관련된 처리를 하는 클래스를 별도로 만듦 (DAO : Data Access Object)

<img src="https://user-images.githubusercontent.com/93306929/178178336-6c58fd5e-29d7-412a-8715-f569a740ab16.png" width="500" height="500"/>


JDBC란 자바에서 데이터베이스에 접속할 수 있도록 하는 자바 API
편의성을 위해 Mybatis라는 FrameWork를 쓴다.
FrameWork는 간단하게 복잡한 절차를 간소화 해서 문제를 쉽게 해결하기 위해 만들어진 것.
