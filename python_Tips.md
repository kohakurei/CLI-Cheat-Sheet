# Python_Tips
以下のようにすると、Noneの値がn個格納されたリストができる。  
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
