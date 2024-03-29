---
layout: posts
title: "Jekyll을 이용한 GitHub page 블로그 작성(3)" 
date: 2024-02-15 02:00:00 +0900
category: jekyll
mermaid: true
author_profile: true
sidebar:
    nav: "saidebar-category"
---

## Minimal mistake theme 에 사이드바 구현하기

**전제**

- minimal mistakes theme 를 적용한 jekyll 환경.

### 수정 파일

- index.md
- _data/navigation.yml
- _pages/<카테고리 이름>.md

### 수정 내용

#### index.md

초기 화면부터 사이드바 카테고리를 표시 하기 위해 추가.

```
sidebar:
  nav: "saidebar-category"
```

#### _data/navigation.yml

자신이 만들고 싶은 카테고리의 트리를 정의.  
아래 예시는 [saidebar-category] 이름으로 카테고리를 묶고, 각 post를 나열하기 위한 이름과 카테고리 값을 정의.  

```
saidebar-category:   #머리글에서 사용하는 값으로, 원하는 이름으로 정의하면 됩니다.
  - title: "Jekyll"    #사이드바에 표시되는 상위 카테고리 값.
    children:
      - title: "Jekyll"  #카테고리 목록에 표시되는 타이틀 값.
        url: jekyll/
        category: "jekyll" #post 작성시 입력 해줘야 하는 값.
```



#### _pages/

정의한 카테고리에 만큼 마크다운 파일을 만든다.

```
---
layout: archive
title: "Jekyll"
permalink: jekyll
author_profile: true
sidebar:
  nav: "saidebar-category"
---

{% assign posts = site.categories.jekyll %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
```