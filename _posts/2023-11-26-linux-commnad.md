---
title: "리눅스 커맨드"
author: Yeongjune Joe
date: 2023-11-26 00:00:00 +0900
layout: posts
category: linux
author_profile: true
sidebar:
    nav: "saidebar-category"
---

# Linux 서버 - 서버 운용시 유용한 커맨드 정리

**목차**

- [Linux 서버 - 서버 운용시 유용한 커맨드 정리](#linux-서버---서버-운용시-유용한-커맨드-정리)
    - [메모리 사용량을 감시 하고 싶을 때](#메모리-사용량을-감시-하고-싶을-때)

---

### 메모리 사용량을 감시 하고 싶을 때

|No|커맨드|설명|사용예|
| --- | --- | --- | --- |
|1|top|시스템의 상태를 실시간으로 확인. 종료시에는 <q>를 입력|`top`|
|2|ps|프로세스별 메모리 사용량을 표시한다.|`ps aux --sort=-rss` 메모리의 양이 높은 순으로 표시|