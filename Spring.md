# SPRING MVC

## Model
- DAO(Data Access Object)역할
- 데이터베이스에서 값을 가져와서 도메인 오브젝트에 리턴시켜주거나 도메인의 값을 가져와 데이터베이스에 리턴시켜주는 역할

## enumclass
- Enum이란 Enumeration의 앞 글자로 열거라는 의미이며, 관련이 있는 상수들의 집합
- 자바에서는 final로 String과 같은 문자열이나 숫자들을 나타내는 기본 자료형의 값을 고정할 수 있고 이렇게 고정된 값을 상수(constant)라고 함. 
- 데이터의 그룹화 및 관리에 용이<br>
![image](https://user-images.githubusercontent.com/86811852/158139496-792462c1-0e95-42c5-8a8c-8c79e2df890b.png)

## Repository
- 저장소 역할
- JPA에서 Repository 인터페이스를 생성 후 JpaRepository<Entity, 기본키타입>을 상속(extends) 받으면 기본적인 CRUD가 자동으로 생성됨.
- 데이터를 검색, 삽입, 수정, 삭제를 할 수 있는 인터페이스
- 내가 사용하고자하는 interface를 만든 후  JpaRepository를 extends 시키기

## Controller
- 사용자의 요청을 처리한 후 지정된 뷰에 모델 객체를 넘겨주는 역할
- 뷰를 연결하여 웹 상에 띄우고, 뷰에서 가져오는 데이터들을 어떻게 처리하는지 사용자가 지정해놓으면 그 역할에 맞춰 사용자의 요청을 처리

## Service 
- Model이 데이터베이스에서 받아온 데이터를 전달받아 가공하는 역할
