bashのコマンドラインチートシート
===============================

* AWS S3コマンドでバケットから特定のディレクトリを出力する
```
aws s3 ls s3://<bucket name> --recursive | awk '{print $NF}' | grep PAN | grep -v -e "^.*\.[a-zA-Z]\{3\}" 
```
[解説]  
*  awk '{print $NF}' で一番最後のカラムを出力
* grep -v -e "^.*\.[a-zA-Z]\{3\}" で任意の拡張子（3文字限定）を持たない行を出力
