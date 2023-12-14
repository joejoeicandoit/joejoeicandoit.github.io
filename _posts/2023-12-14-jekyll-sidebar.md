---
title: "[Jekyll] Minimal-mistake Theme 에 사이드 바 카테고리 만들기" 
date: 2023-12-14 00:00:00 +0900
layout: posts
category: jekyll
mermaid: true
author_profile: true
sidebar:
  nav: "saidebar-category"
---

# Minimal-mistake Theme 에 사이드 바 카테고리 만들기

## 수정 파일

- _data/navigation.yml
  - 자신이 만들고 싶은 카테고리의 트리를 정의 한다.
  - 아래 예시에서는 [saidebar-category] 이름으로 카테고리를 묶고, 각 post를 나열하기 위한 이름과 카테고리 값을 정의 했습니다.
```
main:
 - 생략 -

- 여기서 부터 왼쪽 사이드바에 표시할 카테고리 입니다 -
saidebar-category:   #머리글에서 사용하는 값으로, 원하는 이름으로 정의하면 됩니다.
  - title: "Blog"    #사이드바에 표시되는 상위 카테고리 값.
    children:
      - title: "Jekyll"  #카테고리 목록에 표시되는 타이틀 값.
        url: jekyll/
        category: "jekyll" #post 작성시 입력 해줘야 하는 값.
  - title: "Docs"
    children:
      - title: "English"
        url: english/
        category: "english"
      - title: "Mariadb"
        url: mariadb/
        category: "mariadb"
      - title: "Etc"
        url: etc/
        category: "etc"
  - title: "OS"
    children:
      - title: "Linux"
        url: linux/
        category: "linux"
  ```
- index.md
  - 초기 화면부터 사이드바 카테고리를 표시 하기 위해, 아래 머리말을 추가 합니다. 
```
---
layout: home

- 추가 -
author_profile: true
sidebar:
  nav: "saidebar-category"
---
```

- _pages/