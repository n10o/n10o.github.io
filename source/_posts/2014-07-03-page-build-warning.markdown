---
layout: post
title: "page-build-warning"
date: 2014-07-03 10:38:29 +0000
comments: true
categories: github
---
octopressでページをデプロイするたびに、githubから[n10o.github.io] Page Build Warningというメールがきていました。

現在、URLを見ても明らかなように、apex domain(サブドメイン無しのdomain名)を使っています。

その場合、204.232.175.78(deprecated)に向けていたDNSのAレコードを、192.30.252.153と192.30.252.154に切り替えてくれとのことです。[参考:github help](https://help.github.com/articles/tips-for-configuring-an-a-record-with-your-dns-provider)

なお、DNSでALIASレコードかANAMEレコードが使える場合はそっちを使えばCDNが効くからオススメらしいです。
