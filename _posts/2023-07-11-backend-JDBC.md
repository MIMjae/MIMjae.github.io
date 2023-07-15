---
title: "[Backend] JDBC 프로그래밍"
categories:
  - Backend
# tags:
comment: true
sidebar:
  nav: "docs"
---

### JDBC 프로그래밍
---
#### 1. JDBC(Java Database Connectivity)
- 자바 애플리케이션에서 DB 프로그래밍을 할 수 있도록 도와주는 표준 인터페이스
- JDBC 인터페이스들을 구현한 구현체들은 각 데이터베이스 벤더 사들이 제공 > JDBC 드라이브
- DB를 변경하더라고 코드 변경 없이 동일한 JDBC 코드 사용 가능
![image](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/9997d770-73f9-4096-b00e-3724bcfbc08b)

  
<br><br>

#### 2. DBCP(Database Connection Pool)
- 미리 일정량의 DB 커넥션을 생성해서 풀에 저장해 두고 있다가 HTTP 요청에 따라 필요할 때 풀에서 커넥션을 가져다 사용하는 기법
- 참고로 스프링 부트 2.0 부터는 디폴트 커넥션 풀로 HikariCP 사용
- 커넥션 풀 사용 시 유의사항
  - 커넥션의 사용 주체는 WAS 스레드이므로 커넥션 개수는 WAS 스레드 수와 함께 고려해야 함
  - 커넥션 수를 크게 설정하면 메모리 소모가 큰 대신 동시 접속자 수가 많아지더라도 사
용자 대기 시간이 상대적으로 줄어들게 되고, 반대로 커넥션 개수를 작게 설정하면 메모리 소모는 적은 대신 그만큼 대기시간이 길어질 수 있음. 따라서 적정량의 커넥션 객체를 생성해 두어야 함

<br><br>

#### 3. DataSource
- 커넥션 획득하기 위한 표준 인터페이스
- HikariCP의 DataSource 사용

  

<br><br>


### 실습
---


