# Options

| オプション | 説明                              | 引数例          |
| ----- | ------------------------------- | ------------ |
| `-o`  | 出力をファイルに保存                      |              |
| `-O`  | リモートファイル名を使用して保存                |              |
| `-I`  | ヘッダーのみを表示                       |              |
| `-X`  | リクエストメソッドの指定                    | GET POST PUT |
| `-d`  | POSTリクエストで送信するデータ               |              |
| `-H`  | リクエストヘッダーの追加                    |              |
| `-u`  | ユーザー名とパスワードの指定                  |              |
| `-L`  | リダイレクトを追跡                       |              |
| -v    | リクエストしたときのHeaderもみる場合(-Iと似ている。) |              |
|       |                                 |              |
# Examples

HTTPリクエストを使用してデータを取得する
```
curl http://example.com
```
ファイルに保存する
```
curl -o output.html http://example.com
```
リクエストヘッダーを表示する (HEAD)
```
curl -I http://example.com
```
GETのリクエストを送る
```
curl -X GET sample.com
```
POSTリクエストを送信する。
```
curl -X POST -d "name=John&age=25" http://example.com
```
PUTリクエストを送る
```
curl -X PUT sample.com
```

curlでファイルを送る。
```
curl sample.com/uploads/ --upload-file hello.txt
```
ファイルを消す。
```
curl -XDELETE sample.com/uploads/hello.txt
```

JSON形式のリクエストボディを使用したPOST
```
curl -X POST -H "Content-Type: application/json" -d {"name": "John", "age": 25} http://example.com
```
ファイルを使用する場合。
data.json
```
"name": "John"
"age": 25
```

```
curl -X POST -H "Content-Type:application/json" -d @data.json http://example.com
```
