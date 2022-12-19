# 如何测试DNS服务器的响应速度
使用``dig``命令， 基本用法``dig <DNS Address> <Address>``

Example：
```bash
jiaqi.zhang@mbp ~ % dig 1.1.1.1 www.baidu.com

; <<>> DiG 9.10.6 <<>> 1.1.1.1 www.baidu.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NXDOMAIN, id: 25468
;; flags: qr rd ra ad; QUERY: 1, ANSWER: 0, AUTHORITY: 1, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;1.1.1.1.			IN	A

;; AUTHORITY SECTION:
.			86397	IN	SOA	a.root-servers.net. nstld.verisign-grs.com. 2022121900 1800 900 604800 86400

;; Query time: 83 msec
;; SERVER: 8.8.8.8#53(8.8.8.8)
;; WHEN: Mon Dec 19 23:14:51 CST 2022
;; MSG SIZE  rcvd: 111

;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 50898
;; flags: qr rd ra; QUERY: 1, ANSWER: 3, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;www.baidu.com.			IN	A

;; ANSWER SECTION:
www.baidu.com.		667	IN	CNAME	www.a.shifen.com.
www.a.shifen.com.	225	IN	A	36.152.44.95
www.a.shifen.com.	225	IN	A	36.152.44.96

;; Query time: 88 msec
;; SERVER: 8.8.8.8#53(8.8.8.8)
;; WHEN: Mon Dec 19 23:14:51 CST 2022
;; MSG SIZE  rcvd: 101

jiaqi.zhang@mbp ~ %
```