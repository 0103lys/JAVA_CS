# Spring Security
스프링 기반의 애플리케이션의 보안(인증, 권한, 인가 ..)을 담당하는 스프링 하위 프레임워크
<br><br>

## 과정 
![image](https://user-images.githubusercontent.com/86811852/155856914-d753fc07-c0ce-48c2-92c3-1b090acbf2df.png)
<br><br>
		                

`인증(Authorization)`
<br>
해당 사용자가 본인이 맞는지를 확인하는 절차<br><br>
`인가(Authentication)`
<br>
인증된 사용자가 요청한 자원에 접근 가능한지를 결정하는 절차

- 기본적으로 인증 절차를 거친 후 인가 절차를 진행
- 인가 과정에서 해당 리소스에 대한 접근 권한이 있는 지 확인
- Spring Security에서 인증과 인가를 위해 Principal을 아이디로, Credential을 비밀번호로 사용하는 Credential 기반의 인증방식 사용


## Spring Security 사용 모듈
* Authentication
  - 현재 접근하는 주체의 정보와 권한을 담는 인터페이스
  - Authentication 객체는 Security Context에 저장되며, SecurityContextHolder를 통해 SecurityContext에 접근하고, 
	SecurityContext를 통해 Authentication에 접근할 수 있다.


* UsernamePasswordAuthenticationToken
  - UsernamePasswordAuthenticationToken은 Authentication을 implements한 AbstractAuthenticationToken의 하위 클래스로, User의 ID가 Principal 역할을 하고, Password가 Credential의 역할을 함. 
  - UsernamePasswordAuthenticationToken의 첫 번째 생성자는 인증 전의 객체를 생성하고, 두번째 생성자는 인증이 완료된 객체를 생성함.

* SecurityContextHolder
  - 보안 주체의 세부정보를 포함하여 응용프로그램의 현재 보안 컨텍스트에 대한 세부 정보가 저장됨

* SecurityContext
  - Authentication을 보관하는 역할, SecurityContext를 통해 Authentication 객체를 꺼내올 수 있음

* AuthenticationProvider
  - 실제 인증에 대한 부분을 처리함
