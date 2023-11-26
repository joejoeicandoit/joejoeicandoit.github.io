---
title: 'Raspberry Pi4 에 사용한 32GB micro SD CARD 의 디스크 확장'
categories:
    - RaspberryPi

tag:
    - RaspberryPi
    - Linux
    - CentOS

author_profile: true    #작성자 프로필 출력 여부

last_modified_at: 2021-11-25T11:20:00+09:00

toc: true   #Table Of Contents 목차 

toc_sticky: true
---


리눅스 서버의 공부 목적으로 RaspberryPi4 B 모델을 아마존에서 구매, 스토리지로는 32GB 용량의 micro SD Card를 구매.
CentOS 7 minimal 을 설치 하고, 부팅 후, 네트워크까지 문제 없이 진행을 마치고, 의기 양양하게 이후 yum을 이용한 패키지를 설치 하려고 하자,
스토리지의 용량 부족이라는 메세지를 토해냄과 함께, 왜(?) 라는 의구심을 갖고, 다시 또 구글링을 시작 했다...


일단 파일 시스템의 사용 현황을 했는데, 아무리 봐도 32GB의 용량으로 보이진 않았고, 딱히 설치한 패키지도 없는데 디스크 사용량이 이미 100%를 표시하고 있었다.



> df -H
![Image 055](https://user-images.githubusercontent.com/42788315/143250815-f4895d56-173e-481f-afa3-622b1d71941a.png)


Disk /dev/mmcblk0: 32.0 GB로 총 용량은 맞지만, 부트 시스템과 스왑용 영역을 제외한 나머지 영역을 /dev/mmcblk0p3 의 파티션이 제대로 잡질 못하고 있어서, 지금의 3번째 파티션을 삭제 하고, 새롭게 다시 작성 하기로 했다.


> fdisk /dev/mmcblk0
![Image 056](https://user-images.githubusercontent.com/42788315/143250825-a7ae9f41-aa35-4016-9d5d-feae4ab2bc7f.png)
![Image 057](https://user-images.githubusercontent.com/42788315/143250832-73ac1bd0-7320-4467-b276-dd7ac11e3d3d.png)
  
  

> Comand (m for help): n
Select (default p):p  
Pattition number (3,4, default 3): 3  
First sector (2048-62521343, default 2048): 시작 영역은, 2번 파티션 End값에서 +1 한 값  
Last sector: 남은 용량을 모두 사용 하기에 Enter  
Comand (m for help): w
![Image 058](https://user-images.githubusercontent.com/42788315/143250839-919ca522-999e-4c86-8c2a-ae766faeee51.png)
![Image 059](https://user-images.githubusercontent.com/42788315/143250854-a7c3dd02-02fa-4162-9810-1a2e081ad741.png)


시스템을 재시작해서 다시 확인 해 봤지만, 아직 제대로 인식을 안하고 있었서 3번 파티션을 리사이즈 했고, 이후 /dev/root 가 정상적으로 확장 된걸 확인 할수 있었다.


> resize2fs /dev/mmcblk0p3
![Image 060](https://user-images.githubusercontent.com/42788315/143250863-543de59f-be3e-4eb1-8415-eda276cce11c.png)
