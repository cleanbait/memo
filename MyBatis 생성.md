DAO란 Data Access Object의 약어로서 실질적으로 DB에 접근하는 객체를 말한다.   
알기쉽게 말하면 DAO는 DB를 사용해 데이터를 조회하고 조작하는 기능을 전담한다.   
DAO의 사용 이유는 효율적인 커넥션 관리와 보안성 때문이다.   

DB에 대한 접근을 DAO가 담당하도록 하여 데이터베이스 엑세스를 DAO에서만
하게 되면,   
다수의 원격호출을 통한 오버헤드를 VO나 DTO를 통해 줄일 수 있고 다수의 DB호출문제를 해결할 수 있다.    
단순히 읽기만 하는 연산이라 트렌젝션간의 오버헤드를 감소할 수 있다.

DTO(Data Transfer Object)는 VO(Value Object)로 바꿔 말할 수 있는데   
간단하게 컨트롤러, 뷰, 비즈니스 계층, 퍼시스턴스 계층을 말하고 각 계층간의
데이터 교환을 위한 객체이다.

<img src="https://user-images.githubusercontent.com/93306929/178177268-4fbd4294-3091-493a-b44d-e1a223363b2f.png" width="250" height="300"/>

MVC : Model(M),View(V),Controller(C)
순서 C->M->V

View = UI   
Controller 및 Medel = manager   
값을 저장하고 있는 클래스 (Person,Student) = VO이용      

M은 데이터와 관련된 처리를 하는 클래스를 별도로 만듦 (DAO : Data Access Object)

<img src="https://user-images.githubusercontent.com/93306929/178178336-6c58fd5e-29d7-412a-8715-f569a740ab16.png" width="700" height="500"/>


JDBC란 자바에서 데이터베이스에 접속할 수 있도록 하는 자바 API
편의성을 위해 Mybatis라는 FrameWork를 쓴다.
FrameWork는 간단하게 복잡한 절차를 간소화 해서 문제를 쉽게 해결하기 위해 만들어진 것.

1. processing to run once는 딱 한번만 실행
2. processing to run per requests는 요청이 있을때마다 실행
이중에 한번만 실행 하는게 공용자원(Static) 1번

1번쪽에 Factory Builder(1)가 있다.   
여기서 SqlSession Factory(3)라는 Static한 공용자원을 만듦   
이것을 가지고 SqlSession(10)을 만들고 여기에 매핑된 Mapper interface(6)를 통해 SQL명령이 기록되어 있는 MapperXML(11)파일에 접근   
그 후 그 결과를 Controller(C)한테 돌려주는것이 Mybatis의 구성   
이것을 V한테 넘겨주고 사용자한테 보여줌   

<img src="https://user-images.githubusercontent.com/93306929/178179523-10a60fe0-19d8-4dba-90a0-6087a280a470.PNG"/>
1. Mybatis를 수동으로 설치하기 위해서 그림에 있는 'mybatis-xxx.jar' 파일을 다운로드

<img src="https://user-images.githubusercontent.com/93306929/178179620-4d38dd15-9cd2-429c-b2f8-4f16c3bfe94c.PNG"/>
2. c드라이브에 oracleexe->product->'jdbc6' 이것이랑 다운받은것 안의 'mybatis-3.5.7.jar' 이 두개를 java Build Path 라이브러리에 더하기

<img src="https://user-images.githubusercontent.com/93306929/178179716-762a1a08-0206-4ad5-ac6f-86dace8dd873.PNG"/>
3. 자바에서 'java project' 파일을 만들고 그 파일을 오른쪽 클릭해서 'properties'로 들어가기. 그 후에 그림처럼 임폴트

<img src="https://user-images.githubusercontent.com/93306929/178179795-b0cdc427-3931-4505-bb3c-91d8887b1405.PNG"/>
4. 다음으로 XML을 복사. FactoryBuilder(1)를 빌드해서 공용자원인 SqlSessionFactory(3)을 만드는 과정. 자바에서 'ctrl+n을 해서 xml검색 후 생성하고 거기다 '붙여넣기'

<img src="https://user-images.githubusercontent.com/93306929/178179921-7766dfdb-34e7-40f5-862e-e1ea793cd09b.PNG"/>
5. 다음으로 그림에 나온 Resources를 복사. 자바에서 클래스를 만들고 그 안에 붙여넣기 하고 '임폴트랑 트라이캣치이용' 그 후에 resource 경로는 'xml쪽'으로 설정.

<img src="https://user-images.githubusercontent.com/93306929/178180057-bb519a9c-ba4e-47a8-a4e2-c84b005e5600.PNG"/>
6. 자바에서 'ctrl+n을 해서 file검색' 후 제너럴 쪽에 있는거 생성 하고 그림처럼 생성.   
아니면 text쳐서 똑같이 만들고 제목을 ㅁ.properties로 바꿔주기. username은 생성자명 password는 생성자 비밀번호

7.아까 만든 xml으로 돌아가서 '<configuration> 밑에 <properties resource = "ㅁ.properties" />' 를 만들기
  
<img src="https://user-images.githubusercontent.com/93306929/178180255-c3027998-f4d7-4f2a-901b-a4213ea478b3.PNG"/>
8.그림에 보이는 매핑된 Sql 구문을 가지고 MapperXML(11)을 만들거니 복사.   
자바에서 ctrl+n해서 xml 만들고 붙여넣기 한 뒤에 select쪽은 지워두기.   
SqlSessionFactory(3).xml 쪽의 밑에 mapper resource쪽을 지금 만든 경로로 설정.
  
<pre>
지금까지 한게 Builder(1)를 통해서 Factory(3)라는 Static과 Mapper(11)를 만든것.
이제 SqlSession(10)을 만들어서 Mapper(11)에 접근시켜야 한다.

Mapperinterface(6)의 Mapper인스턴스를 만들어야 한다.   
interface에다가 미리 지정을 해놓고 그 타입으로만 받게끔 코딩을 할 것이다.   
리스트의 타입이나 또는 형변환할때 문제 발생 안되게 하려는 것.   
</pre>

9. 자바에서 컨트롤n 누르고 인터페이스를 하나 만들어주기. 이름은 Mapperinterface으로 알기 쉽게 지정.
10. 이제 MapperXML(11)에 있는 메퍼를 <mapper namespace = "Mapperinterface"> 이렇게 경로설정 해주면 연동이 끝난다.

<pre>
이게 매핑된 Mapperinterface(6)를 만든것. Sqlsession(10)을 만드는건 DAO클래스에서 만들어 주면 된다.
try (SqlSession session = factory.openSession()){
Mapperinterface mapper = session.getMapper(Mapperinterface.class);
} catch (Exception e) {
e.printStackTrace();
}
</pre>

## 정리(밑의 사진 참조)

1. 클래스 MybatisConfig는 mybatis-config.xml을 읽어오는 클래스고 이걸 읽어오기 위해 xml안에 properties resource를 만드는 것이다.   
2. 이 properties값은 데이터베이스에 접속할때 계정과 패스워드가 필요하다. 이걸위해 db.properties를 만든 것이다.   
3. mybatis-config.xml안의 mapper는 내가 실행할 xml문들이 저장되어 있는 파일이다. 이것이 memberMapper.xml   
4. Mapperinterface의 안을 체우는 일이 매핑이라고 보면 되고 SqlSession은 DAO클래스에서 처리해주면 memberMapper.xml에 접근하게 되는 것이다.   

<img src="https://user-images.githubusercontent.com/93306929/178180894-1084101e-9ea0-4ba2-8167-70dcc89f75f1.PNG"/>
