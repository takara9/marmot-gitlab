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


