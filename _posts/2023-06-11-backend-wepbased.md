---
title: "[Backend] 웹 애플리케이션 이해"
categories: 
  - Backend
# tags:
comment: true
sidebar:
  nav: "docs"
---

### HTTP 프로토콜 이해
--- 

#### 1. HTTP

- HTTP 프로토콜 이해
  - 서버와 클라이언트가 웹에서 데이터를 주고받기 위한 프로토콜(규약)
  - 참고
    - HTTP/1.1 , HTTP/2는 TCP 기반 위에서 동작 (3-way handshake 통해서 연결)
    - HTTP/3는 UDP 기반 위에서 동작 (3-way handshake로 연결될 필요가 없음)

- HTTP 요청/응답 메시지 구조 <br>
  ![image](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/56b3bf3a-e343-426b-8c1b-688613652159)

  - 규칙대로 클라이언트와 서버가 데이터를 주고받음

- HTTP 특징
  - 클라이언트-서버 모델
  - 무상태 프로토콜(Stateless)
    - 서버가 클라이언트 상태를 유지하지 않음
    - 해결책 : Keep-Alive 속성 사용<br>
    ![image](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/0f4fe91b-144c-423d-b799-8181a872d096)
    - 일정시간동안 연결 유지, 잘못사용하게되면 웹스레드 부족(클라이언트 多)

  - 비 연결성(Connectionless)
    - 서버가 클라이언트 요청에 대해 응답을 마치면 맺었던 연결을 끊어 버림
    - 해결책 : 쿠키(클라이언트에 정보 저장), 세션(서버에 정보 저장), JWT

  - 기타
    - HTTP 요청 메소드 : GET, POST, PUT, DELETE 등
    - HTTP 응답 코드 : 2xx(성공), 3xx(리다이렉션), 4xx(클라이언트 에러), 5xx(서버 에러) 등
    - HTTP 헤더 : Content-type, Accept, Cookie, Set-Cookie, Authorization 등

