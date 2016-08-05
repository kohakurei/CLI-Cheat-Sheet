Vagrantのコマンドラインチートシート
===============================

Vagrantで仮想マシン立ち上げ後に再度プロビジョナーを実行する場合は、`vagrant provision`で実行できる。  
この時、Vagrantfileの中で複数の形式でプロビジョナーを定義している場合、例えば`ansible_local`のプロビジョナーのみを実行したい場合は
`--provision-with`オプションを指定して実行する。
```
vagrant provision --provision-with ansible_local
```
とすれば、`ansible_local`のプロビジョナーだけが実行される。
