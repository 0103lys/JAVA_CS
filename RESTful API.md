# RESTful API(Representational State Transfer)

## REST
- HTTP URI(Uniform Resource Identifier)을 통해 자원을 명시
- HTTP Method(POST, GET, PUT, DELETE)를 통해
- 해당 자원(URI)에 대한 CRUD Operation을 적용하는 것을 의미

## CRUD Operation
CRUD Create(생성) - 데이터 생성(POST), Read(읽기) - 데이터 조회(GET), 
		Update(갱신) - 데이터 수정(PUT) , Delete(삭제) - 데이터 삭제(DELETE)

## REST API 설계 예시
- URI는 동사보다는 명사, 대문자보다는 소문자를 사용
- 마지막 슬래시(/)를 포함하지 않음
- 언더바 대신 하이픈을 사용
- 파일 확장자는 URI에 포함하지 않음
- 행위를 포함하지 않음


## RESTful
- REST 원리를 따르는 시스템을 의미함. 그러나 REST를 사용했다 헤서 모두 RESTful 한 것은 아님!
- REST API의 설계 규칙을 올바르게 지킨 시스템을 RESTful이라고 말할 수 있음.
- 모든 CRUD 기능을 POST로 처리하는 API 혹은 URI 규칙을 올바르게 지키지 않은 API는 REST API의 설계 규칙을 올바르게 지키지 못한 시스템은 REST API를 사용하였지만
RESTful 하지 못한 시스템이라고 할 수 있음.
