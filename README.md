# SQL
 SQL(Structured Query Language)란?
(구조적 질의 언어)의 줄임말로, 관계형 데이터베이스 시스템(RDBMS)에서 자료를 관리 및 처리하기 위해 설계된 언어이다.

1. SQL은 대소문자를 가리지 않으며
2. SQL명령은 반드시 세미콜론(;)으로 끝나야 하며
3. 고유의 값은 따옴표('')로 감싸주며
4. 객체는 백틱(``)으로 감싸준다.

정규화를 통해 데이터를 유지하고 저장한다.

제1 정규화 : 테이블의 컬럼이 원자값을 가지도록 테이블 분해   
제2 정규화 : 제1 정규화를 진행한 테이블에 대해 완전 함수 종속을 만족하도록 테이블을 분해   
제3 정규화 : 제2 정규화를 진행한 테이블에 대해 이행적 종속을 없애도록 테이블을 분해   
BCNF : 제3 정규화를 진행한 테이블에 대해 모든 결정자가 후보키가 되도록 테이블을 분해   
제 4,5 정규화 : 왠만하면 안쓴다 제3 까지 가면 다 분해됨   
  
## 1. DQL(Data Query Language) 데이터를 조회 하는 명령어 (사람 따라 DQL이 DML에 포함됨)

<pre>
### select(검색)
select (조회 하고자 하는 컬럼명, 콤마로 구분) from 테이블명 where 조건

alias (별칭)
컬럼명 as 별칭

★order by(데이터정렬)
order by & order by desc

★distinct(중복제거)
distinct (컬럼명)

★and, or (그리고, 또는)
where조건절 뒤에 (컬럼명) and (컬럼명), (컬럼명) or (컬럼명)

★in (x개의 컬럼명 안의 값 출력)
where조건절 뒤에 (컬럼명) in(x, y, z)

★between A and B (a와 b사이의 값 출력)
where조건절 뒤에 (컬럼명) between (값) and (값)

★like (포함된 값 출력)
where조건절 뒤에 (컬럼명) like '값%'     값~
where조건절 뒤에 (컬럼명) like '%값'     ~값
where조건절 뒤에 (컬럼명) like '%값%'    값이 있는
where조건절 뒤에 (컬럼명) like '_값%'    _이후 위치에 값이 있는

★union, union all(합집합)
두 개의 select 사이에 입력 (union중복제외,all중복포함)
</pre>
