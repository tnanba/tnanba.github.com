---
layout: post
title: "Vagrantのインストール"
date: 2012-04-10 01:50
comments: true
categories: [ruby, pik, vagrant, virtualization]
---

ruby(pik)、DevKitと必要な道具がそろったのでVagrantをインストールする。インストール自体はgemからインストールするだけ。

	$ pik use 193
	$ gem install vagrant

インストールできたら、配布されているboxを使って試しに起動してみる。

	$ vagrant box add lucid32 http://files.vagrantup.com/lucid32.box
	$ vagrant init lucid32
	$ vagrant up

LinuxやMacの場合はここで"vagrant ssh"を実行するだけで起動した仮想マシンに接続できるが、Windowsの場合はそれができないので、puttyから接続する必要がある。

- [Vagrant - Getting Started - SSH][1]

接続方法は"vargrant ssh"を実行すると出てくる。

	$ vagrant ssh
	`vagrant ssh` isn't available on the Windows platform. You are still able
	to SSH into the virtual machine if you get a Windows SSH client (such as
	PuTTY). The authentication information is shown below:

	Host: 127.0.0.1
	Port: 2222
	Username: vagrant
	Private key: C:/Users/xxx/.vagrant.d/insecure_private_key

接続に使用する秘密鍵は%HOME%/.vagrant.d/insecure_private_keyにあるが、これはこのままではputtyで使用できないので、puttygenでputty用に変換しておく必要がある。

あとは表示される設定に従ってputtyで接続するだけ。

確認が終わったら終了させておく。

	$ vagrant destory

[1]: http://vagrantup.com/docs/getting-started/ssh.html
