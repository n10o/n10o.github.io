---
layout: post
title: "fluent-plugin-elasticsearchのハマりポイント"
date: 2014-07-15 11:27:45 +0000
comments: true
categories: fluentd, elasticsearch
---
FluentdでElasticsearchサーバにデータを送るときに使う[fluent-plugin-elasticsearch](https://github.com/uken/fluent-plugin-elasticsearch)を利用するためには、公式にも書いてあるようにlibcurl-develが必要です。

これを/etc/sysconfig/clockを適切に設定していないAmazon Linux AMIにインストールすると、内部的にglibcが更新され、その際に時刻情報がUTCに再設定されて、面倒なことになります。

もしJSTにするなら以下の事前設定が必要です。ファイルコピーをした時点で時刻はJSTになるので、それだけでも当座はしのげますが、clockを書き換えないとパッケージを色々更新した時にいつの間にか時刻情報が巻き戻ってハマる可能性があります。
```
$ cp /usr/share/zoneinfo/Japan /etc/localtime
$ cat /etc/sysconfig/clock
ZONE="Asia/Tokyo"
UTC=False
```
なお、実際に時刻情報が書き換わってしまうと、crondが動作しなくなるので、/etc/init.d/crond restartして下さい。

上記現象でcrondが動かなくなると、/var/log/cronに(root) FAILED to authorize user with PAM (Module is unknown) が出て動作しなくなります。
