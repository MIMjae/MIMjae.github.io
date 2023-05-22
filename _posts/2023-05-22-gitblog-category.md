---
title: "[gitblog] Minimal Mistakes git-blog 카테고리 수정"
categories:
  - git-blog
# tags:
comment: true
sidebar:
  nav: "docs"
---

### Introduction
--- 

블로그 상단의 카테고리 메뉴를 수정하는 방법이다.

<br>

### navigation.yml 수정
---
카테고리는 _data/navigation.yml 파일으로 수정할 수 있다. 

title은 카테고리 이름, url은 카테고리 주소이다. url에는 실제 주소나 _pages 폴더 하위에 존재하는 마크다운 파일로 설정하면 된다. 

아래 코드는 기존에 있는 Quick-Start, About 페이지를 주석처리한 뒤, 카테고리 이름을 변경하였다. 기존 세팅으로 설정해서 문제없이 적용된다.

```python
# main links
main:
#   - title: "Quick-Start Guide"
#     url: https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/
  # - title: "About"
  #   url: https://mmistakes.github.io/minimal-mistakes/about/
  - auto_categories: true
  - title: "Home"
    url: https://MIMjae.github.io
#  - title: "Posts"
#    url: /year-archive/
  - title: "Category"
    url: /categories/
  - title: "Tags"
    url: /tags/
```

새로운 페이지를 생성하게 되면 _pages 폴더 내에 마크다운 파일을 추가해주어야 한다.


### _config.yml 수정
---
yml 파일은 초기 세팅에서 이미 추가한 경우는 해당사항 없음. 추가하지 않았을 경우 아래 코드를 yml 파일의 가장 하단에 추가하면 된다. 

```python
# Defaults
defaults:
  # _pages
  - scope:
      path: ""
      type: pages
    values:
      layout: single
      author_profile: true
```

<br>

+ 카테고리가 적용되는데에는 어느정도 시간이 소요된다. 

<br>

### References
--- 
[[Github Blog] 카테고리 세팅하기](https://velog.io/@eona1301/Github-Blog-minimal-mistakes-%EC%B9%B4%ED%85%8C%EA%B3%A0%EB%A6%AC-%EC%84%B8%ED%8C%85%ED%95%98%EA%B8%B0)



<br><br>