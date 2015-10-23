OpenSSH チートシート
==============================

* エージェントフォワードする方法
ssh-keygenで秘密鍵を登録しておき、登録した鍵を転送する。
```
eval `ssh-agent`
ssh-add

ssh -A Host1
```
sshコマンドを利用するときに「-A」オプションを付けるだけ。

* 多段認証でconfigファイルを利用した認証からエージェントフォワードする
手順は同じ。ただしconfigファイルに対して`ForwardAgent yes`を追記しておく。

http://euske.github.io/openssh-jman/ssh_config.html
