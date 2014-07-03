---
layout: post
title: "Intro"
date: 2014-06-07 14:23:11 +0900
comments: true
categories: github
---
このブログはOctopressを使ってgithub pagesでホストしています。

deployが面倒だったので、CIツールの[wercker](http://wercker.com/)を使って、githubに記事をpushしたら自動deployする設定にしています。

たまにbuildやdeployで反応がなくなって15分のタイムアウトでこけますが、それを除けばwerckerいい感じです。

![wercker](/images/wercker.jpg)

ただ、記事を書く作業が一番面倒なので、そのうち記事を書く作業も自動化したいです。
