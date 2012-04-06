---
layout: post
title: "pik環境へのDevKitインストール"
date: 2012-04-06 02:35
comments: true
categories: [ruby, install, pik, devkit, windows]
---

DevKitのインストール
====================
Vagrantが依存するgemの中にコンパイルを必要とするものがあるため、DevKitをインストールしておく必要がある。

- [DevKit][1]
- [Development Kit · oneclick/rubyinstaller Wiki][2]


ファイルの用意
--------------
[ダウンロードページ][3]から、自己解凍型のファイル(DevKit-tdm-32-4.5.2-20111229-1559-sfx.exe)をダウンロードする。ダウンロードしたファイルを実行すると解凍先を聞かれるので適当に指定する。このとき指定したフォルダに全ファイルがそのまま展開されてしまうので、空のフォルダを作ってそこに展開した方がいい。

展開されたすべてのファイルをまとめて適当なフォルダに移動しておく → とりあえず C:\dev\DevKit-tdm-32-4.5.2 へ。

[1]: http://rubyinstaller.org/add-ons/devkit/
[2]: https://github.com/oneclick/rubyinstaller/wiki/Development-Kit
[3]: http://rubyinstaller.org/downloads/


インストールスクリプトの実行
----------------------------
DevKitファイルを移動した先のフォルダでコマンドを実行する。

	$ ruby dk.rb init

config.ymlファイルができあがるけど中身が空なので、pikでインストールしたrubyのパスを追記する。

	- C:\Users\ユーザ名\.pik\rubies\Ruby-193-p125

後は内容をチェックして問題なければインストールして完了。

	$ ruby dk.rb review
	$ ruby dk.rc install

DevKitの動作確認
----------------
[DevKitのページ][2]に書いてあるサンプルを動かしてみて、正しくインストールされているかどうかを確認する。

	$ gem install rdiscount --platform=ruby
	Fetching: rdiscount-1.6.8.gem (100%)
	Temporarily enhancing PATH to include DevKit...
	Building native extensions.  This could take a while...
	Successfully installed rdiscount-1.6.8
	1 gem installed
	Installing ri documentation for rdiscount-1.6.8...
	Installing RDoc documentation for rdiscount-1.6.8...

"Temporarily enhancing PATH to include DevKit..."というメッセージが表示されていれば、DevKitが正常に動いているはず。
