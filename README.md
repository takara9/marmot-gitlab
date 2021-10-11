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


## rootパスワードのリセット方法

仮想マシンにログインして、GitLabコンテナに対話型シェルを動かして
パスワードリセットコマンドを実行する。

~~~
tkr@hmc:~/marmot-gitlab$ ssh ubuntu@172.16.0.222
docker exec -it gitlab_web_1 bash
root@gitlab:/# gitlab-rake "gitlab:password:reset"
Enter username: root   
Enter password: 
Confirm password: 
Password successfully updated for user with username root.
~~~


## ユーザーの追加方法

1 ハンバーガーメニューのMenu -> Admin　へ進む
2 New user をクリック 権限はadminでユーザーを作成、仮パスワードを設定
3 登録したユーザーで再度ログインして、パスワードをセット
3 sshkey pubを登録する

## プロジェクトを登録

ファイル一個だけのProject test1を作成する


## ユーザーの端末からgit clone

git clone https://gitlab.labo.local/tkr/test1
cd test1

修正して、コミット、プッシュする方法は、GitHubと同じ

