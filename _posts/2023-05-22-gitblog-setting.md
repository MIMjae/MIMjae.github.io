---
title: "[gitblog] Minimal Mistakes git-blog 초기 세팅"
categories:
  - git-blog
# tags:
comment: true
sidebar:
  nav: "docs"
---

### Introduction
--- 

블로그를 커스터마이징 하기 전, 초기 세팅을 진행한다.

블로그 정보, 카테고리, 사이드바, 테마 색, 글씨체 등을 변경하는 방법을 포스팅한다.

<br>

### 블로그 정보 수정
--- 

블로그 정보는 _config.yml 파일에서 수정할 수 있다. 파일 위치는 디렉토리 최상위.

#### 1. 테마 변경

15번째 열의 minimal_mistakes_skin 값을 변경한다. 기본값은 default, 주석 부분의 테마를 전부 적용할 수 있다. 각 테마들의 css는 _sass/minimal-mistakes/_skins.scss 에서 확인할 수 있다.

```html
minimal_mistakes_skin    : "dirt" # "air", "aqua", "contrast", "dark", "dirt", "neon", "mint", "plum", "sunrise"
```

#### 2. 블로그 정보 변경

17번째 열부터 Site setting을 수정할 수 있다.

title, name, description, repository 을 수정하였다. repository는 수정해놓는 것이 좋다. (언젠가 필요했던 것 같으나 추후에 찾아 작성하겠음.) 

```html
locale                   : "en-US"
title                    : "MIMjae's blog"
title_separator          : "-"
subtitle                 : # site tagline that appears below site title in masthead
name                     : "MIMjae"
description              : "An amazing website."
url                      : # the base hostname & protocol for your site e.g. "https://mmistakes.github.io"
baseurl                  : # the subpath of your site, e.g. "/blog"
repository               : "MIMjae/MIMjae.github.io" # GitHub username/repo-name e.g. "mmistakes/minimal-mistakes"
```

#### 3. 블로그 주인 정보 변경

105번째 열(다를 수 있음)부터 Site Author 정보를 수정하면 된다.
바이오 이미지는 assets/images/ 에 이미지를 추가하여 수정하면 된다. 참고로 해상도가 너무 높으면 흰바탕이 생기므로, 조정해주는 것이 필요하다. 원본 이미지는 480*480 이다.(아마도)

links 부분은 프로필 하단에 표시되는 SNS, Github 이다. 필요한 것만 남기고 나머지는 삭제 혹은 주석처리하면 된다.

```html
author:
  name             : "MIMjae"
  avatar           : "/assets/images/bio-photo.jpg"
  bio              : "개발공부기록"
  location         : "Seoul, Republic of Korea"
  email            :
  links:
    - label: "Website"
      icon: "fas fa-fw fa-link"
      url: "https://MIMjae.github.io"
```

##### 4. Footer 설정

사이트 하단에도 Github나 SNS 등을 추가할 수 있다. FEED 표시가 되어있는 부분이다.
위와 같이 url 추가만 하면 설정할 수 있으나, 나는 삭제하였다.

##### Defaults 값 설정

post, page 등의 설정에 필요한 부분이다. 기본 설정에서 가장 중요한 부분이라고 할 수 있다. yaml 파일 제일 하단에 추가만 해주면 된다. 

```html
# Defaults
defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: true
      comments: # true
      share: true
      related: true
  # _pages
  - scope:
      path: ""
      type: pages
    values:
      layout: single
      author_profile: true
```

<br><br>

### 카테고리 변경
--- 

#### 

  

<br><br>

### title 3
---


<br><br>

### title 3
---


<br><br>

### title 3
---


<br><br>

### References
--- 



<br><br>