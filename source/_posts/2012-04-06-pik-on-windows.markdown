---
layout: post
title: "pikによるrubyインストール"
date: 2012-04-06 02:13
comments: true
categories: [windows, ruby, pik]
---

pikを動作させる
===============
msiからpikをインストールして実行してみるとなぜかうまく動かない。

	C:\dev\pik>pik list

	There was an error.
	 Error: can't dup NilClass

	  in: pathname.rb:205:in `dup'
	  in: pathname.rb:205:in `initialize'
	  in: pik/commands/add_command.rb:17:in `new'
	  in: pik/commands/add_command.rb:17:in `add'
	  in: pik/commands/add_command.rb:13:in `execute'
	  in: pik_runner:27

調べたところ、rubyが全くない環境で動かすと発生するらしい → [pik を使って Windows に ruby をインストール - miauの避難所][1]

rubyをインストールすれば回避できるらしいが、そもそもpikを使ってrubyをインストールしようとしているのに、それを動かすためにrubyが必要というのでは本末転倒なので、違う方法での回避を試みる。

回避方法も上のページに書いてある。ダミーのエントリを作って、1つでもrubyがインストールされているように見せかければよいらしい。


%HOME%/.pik/config.ymlを作成してダミーを作成しておく。

	---
	"000: ruby 0.0.0 (dummy ruby for pik)":
	  :path: !ruby/object:Pathname
	    path: C:/pik/dummy
	--- {}

これでpikが動くようになる。

[1]: http://d.hatena.ne.jp/miau/20110106/1294325095

  ---------------------------------------------------------------------

rubyインストール
================
pikが動作するようになったので、pik経由でrubyをインストールする。現時点での最新の安定版1.9.3-p125を入れる。

	$ pik install ruby 1.9.3-p125

インストールが完了したらconfig.ymlを編集してダミーのエントリを削除しておく。
