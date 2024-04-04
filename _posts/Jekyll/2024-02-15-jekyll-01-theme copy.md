---
layout: posts
title: "Jekyll 개발 환경 만들기(2)" 
date: 2024-02-15 01:00:00 +0900
category: jekyll
mermaid: true
author_profile: true
sidebar:
    nav: "saidebar-category"
---

### 9. Git 초기화

- Git으로 프로젝트를 관리 하려는 분들만 진행 하되, 꼭 필수 사항은 아닙니다.

```
## jekyll 서버 디렉토리 이동
$ cd ~/myblog

## 윈도우와 맥의 엔터 방식 오류 방지 설정
$ git config --global core.autocrlf true

## 사용자 이름및 이메일 확인 (※등록 필수)
$ git --global user.name
$ git --global user.email

## 사용자 등록
$ git --global user.name "<본인 이름>"
$ git --global user.email "<본인 이메일>"

## 브랜치명을 main으로 설정
$ git config --global init.defaultBranch main

## repository 설정
$ git init

## repository 확인
$ ls -l
.git

[.git] 의 숨은 디렉토리가 표시되면 OK

## 브랜치 확인
$ git branch
* main

현재 main 브랜치를 사용중이라는 의미

## 파일 추적 상태 확인
$ git status

_config.yml
_posts/
404.html
about.markdown
Gemfile
Gemfile.lock
index.markdown

초기 jekyll을 설치 하면서 생성된 위의 파일및 디렉토리가 빨갛게 표시 된다.
빨간색은 아직 git이 파일들의 버전을 관리 하는 대상으로 인식 하지 않았다는 의미.
```

## 10. 버전 관리 등록

```
$ cd ~/myblog
$ git add .
$ git commit -m "init"
```

## 11. SSH 공개키 생성

```
포스트 작성은 server (Ubuntu) 가 아닌, 별도의 Windows PC 에서 진행 할 예정으로,
서버 접속시 id 와 password 입력 방식을 금지 시키고, 공개키 방식으로만 접속을 할 예정이다.
또한, 키의 passphrase 를 설정 하지 않고, 바로 서버에 접속 하도록 설정 했다.
※사람이 사용하는 이상, passphrase 를 설정 할때 비슷한 password 로 설정 하기때문에 이것이 오히려 Security level을 떨어트리는 결과로 이어진다고 한다.

[Windows PC]

## 키 페이 생성
시작 - Windows PowerShell 기동
Powershell> ssh-keygen

아래의 질문에 대해 모두 Enter 키를 누른다.
1. 키를 저장할 경로
2. passphrase 입력
3. passphrase 재차 입력
```



## 11. ssh_config

$ sudo vi  /etc/ssh/ssh_config

패스워드로 로그인 금지
PasswordAuthentication no

root 로그인 금지
PermitRootLogin no