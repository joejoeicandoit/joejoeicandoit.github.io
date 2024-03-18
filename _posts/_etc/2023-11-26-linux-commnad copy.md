

**내가 Linux Server를 사용하면서   사용하는 커맨드 정리!!**

#### uname

カーネル情報などを表示すうコマンド
- オプション
  - a (すべての情報を表示)
  - r (カーネルバージョンを表示)
  - n (ホスト名を表示)
  - p (プロセッサの種類を表示)


```shell
[tickle@oracle8 ~]$ uname
Linux
[tickle@oracle8 ~]$ uname -a
Linux oracle8 5.15.0-200.131.27.el8uek.x86_64 #2 SMP Wed Oct 4 22:19:10 PDT 2023 x86_64 x86_64 x86_64 GNU/Linux
[tickle@oracle8 ~]$ uname -r
5.15.0-200.131.27.el8uek.x86_64
[tickle@oracle8 ~]$ uname -n
oracle8
[tickle@oracle8 ~]$ uname -p
x86_64
```

#### netstat

- ホストのネットワーク接続状態やソケット・インターフェイスごとのネットワーク統計などを表示するコマンド
- オプション
  - a	すべての接続を表示	接続待ちを含めた全ポートが表示される
  - b	サービス名/実行ファイル名を表示	
  - f	外部アドレスをFQDNで表示	
  - n	外部アドレスをIPアドレスで表示、プロトコルではなくポート番号で表示
  - e	インターフェースの統計情報を表示	
  - r	ルーティングテーブル（ルーティングキャッシュ）を表示	
  - s	各プロトコルの統計情報を表示	
  - o	プロセスIDを表示	
  - p	プロトコルを指定して表示	-ap tcpのように、他オプションと組み合わせて使う

```shell
[tickle@oracle8 ~]$ netstat -nltp
(Not all processes could be identified, non-owned process info
 will not be shown, you would have to be root to see it all.)
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name
tcp        0      0 0.0.0.0:3306            0.0.0.0:*               LISTEN      -
tcp        0      0 127.0.0.1:53            0.0.0.0:*               LISTEN      -
tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN      -
tcp        0      0 192.168.0.2:53          0.0.0.0:*               LISTEN      -
tcp        0      0 127.0.0.1:953           0.0.0.0:*               LISTEN      -
tcp        0      0 0.0.0.0:10050           0.0.0.0:*               LISTEN      -
tcp        0      0 0.0.0.0:10051           0.0.0.0:*               LISTEN      -
tcp6       0      0 ::1:953                 :::*                    LISTEN      -
tcp6       0      0 :::3306                 :::*                    LISTEN      -
tcp6       0      0 :::80                   :::*                    LISTEN      -
tcp6       0      0 :::22                   :::*                    LISTEN      -
tcp6       0      0 :::10050                :::*                    LISTEN      -
tcp6       0      0 :::10051                :::*                    LISTEN      -

```


## 메모리 사용량 감시

|No|커맨드|설명|사용예|
| --- | --- | --- | --- |
|1|top|시스템의 상태를 실시간으로 확인. 종료시에는 <q>를 입력|`top`|
|2|ps|프로세스별 메모리 사용량을 표시한다.|`ps aux --sort=-rss` 메모리의 양이 높은 순으로 표시|