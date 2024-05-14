---
layout: posts
title: "apt 와 apt-get 의 차이점" 
date: 2024-03-26 11:00:00 +0900
category: OS
mermaid: true
author_profile: true
sidebar:
    nav: "saidebar-category"
---

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
```







BootDevice Not Found

Plase install on operating system on your hard disk.

Hard Disk - (3F0)

F2 System Diagnostics

For more information, please visit: www.hp.com\go\techcenter\startup



--- From chat GPT

이러한 오류는 주로 하드 디스크가 올바르게 감지되지 않거나 부팅 가능한 운영 체제가 설치되지 않았음을 나타냅니다. 이 문제를 해결하기 위해 다음 단계를 시도할 수 있습니다.

BIOS 설정 확인: 먼저 컴퓨터를 재부팅하고 BIOS 설정으로 들어가서 하드 디스크가 올바르게 감지되었는지 확인합니다. BIOS에서 하드 디스크가 나타나지 않는다면, 하드웨어 연결이나 하드웨어 자체의 문제일 가능성이 높습니다.

부팅 순서 확인: BIOS 설정에서 부팅 순서를 확인하고 하드 디스크가 올바른 순서로 설정되어 있는지 확인합니다. 하드 디스크가 부팅 순서에서 올바르게 설정되어 있지 않으면, 컴퓨터가 하드 디스크에서 운영 체제를 찾을 수 없을 것입니다.

하드 디스크 연결 확인: 컴퓨터의 하드 디스크가 올바르게 연결되어 있는지 확인합니다. 때때로 하드 디스크가 떨어져 있거나 제대로 연결되지 않은 경우가 있습니다.

다른 부팅 장치로 테스트: USB 플래시 드라이브 등 다른 부팅 가능한 장치를 사용하여 시스템을 부팅해 봅니다. 이렇게 하면 하드 디스크에 문제가 있는지 또는 다른 문제가 있는지 확인할 수 있습니다.

하드 디스크 장애 확인: 하드 디스크의 물리적 또는 논리적인 장애가 있는지 확인할 수 있는 도구를 사용합니다. 예를 들어, Ubuntu Live CD나 USB를 사용하여 시스템을 부팅하고 디스크 유틸리티를 실행하여 하드 디스크의 상태를 확인할 수 있습니다.

재설치: 위의 단계들을 시도한 후에도 문제가 해결되지 않는다면, 하드 디스크에 문제가 있을 수 있으므로 새로운 하드 디스크로 교체하거나 운영 체제를 재설치하는 것이 좋습니다.



###########

기동 USB
> rufus 툴을 사용
> 파티션 구성 GPT
> 타켓 시스템 UEFI(CSM なし)

노트북
> BIOS 셋업
> 레거시 BIOS ⇒ UFEI(CSM なし)　변경

USB로 기동
> 파티션 설정

설치 완료 후, Ubuntu 로그인 성공!!



/lib/systemd/system