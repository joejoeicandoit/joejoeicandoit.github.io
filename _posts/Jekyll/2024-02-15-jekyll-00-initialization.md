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

## 환경

- 빈번히 발생하는 Windows 환경의 에러문제로 인해, 개발환경의 OS는 `Oracle Linux server` 를 사용했습니다.
- Jekyll 사용을 위해서 ruby 언어의 설치가 필요합니다. ruby 의 버전별 관리를 간편히 하기 위해 `rbenv` 를 사용 했습니다.



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
```

## 8. Start

```
## 사이트 기동
$ bundle exec jekyll serve

## 브라우저를 열고 `http//localhost:4000` 으로 접속하면 jekyll 로 구현한 정적 웹 사이트가 보여질것이다.
## 만약, 사이트를 구축한 Linux 서버와 접속 하는 브라우저가 서로 다른 PC라면, <localhost:4000> 으로 접속이 안되기에,
## 아래의 방법으로 사이트를 기동 시키고 접속 하면된다.

$ bundle exec jekyll serve --host=<linux server IP>

## 브라우저를 열고 `http//<linux server IP>:4000` 으로 접속.
## 혹시, 4000포트를 변경 하고 싶다면 `--port=<port number>` 옵션도 추가해주면 된다.
```

-----

## 참고

- [jekyll DOCS:빠른시작](https://jekyllrb-ko.github.io/docs/)