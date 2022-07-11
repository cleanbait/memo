# SQL
  
1. DQL(Data Query Language) 데이터를 조회 하는 명령어 (사람 따라 DQL이 DML에 포함됨)

<pre>
★select(검색)
select (조회 하고자 하는 컬럼명, 콤마로 구분) from 테이블명 where 조건

★alias (별칭)
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
