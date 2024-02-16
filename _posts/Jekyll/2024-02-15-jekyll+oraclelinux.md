---
title: "Jekyll을 이용한 GitHub page 블로그 작성(1)" 
date: 2024-02-15 00:00:00 +0900
layout: posts
category: jekyll
mermaid: true
author_profile: true
sidebar:
    nav: "saidebar-category"
---

# 환경구축에 대해

`Oracle Linux server` 를 사용해서 개발 환경을 구축 했습니다.  
이유는 linux의 공부 목적도 있었지만, Windows에서 구축할때 에러가 너무 많이 발생해서,
제대로 해보기도 전에 지칠꺼 같았기 때문입니다.
※Windows는 훗날 다시 도전해 보고, 내용 정리 되면 업로드할 예정!

## 1. Git

```
## git 설치
$ sudo yum -y install git

## 확인
$ git --version
```

## 2. rbenv

```
## rbenv 설치
$ git clone https://github.com/sstephenson/rbenv.git ~/.rbenv

## 확인
ls -d ~/.rbenv
```

## 3. ruby-build

```
## ruby-build 설치
$ git clone https://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build

## 확인
$ ls -d ~/.rbenv/plugins/ruby-build
```

## 4. .bash_profile

```
## 설정
$ echo '# rbenv' >> ~/.bash_profile
$ echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bash_profile
$ echo 'eval "$(rbenv init -)"' >> ~/.bash_profile

## 확인
$ cat ~/.bash_profile

## 적용
$ exec $SHELL --login
```

## 5. packge

```
## ruby 설치에 필요한 패키지 설치
$ sudo yum -y install bzip2 gcc openssl-devel readline-devel zlib-devel

## 확인
$ bzip2 --version
$ gcc --version
$ yum list installed | grep openssl-devel
$ yum list installed | grep readline-devel
$ yum list installed | grep zlib-devel
```

## 6. ruby

```
## rbenv 버전 확인
$ rbenv --version

## 설치 가능한 ruby 리스트 확인
$ rbenv install --list

## ruby 설치
$ rbenv install <version>

## 설치한 ruby의 리스트 확인(※설치 하지 않은 버전은 표시되지 않는다.)
$ rbenv versions

## 사용할 ruby 버전 설정
$ rbenv global <version>

※ `global` 로 지정된 버전은 유저가 `$ ruby` 명령어를 실행 했을때 사용되는 버전이고, `local` 로 지정된 버전은 유저가 특정 디렉토리에서 `$ ruby` 명령어를 실행 했을때 사용되는 버전입니다. 간단히 말하면, 하나의 버전을 사용할지 디렉토리 마다 다른 버전을 설정 해서 사용할지를 설정할 수 있습니다.

## ruby 버전 확인
$ ruby -v
```

## 7. jekyll

```
## jekyll and bundler 설치
$ gem install jekyll bundler

## jekyll 사이트용 디렉토리 생성
$ jekyll new ~/myblog

## 이동
$ cd ~/myblog

## 사이트를 빌드하고 로컬 서버에 적용
$ bundle exec jekyll serve --host=<oraclelinux IP>

브라우저를 열고 `http//<oraclelinux IP>:4000` 으로 접속 한다.

## 만약, 구축한 서버와 브라우저가 같은 PC일 경우라면, `--host` 옵션을 안넣어도 괜찮다.
$ bundle exec jekyll serve

브라우저를 열고 `http//localhost:4000` 으로 접속.
```

<hr>

## 참고

- [jekyll DOCS:빠른시작](https://jekyllrb-ko.github.io/docs/)