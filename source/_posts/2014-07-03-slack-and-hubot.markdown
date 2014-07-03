---
layout: post
title: "slack-and-hubot"
date: 2014-07-03 12:20:09 +0000
comments: true
categories: 
---
チャットツールのslackを試すついでにhubotを入れました。

hubot自体のインストールは各所で書かれている通り、nodejsとnpmを入れて、npmでhubotとcoffee-scriptを入れてhubot --createで簡単にできます。

slackとのつなぎ込みは[hubot-slack](https://github.com/tinyspeck/hubot-slack)に書かれている通りに実施して、herokuでホストさせれば無料で動かせるところまでいきます。

なお、hubotのプロジェクトを作った後に自動でscriptsフォルダが生成されますが、この中のスクリプトはデフォルトで実行されるので、不要なものは別の場所に置きましょう。初期スクリプトの中にはredisを利用するものもあるので、インストールしていなければ警告が出ます。

後は、herokuのconfigで部屋情報等を設定し、slackの設定のIntegrationからhubotを設定すれば動きます。

私はデフォルトのスクリプト系はほとんど外しておきましたが、以下のような状況に陥ったので、

![please pug me](/images/slack1.jpg)

対応して、

![implement pug me](/images/slack2.jpg)

ハッピーになったと思ったら、

![happy](/images/slack3.jpg)

その後、チャットルームがpugだらけになってしまったので、良かったのか良くなかったのかはよくわかりません。
