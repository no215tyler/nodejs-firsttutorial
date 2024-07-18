# 手順
1. モジュールを管理するpackage.jsonファイルを作成
```zsh
npm init -y 
```

2. サーバーを作る
**`server.js`** ファイルを手動で作成する
```zsh
touch server.js
```

3. **`HTTPモジュール`** をインストールする
```zsh
npm install --save-dev http
```
- package-lock.jsonが新たに生成され、
- package.json内にHTTPモジュールに関する記述が自動反映される


〈参考ドキュメント〉https://nodejs.org/api/http.html#http

4. インストールした **`HTTPモジュール`** を **`require`** する

5. **`PORT`** を変数として指定（3000とか8000とか）

6. webサーバーの処理を **`createServer関数`** で作る

7. **`listen関数`** で指定したPORTのサーバーを起動

-----

# サーバーの立て方
現場ではターミナルで **`node server.js`** とするのではなく、package.jsonの **`scripts`** から呼び出す。
1. package.jsonの **`scripts`** 内を修正する
```json
"scripts": {
  "start": "node server.js"
}
```
2. ターミナルで以下のコマンドを打つことでサーバーが起動する
```zsh
npm run start
```
- npm run に続く文言はpackage.jsonの **`scripts`** 内のkeyに準拠

## サーバーを自動リロード化する
1. 以下のnpmコマンドを実行
```zsh
npm install --save-dev nodemon
```
2. package.jsonの **`scripts`** 内を修正する（ **`nodemon`** ）
```json
"scripts": {
  "start": "nodemon --ext js,html server.js"
}
```
