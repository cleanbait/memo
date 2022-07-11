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
제 4,5 정규화 : 왠만하면 안쓴다고 한다. 제3 까지 가면 다 분해된다고 한다.   
  
## 1. DQL(Data Query Language) 데이터를 조회 하는 명령어 (사람 따라 DQL이 DML에 포함됨)

<pre>
* select(검색)
select (조회 하고자 하는 컬럼명, 콤마로 구분) from 테이블명 where 조건

* alias (별칭)
컬럼명 as 별칭

* order by(데이터정렬)
order by & order by desc

* distinct(중복제거)
distinct (컬럼명)

* and, or (그리고, 또는)
where조건절 뒤에 (컬럼명) and (컬럼명), (컬럼명) or (컬럼명)

* in (x개의 컬럼명 안의 값 출력)
where조건절 뒤에 (컬럼명) in(x, y, z)

* between A and B (a와 b사이의 값 출력)
where조건절 뒤에 (컬럼명) between (값) and (값)

* like (포함된 값 출력)
where조건절 뒤에 (컬럼명) like '값%'     값~
where조건절 뒤에 (컬럼명) like '%값'     ~값
where조건절 뒤에 (컬럼명) like '%값%'    값이 있는
where조건절 뒤에 (컬럼명) like '_값%'    _이후 위치에 값이 있는

* union, union all(합집합)
두 개의 select 사이에 입력 (union중복제외,all중복포함)

--------------

DQL 오라클함수
특정 기능을 수행하도록 만들어진 것 (자바로 치면 메소드)

* upper, lower (대문자, 소문자로 변경)
upper (컬럼명or문자열), lower(컬럼명or문자열)

* dual (가상의 테이블)
from dual

* length (문자열의 길이)
length (컬럼명)

* substr (문자열 추출)
substr ('컬럼명 or 문자열', (x)번째 위치, (y)번째 위치)

* replace (특정문자 변경)
replace ('컬럼명 or 문자열', '찾는문자', '변경문자')

* Lpad, Rpad (공백 맞춤)
Lpad (컬럼명, 자릿수, '채울문자')

* concat (문자열 합치기)
concat (컬럼명or문자열, 컬럼명or문자열), 컬럼명or문자열 || 컬럼명or문자열

* trim (공백제거)
trim ('   문자열    ')

* round (반올림)
round(숫자, (x)번째 소수점까지출력)

* trunc (버림)
trunc(숫자, (x)번째 소수점까지 출력)

* mod (나머지)
mod(숫자, 숫자)
날짜 함수 

* add_months (달을 연산하는 함수)
add_months(날짜, 숫자)

* months_between (a~b개월을 구하는 함수)
months_between (날짜, 날짜)

* next_day (날짜 이후의 요일을 구하는 함수)
next_day (날짜, 요일)

* last_day (해당 달의 마지막 날)
last_day (날짜)
형변환 함수

* to_char (문자타입으로 변환)
to_char (날짜)
to_char (sysdate, 'YYYY-MM-DD HH24:MI:SS'') 년월일 시분초
MON, MONTH (월) / DDD (일년중에 몇일) / DAY (요일) / W (달에서 몇주) / WW (일년중에 몇주)

* to_number (문자를 숫자로 변환)
to_number ('숫자')

* to_date (날짜 형식으로 변환)
to_date ('숫자', 'YYMMDD')
null 처리 함수

* nvl (null값을 입력한 값으로 출력)
nvl (null, '문자열')

* nvl (대상이 null일 경우와 아닐경우의 값을 각각 출력)
nvl2 (컬럼명, null일경우, null이아닐경우)
decode와 case 함수

* decode (자바의 스위치와 비슷)
decode (대상, 
            조건1, 조건1에 해당할 때,
            조건2, 조건2에 해당할 때,
            ....
            해당이 없을때)

* case (decode와 비슷하지만 대상을 따로 지정가능)
case 대상
        when 조건1 then 조건1이 참일 경우
        when 조건2 then 조건2가 참일 경우
        ....
        else 일치하는 조건이 없을 경우
end

--------------

그룹화 함수

* sum, count (합계 갯수)
sum(컬럼명 , count(컬럼명)

* max, min, avg (최대,최소,평균)
max(컬럼명), min(컬럼명), avg(컬럼명)

* group by (컬럼의 값을 기준으로 출력)
from문 뒤에 group by (컬럼명)

* having (그룹화된 대상을 제한)
group by문 뒤에 having (컬럼명)
</pre>
 
## DDL(Data Definition Language)
 
<pre>
1. primary key(기본키) = 고유값 = 다른값과 중복될 수 
                        없음 = null도 안됨
2. not null = 중복값 (O) = null(X)
3. default = 인설트할때 null값이 들어오면 0을 자동으로 줌
4. unique = 지정한 컬럼이 유일한 값을 가진다
5. foreign key = 다른 테이블의 열을 참조하여 존재하는 
                값만 허용
6. check = 설정한 조건식을 만족하는 데이터만 허용

* create (테이블 생성)
create table 소유자 계정명 or 테이블명(
    컴럼명1 데이터타입,
    컴럼명2 데이터타입,
    ....
    );

* rename (테이블 이름 변경)
rename 변경할테이블명 to 변경후테이블명

* drop (테이블 삭제)
drop table 테이블명

----------------------------------------------------------------

* alter add (테이블 안의 컬럼 추가)
alter table 테이블명 add 컬럼명 데이터타입

* alter rename (테이블 안의 컬럼명 변경)
alter table 테이블명 rename 컬럼명 to 변경할컬럼명

* alter modify (테이블 안의 컬럼 타입 수정)
alter table 테이블명 modify 컬럼명 데이터타입;

* alter drop (테이블 안의 컬럼 삭제)
alter table 테이블명 drop column 컬럼명;
</pre>
