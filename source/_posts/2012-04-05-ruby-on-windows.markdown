---
layout: post
title: "WindowsへのRuby環境構築"
date: 2012-04-05 03:32
comments: true
categories: [ruby, windows, vagrant, virtualization, veewee, pik]
---

VagrantにCentOSのboxを作成したいけれども、一からやるよりはveeweeというのを使った方がよさそう？

- [veewee で vagrant 用の仮想サーバ(box)を自動作成 - エンジニアきまぐれTips][1]
- [Vagrant & VeeWee を再設定してCentOS 6.2のBoxを作成してみた - Hirohiroの日記][2]

でもvagrant/veeweeともrubyなので、まずはWindowsにrubyの環境を構築する。

[1]: http://d.hatena.ne.jp/okinaka/20110903/1315034637
[2]: http://d.hatena.ne.jp/Hirohiro/20120122/1327238450

  ---------------------------------------------------------------------

RVM on Windows
==============

- [RVM: Ruby Version Manager - RVM Ruby Version Manager - Documentation][3]

Windows環境へのインストール方法の記述がない。と思ったらFAQに記述があった。

- [RVM: Ruby Version Manager - RVM Frequently Asked Questions][4]

>Does RVM work on windows? Will it in the future?
>
>NO. If you would like to manage multiple versions of ruby on windows please use pik which is an excellent tool by Gordon Thiesfeld. You can find it on GitHub.

WindowsではRVMは動かないらしいので、pikを調べてみる。

[3]: https://rvm.beginrescueend.com/
[4]: http://beginrescueend.com/support/faq/

  ---------------------------------------------------------------------

pik on Windows
==============

- [vertiginous/pik][5]
- [Ruby/Windows7で1.8と1.9環境を同居させる - 俺の基地][6]
- [pikで簡単、複数のRuby環境構築！ » 梨木を読む][7]

ダウンロードページからpik-0.2.8.msiを入手してインストールする。ディレクトリはc:\dev\pikに変更。

[5]: https://github.com/vertiginous/pik/
[6]: http://yakinikunotare.boo.jp/orebase/index.php?Ruby%2FWindows7%A4%C71.8%A4%C81.9%B4%C4%B6%AD%A4%F2%C6%B1%B5%EF%A4%B5%A4%BB%A4%EB
[7]: http://cyberwave.jp/nashiki/2010/05/windows%E3%81%AB%E3%81%A6%E3%80%81%E8%A4%87%E6%95%B0%E3%81%AEruby%E7%92%B0%E5%A2%83%E3%82%92%E5%85%B1%E5%AD%98%E3%81%95%E3%81%9B%E3%82%88%E3%81%86%EF%BC%81/]
