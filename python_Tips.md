# Python_Tips
* 以下のようにすると、Noneの値がn個格納されたリストができる。  
`sample = [None] * n`

```
In [3]: sample = [None] * 2

In [4]: sample
Out[4]: [None, None]
```

* 引数で渡したファイル名が絶対パスかどうか調べる  
`os.path.isabs`で絶対パスかどうか調べられるので、これを使う

```
if os.path.isabs(args[1]):
    # 絶対パスだった時の処理
else:
    #絶対パスじゃなかった時の処理
```

* 相対パスをスクリプトファイルからの絶対パスに変換する

```
script_dir = os.path.dirname(os.path.abspath(__file__))
abspath = os.path.realpath(os.path.join(script_dir, "relative_path"))
```

* batファイルで指定した引数をPythonスクリプトに渡す

```
実行するPythonスクリプト名の後に「 %* 」を付ける。
こうすることでバッチファイル側で指定したすべての引数を見ることができる
※ %1~%9でも見ることはできるが、この場合は９つの引数までしか見ることができない。
```
