---
title: "[git-blog] Minimal Mistakes로 git-blog 생성하기"
categories:
  - git-blog
# tags:
comment: true
sidebar:
  nav: "docs"
---

### Introduction
--- 

개발 스터디를 시작하기에 앞서 기록을 위해 Github blog를 개설하였다.

생각보다 간단해보였는데 여러가지 커스터마이징을 하는 데 생각보다 오래 걸렸다.

따라서, 스터디 전 테스트로 git-blog 생성과 커스터마이징 과정을 포스팅 해보려고 한다.
  
<br><br>

### git-blog 생성
--- 

1. Github Repository 생성
  
Repository명을 **[username].github.io**로 설정한 뒤, 아래와 같이 설정 후 생성한다.

README 파일은 생성하는 게 훨씬 편하지만 수동으로 세팅해도 무방하다.


![그림1](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/6a65ecd5-1f21-48db-856d-467b0ebe2b37)


2. [username]/[username].github.io 로 접속 후 개설 확인

Repository 생성 후 최대 10분 내에 [username]/[username].github.io로 접속하면 생성된 블로그를 확인할 수 있다.



<br><br>

### Minimal Mistakes 테마 적용
--- 

1. Minimal Mistakes 테마 다운로드

테마는 공식 홈페이지에서 다운받을 수 있다. 

[Minimal Mistakes github](https://github.com/mmistakes/minimal-mistakes) 에서 다운받아 사용하였으나, fork 해서 사용하여도 무방하다.

![그림3](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/95142b62-ecf0-4044-8bcb-ccece96c2601)


2. Minimal Mistakes 구조 정리

필요없는 파일들을 제외하고 아래 사진과 같은 구조로 남기면 된다.

_pages와 _posts 같은 경우에는 처음에 존재하지 않지만 미리 생성해두는게 좋은 것 같다. (어짜피 추후에 생성해야함)

docs는 예시 구조라서 기본 구조 참고할 때 좋은 것 같고, 처음에 docs의 _posts에 있는 마크다운 파일들을 생성한 _posts 폴더 하위로 옮겨두면 예시 포스팅을 확인할 수 있다.

![그림4](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/80da3564-207c-4095-8843-af7e95a32702)


3. [username]/[username].github.io 로 접속 후 테마 적용 확인

<br><br>



### References
--- 

[[Github Blog] Jekyll - minimal mistakes 시작하기](https://velog.io/@eona1301/Github-Blog-Jekyll-minimal-mistakes-%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0)
[GitHub 블로그 기본 설정하기](https://devinlife.com/howto%20github%20pages/blog-config/)

<br><br>