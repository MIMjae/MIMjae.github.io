---
title: "[Backend] JDBC 프로그래밍"
categories:
  - Backend
# tags:
comment: true
sidebar:
  nav: "docs"
---

### JDBC(Java Database Connectivity)
--- 
- 자바 애플리케이션에서 DB 프로그래밍을 할 수 있도록 도와주는 표준 인터페이스
- JDBC 인터페이스들을 구현한 구현체들은 각 데이터베이스 벤더 사들이 제공
![image](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/9997d770-73f9-4096-b00e-3724bcfbc08b)

  
<br><br>

### DBCP(Database Connection Pool)
--- 

- 미리 일정량의 DB 커넥션을 생성해서 풀에 저장해 두고 있다가 HTTP 요청에 따라 필요할 때 풀에서 커넥션을 가져다 사용하는 기법
- 참고로 스프링 부트 2.0 부터는 디폴트 커넥션 풀로 HikariCP 사용



<br><br>

### DataSource
--- 
- 커넥션 획득하기 위한 표준 인터페이스
- HikariCP의 DataSource 사용

  

<br><br>


### 실습
---


