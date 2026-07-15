どのコマンドを実行するときにも必ず末尾は-**「；(セミコロン)」で終わらせること！**
# 起動方法
```
mysql -u root -p -h target.com
```
-u：ユーザー名を指定
-p： パスワードを入力(実行するとパスワードを要求される。)
-h：remoteホストに接続
# データベースの閲覧
データベースの一覧を表示
```
show databases;
```
データベースを選択
```
use [データベース名];
```
# データベースの操作
データベースの作成
```
create database [データベース名];
```
データベースを削除
```
drop database [データベース名];
```

# テーブルの操作
テーブルの一覧を表示
```
show tables;
```
テーブルを作成するコマンド(例)
```
CREATE table non_index_table (id INT AUTO_INCREMENT, num INT, PRIMARY KEY (id));
INSERT INTO non_index_table (num) VALUES ('7084');
INSERT INTO non_index_table (num) VALUES ('1348');
```
テーブルの作成はCREATE文
```
CREATE table [テーブル名] (カラム名 型, カラム名 型, ...);
```
データの追加にはINSERT文
```
INSERT INTO [テーブル名] (カラム名, カラム名) VALUES (値, 値);
```
テーブルの中身を確認する
```
SELECT * FROM [テーブル名];
```
テーブルの削除
```
drop table [テーブル名];
```
データを更新する
```
update [テーブル名] set [カラム名1]=[値1] where  [カラム名2]=[値2];
```
\[テーブル名]の\[カラム名1]=\[値１]の場所の\[カラム名2]を\[値2]に更新する。

# sqlfileの中身を実行
```
source (sqlFile.sqlのアドレス);
```

# テーブルをコピー
```
CREATE TABLE [新しいテーブル名] SELECT * FROM コピー元テーブル;
```