---
title: "[Backend] MVC 프레임워크"
categories:
  - Backend
# tags:
comment: true
sidebar:
  nav: "docs"
---



### Reflection API
--- 

#### 1. Reflection
- 힙 영역에 로드돼 있는 클래스 타입의 객체를 통해 필드/메소드/생성자를 접근 제어자와 상관 없이 사용할 수 있도록 지원하는 API
- 컴파일 시점이 아닌 런타임 시점에 동적으로 특정 클래스의 정보를 추출해낼 수 있는 프로그래밍 기법
- 주로 프레임워크 또는 라이브러리 개발 시 사용됨
<br>

#### 2. Reflection 사용하는 프레임워크/라이브러리
- Spring (DI)
- Test (JUnit)
- JSON Serialization/Deserialization 라이브러리 (Jackson)
<br>

#### 3. 실습
- @Controller 애노테이션이 설정되어 있는 모든 클래스 찾아 출력



<br><br>

### 프런트 컨트롤러
--- 

#### 1. 프런트 컨트롤러 패턴
- 모든 요청을 단일 handler(처리기)에서 처리하도록 하는 패턴
- 스프링 웹 MVC 프레임워크의 DispatcherServlet(프런트 컨트롤러 역할)이 프런트 컨트롤러 패턴으로 구현돼 있음
![image](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/2721d288-3043-4205-9170-5cc62c5609f9)
<br>

#### 2. Forward
- 서블릿에서 클라이언트(웹 브라우저)를 거치지 않고 바로 다른 서블릿(또는 JSP)에게 요청하는 방식
- Forward 방식은 서버 내부에서 일어나는 요청이기 때문에 HttpServletRequest, HttpServletResponse객체가 새롭게 생성되지 않음(공유됨)
- RequestDispatcher dispatcher = request.getRequestDispatcher("포워드 할 서블릿 또는 JSP”)
dispatcher.forward(request, response)
<br>

#### 3. Redirect
- 서블릿이 클라이언트(웹 브라우저)를 다시 거쳐 다른 서블릿(또는 JSP)에게 요청하는 방식
- Redirect 방식은 클라이언트로부터 새로운 요청이기 때문에 새로운 HttpServletRequest, HttpServletResponse 객체가 생성됨
- HttpServletResponse객체의 sendRedirect( ) 이용

![image](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/3f6492e8-fa30-445b-9c5b-634ba2c13553)
<br>

#### 4. 실습

<br><br>


### MVC 프레임워크
---
#### 1. 스프링 웹 MVC 프레임워크

![image](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/d20ea47e-6eee-4202-99c5-8243c01334c8)
<br>

##### 2. 애노테이션 기반 MVC 프레임워크
- DispatcherServlet
- AnnotationHandlerMapping 
- HandlerAdapter 
- ViewResolver
<br>

#### 3. 실습

[실습코드](https://github.com/serverwizard/mvc-practice)