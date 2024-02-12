---
layout: posts
title: "Git Command"
date: 2023-11-26 00:00:00 +0900
category: git
author_profile: true
sidebar:
    nav: "saidebar-category"
---

참조 [Documentaion(한국어)](https://git-scm.com/book/ko/v2/%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-%EB%B2%84%EC%A0%84-%EA%B4%80%EB%A6%AC%EB%9E%80%3F)


- 설정 해둔 원격 저장소 확인 하기
  - git remote
  - git remote -v  //옵션을 사용하면 url 정보까지 표시 된다
- 원격 저장소 추가하기
  - `git remote add <단축이름> <url>`


**SSH를 사용해서 원격 저장소 추가 하기**

ssh의 경우 url은 다음과 같이 기술 하다. `git@github.com:OWNER/REPOSITORY.git`
  - `git remote add oraclelinux tickle@git.oraclelinux.com:tickle/home/tickle/gitserver.git`

