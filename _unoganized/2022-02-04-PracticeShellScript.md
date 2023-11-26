---
title: 'ShellScript練習'
categories:
    - Linux

tag:
    - Linux
    - ShellScript

author_profile: true    #작성자 프로필 출력 여부

last_modified_at: 2022-02-04T16:20:00+09:00

toc: true   #Table Of Contents 목차 

toc_sticky: true
---

### While を使った繰り返し

> $./testWhile.sh

```bash
#!/usr/bin/bash

##変数作成
declare -i COUNTER
declare -i TMP_NUM
COUNTER=0

##入力受付
read -p "何回繰り返しますか？：" TMP_NUM

## COUNTERの値がTMP_NUMより小さければ実行
while [ "$COUNTER" -lt "$TMP_NUM" ]
do
 echo "$COUNTER"回目の繰り返しです。
 let COUNTER++
done
```
> 実行結果

![Image 2290](https://user-images.githubusercontent.com/42788315/152488494-e99a2b58-b5be-4be0-929c-6e8af53cc510.png)