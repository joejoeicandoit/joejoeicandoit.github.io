---
layout: post
current: post
cover:  assets/built/images/oracle_linux.png
navigation: True
title: Linux 커맨드 이야기
date: 2023-10-12 00:00:00 +0900
tags: [linux]
class: post-template
subclass: 'post tag-linux'
author: joeyeongjune
---

{% include linux-table-of-contents.html %}

```
$ sudo dnf clean all
```
`dnf clean all` 명령어는 Fedora 및 RedHat 계열의 Linux 배포판에서 사용되는 패키지 관리 도구인 DNF(Dandified Yum)를 통해 시스템에서 패키지 캐쉬를 정리 하고 삭제하는 명령어 입니다. 해당 명령어를 실행 함으로서 이전에 다운로드한 패키지 정보를 삭제 하고, 디스크 공간의 확보 및 시스템 성능의 최적화를 진행할 수 있습니다.

- `sudo`:슈퍼유저 또는 관리자 권한으로 명령을 실행하도록 하는 명령어.
- `dnf`:DNF패키지 관리 도구를 실행하는 명령어.
- `clean`:패키지 관리 도구의 서브 커맨드로 "clean"을 사용 하라는 의미.
- `all`:패키지 관리 도구의 서브 커맨드로 모든 캐시 및 패키지 메타데이터를 삭제 하라는 의미.

```
$ sudo cat /etc/oracle-release
```
설치한 오라클 리눅스의 버전을 확인 하는 명령어 입니다.