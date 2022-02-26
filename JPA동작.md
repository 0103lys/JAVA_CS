# JPA(Java Persistence API)
* JPA는 자바 진영에서 ORM(Object-Relational Mapping) 기술 표준으로 사용되는 인터페이스 모음
	- 실제로 구현된 것이 아니라 구현된 클래스와 매핑해주기 위해 사용되는 프레임워크
	- 자바에서 관계형 데이터베이스를 사용하는 방식을 정의한 인터페이스
	- 인터페이스이기 때문에 대표적인 JPA를 구현한 오픈소스 Hibernate가 있음

`JPA 동작`
<br><br>
![image](https://user-images.githubusercontent.com/86811852/155684380-5eb91d60-a819-48ff-8554-08e3bbfd45b3.png)
<br>애플리케이션과 JDBC 사이에서 동작.
JPA를 사용 -> JPA 내부에서 JDBC API를 사용하여 SQL을 호출하여 DB와 통신.



JPA 사용이유?
반복적인 CRUD SQL을 처리
SQL이 아닌 객체 중심으로 개발할 수 있다는 장점
=> 생산성이 좋고, 유지보수도 수월함.
Java에서는 상속관계가 존재하는데 데이터베이스에서는 객체의 상속관계를 지원하지 않음.



ORM(Object-Relational Mapping) 
Class와  RDB(Relational DataBase(=관계형데이터베이스))의 테이블을 매핑(연결)하는 것
- 장점 : SQL문이 아닌 Method를 통해 DB조작
