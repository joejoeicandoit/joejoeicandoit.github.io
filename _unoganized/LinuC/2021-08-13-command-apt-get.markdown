---
layout: post
title: "Linux Study"
subtitle: "apt-get 명령어"
categories: knowledge
tags: Linux
comments: true
---
> apt-get 명령어

* __apt-get?__

 `우분투(Ubuntu)를 포함한 데비안(Debian) 계열의 리눅스에서 쓰이는 팩키지 관리 명령어 도구`

.인덱스 정보 업데이트 : apt-get 은 인덱스를 가지고 있는데 이 인덱스는 /etc/apt/sources.list 에 있습니다. 이곳에 저장된 저장소에서 사용할 패키지의 정보를 취득합니다.
- apt-get update


.설치된 패키지 업그래이드 : 설치된 패키지를 모두 새버전으로 업그레이드 합니다.
- apt-get upgrade


.의존성 검사하며 설치하기 :
- apt-get dist-upgrade


.패키지 설치 :
- apt-get install 패키지이름


.패키지 재설치 :
- apt-get --reinstall install 패키지이름


.패키지 삭제 : 설정 파일은 지우지 않음
- apt-get remove 패키지이름


.패키지 삭제 : 설정 파일까지 모두 지움
- apt-get --puge remove 패키지이름


.패키지 소스코드 다운로드 :
- apt-get source 패키지이름


.위에서 다운로드한 소스코드를 의존성 있게 빌드 :
- apt-get build-dep 패키지이름

`apt를 이용해서 설치된 deb패키지는 /var/cache/apt/archive/ 에 설치가 됩니다.`