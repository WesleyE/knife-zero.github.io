---
layout: tips-ja
lang: ja
title: トラブル集
permalink: tips/troubles-ja/
---

## エラー、`Chef::Exceptions::ContentLengthMismatch: Response body length`.

net-ssh 2.9.2以下にある既知の問題が原因です。転送中でも`CHANNEL_CLOSE`を送ってしまうケースがあるようです。  
修正版のnet-ssh 2.9.4以降にアップグレードしてください。

## `Doing old-style registration with ...`という警告がでます

特に問題ありません。[Validatorless Bootstraps | Chef Blog](https://www.chef.io/blog/2015/04/16/validatorless-bootstraps/) の影響で表示されるようになりました。

Knife-Zeroは通常ダミーのvalidation_keyを使用します。このメッセージを無視してもよいし、Chef-Vaultを使って表示されないようにしてもよいです。


## `Field 'policy_name' invalid error` というエラーがでます

おそらく無関係のオプションを`knife.rb`などに設定している状態です。特に`knife configure`によって作られた`validation_key`をセットしている例が多いです。

[https://knife-zero.github.io/40_configuration-ja/](https://knife-zero.github.io/40_configuration-ja/) を参考に、不要なオプションを削除してみてください。
