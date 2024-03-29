---
layout: posts
title: "hp 노트북에 Ubuntu 설치시 Hard Disk Errir" 
date: 2024-03-26 01:00:00 +0900
category: OS
mermaid: true
author_profile: true
sidebar:
    nav: "saidebar-category"
---

## 발단

linux 공부 해보겠다고 중고로 구입한 hp 노트북에 Ubuntu만이 제대로 설치가 안되는 경우가 있었다.  
발생 타이밍은 OS 설치후 시스템 재시작 했을때 
※Rocky linux 나 Oracle linux 의 경우 설치와 동작에 문제 없음.  







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