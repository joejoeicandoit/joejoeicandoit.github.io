---
layout: posts
title: "[Ubuntu] apt 와 apt-get 의 차이" 
date: 2024-05-15 11:20:00 +0900
category: OS
mermaid: true
author_profile: true
sidebar:
    nav: "saidebar-category"
---

### 배경

그동안 RHEL 계열의 리눅스만 써오다가, 마인크래프트 서버 구축을 계기로 데비안 계열 리눅스인 Ubuntu를 사용하게 되었다  
OS 설치는 약간 고생을 했지만 어찌 어찌 해결을 했고, 이후 필요한 프로그램을 설치 하려다 하다 보니 패키지 관리 명령어가 달랐다.  
당분간 Ubuntu를 사용 할껏 같아 겸사 겸사 조사해 본 내용을 적어 놓았다.  

### apt 와 apt-get 의 차이점

- apt 및 apt-get은 우분투(Ubuntu)를 포함한 데비안(Debian)계열의 리눅스에서 쓰이는 패키지 관리 명령어 도구이다.
- 소프트웨어의 설치, 제거, 업데이트 및 관리하는데 사용하는 명령어이다.


1. 사용자 인터페이스

- apt-get 명령줄 지향적으면 간단한 출력을 제공한다.
- apt 컬러 출력및 진행률 표시줄이 있는 친화적 인터페이스를 제공하다.

2. 명령 구문

두 명령어 모두 뒤에 오는 옵션이 거의 비슷하다.

```
# Installing packages
apt install <package>
apt-get install <package>

# Removing packages
apt remove <package>
apt-get remove <package>

# Purging packages (removing package and configuration files)
apt purge <package>
apt-get purge <package>

# Updating package lists
apt update
apt-get update

# Upgrading installed packages
apt upgrade
apt-get upgrade
````