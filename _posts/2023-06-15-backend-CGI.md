---
title: "[Backend] 서블릿 프로그래밍"
categories:
  - Backend
# tags:
comment: true
sidebar:
  nav: "docs"
---


<br><br>

### 1. CGI 프로그램과 서블릿
#### CGI (Common Gateway Interface)
---
- 웹 서버와 애플리케이션 사이에 데이터를 주고받는 규약
 - CGI 규칙에 따라서 만들어진 프로그램 = CGI 프로그램
 - 종류 : 컴파일 방식(C, C++, JAVA 등), 인터프리터 방식(PHP, Python)

![image](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/501cc680-7d42-42aa-83e0-9d7bf5a75fd1)

<br><br>

#### Servlet (Server + Applet)
---
- 자바에서 웹 애플리케이션을 만드는 기술
- 자바에서 동적인 웹 페이지를 구현하기 위한 표준


<br><br>

#### ServletContainer
--- 
- 서블릿의 생성부터 소멸까지의 라이프사이클 관리
- 웹 서버와 소켓을 만들고 통신하는 과정 대신 처리 > 개발자는 비즈니스 로직에만 집중 가능
- 서블릿 객체를 싱글톤으로 관리(인스턴스 하나만 생성하여 공유하는 방식)
  - 상태를 유지(sateful)하게 설계하면 안됨
  - Thread safety하지 않음

<br><br>

#### WAS vs 서블릿 컨테이너
---
- WAS 는 서블릿 컨테이너를 포함하는 개념
- WAS는 매 요청마다 스레드 풀에서 기존 스레드를 사용
- WAS의 주요 튜닝 포인트는 max thread 수
- 대표적인 WAS : 톰캣 등

 ![image](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/deb78c56-5458-4a58-87d3-6f61e00c1692)
 

<br><br>


### 2. 계산기 서블릿 실습
#### 프로그램 구조
--- 
![image](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/be20baa7-503a-4802-abc9-adbfc1975bd8)


#### 서블릿 인터페이스
---
- 서블릿 컨테이너가 서블릿 인터페이스에 있는 메소드들을 호출함
- 서블릿 생명주기와 관련된 메소드 : init(), service(), destroy()
- 서블릿 기타 메소드 : getServletInfo(), getServletConfig()


![image](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/7244b3e5-0286-4adc-b2f3-f8d3c4d44edb)


<br><br>

#### URL 인코딩(=퍼센트 인코딩)
---
- URL로 사할 수 없는 문자(예약어, Non-ASCII 문자(한글) 등)를 사용할 수 있도록 인코딩하는 것
- 인코딩 된 문자는 triplet(세 개가 한 세트)로 인코딩 되며 각각을 % 다음에 두 개의 16진수로 표현함