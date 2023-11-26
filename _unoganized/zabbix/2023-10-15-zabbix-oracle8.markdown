---
layout: post
current: post
cover:  assets/built/images/oracle_linux.png
navigation: True
title: Zabbix 설치 하기(1)
date: 2023-10-15 00:00:00 +0900
tags: [zabbxi]
class: post-template
subclass: 'post tag-zabbxi'
author: joeyeongjune
---

{% include zabbix-table-of-contents.html %}

## Zabbix 메뉴얼

https://www.zabbix.com/documentation/current/jp/manual

### 1. Install MariaDB 10.6 on Oracle Linux 8

https://techviewleo.com/install-mariadb-on-oracle-rocky-linux/



[Install MariaDB](https://techviewleo.com/install-mariadb-on-oracle-rocky-linux/)



### 2. Download and Install Zabbix

https://www.zabbix.com/jp/download?zabbix=6.0&os_distribution=oracle_linux&os_version=8&components=server_frontend_agent&db=mysql&ws=apache

### Open Zabbix UI web page

http://[host]/zabbix

** Issue **
<hr>

Zabbix server is not running

```
https://jsson.tistory.com/47
```

Zabbix clock of Dashboard timezone

```
[User Settings] - [Profile] - [Time zone] - [(UTC+09:00) Asia/Tokyo]

```