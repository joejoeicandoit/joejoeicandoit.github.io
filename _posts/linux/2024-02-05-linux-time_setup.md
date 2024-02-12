---
title: Linux Time Setup
date: 2024-02-05 00:00:00 +0900
category: linux
author_profile: true
sidebar:
    nav: "saidebar-category"
toc: true
toc_sticky: true
---

### 배경

 - Oracle Linux8을 설치 한 후, 시스템 시간을 확인 해 보니 현재 시간과 맞지 않는다.
 - `$ ntpdate ntp.nict.jp` 커맨드를 입력 해서 일본의 공개 NTP 서버로 시간 동기화를 하려고 하자 명령어를 찾지 못하는 에러가 발생
 - `$ dnf install ntp` 커맨드로 ntp를 설치 하려고 하자 패치키가 없다는 에러가 발생(?)
 
### 결론

- RHEL8 부터 NTP의 프리 설치가 안되도록 변경이 되었다.
- 즉, RHEL의 소스 코드로부터 컴파일한 배포판 CentOS8 및 Oracle Linux8 역시 ntp 설치 불가
- **이제부터 시간 동기화는 `Chrony` 를 사용 하도록 변경.**


### 사용 방법

##### 1. 먼저 chrony 의 버전을 확인

`$ chronyc --version`

버전이 표시 되지 않는다면 설치를 진행 하자.

##### 2. Chrony 설치

`# dnf install chronyd`

##### 3. Chrony 의 기동 상태를 확이

`# systemctl status chronyd`

표시된 결과값의 Active: 뒤쪽이

- inactive (dead) ⇒ chronyd 를 기동
- active (running) ⇒ 시간을 동기화

##### 4. chronyd 기동

`# systemctl start chronyd`


##### 5. 시간 동기

`# chronyc makestep`

##### 6. 확인

`$ date`


##### 그 외 시스템 시간을 변경 하는 방법

###### date

date 커맨드를 사용 하면 현재의 시스템 시간을 확인 하거나 변경이 가능하다.

- 시간 확인 : `date`
- 시간 변경 : `date -s "02/06 13:00 2024"` 


###### hwclock

hwclock 커맨드는 하드웨어(RTC) 시계를 읽어 오거나 설정 하는 커맨드로 하드웨어의 시계 값을 설정 한 후, 시스템 시간을 동기화 해주면 된다.

- 하드웨어 시계의 시간 설정 : `hwclock --set --date "02/06 13:00 2024"` 
- 설정한 하드웨어 시계 시간을 시스템 시간에 동기화 : `hwclock --hctosys` 
  - 반대로 시스템 시간을 하드웨어 시계에 동기화 시키고 싶다면 : `hwclock --systohc` 
  - 시간 확인 : `hwclock --show` 