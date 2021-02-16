# Marmot GitLab VM上で GitLabを構築するAnsibleプレイブック

## 概要

これはLinuxの QEMU/KVM または Vagrant でGitLabサーバーを構成するAnsibleコードです。


## Vagrantでの使い方

起動

~~~
$ vagrant up
~~~

削除

~~~
$ vagrant destroy
~~~



## QEMU/KVMの起動方法

起動

~~~
$ vm-create -f Qemukvm.yaml
~~~

削除

~~~
$ vm-destroy -f Qemukvm.yaml
~~~


## ウェブUI

1 ブラウザで https://gitlab.labo.local/ をアクセスして、

2 初期パスワードを設定して、root でログインする。

3 スパナの形をしたアイコン(Admin Area) をクリック
4 左のメニューのUsersをクリック
5 右端グリーンの[ New user ]アイコンをクリック
6 ユーザー名など登録、仮パスワードをセット
7 rootをSign out
8 追加したユーザー名でログイン、本パスワードをセット
9 右端のユーザー Settingsをクリック
10 SSH keys をクリック
11 Key のフィールドに、id_rsa.pubの内容をペースト [Add key]をクリック


## 


