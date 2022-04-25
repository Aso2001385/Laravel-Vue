# Laravel-Vue

## 環境構築手順

### リポジトリをcloneする
* Githubでリポジトリのページを開く
    * `Code`からURLをコピーする
* 以下のコマンドを実行し、リポジトリをクローンする
```
git clone コピーしたURL
```

### イメージの構築（buid）
* 作業ディレクトリに移動する
 ```
 cd ~/`作業ﾃﾞｨﾚｸﾄﾘ名
 ```
* 以下のコマンドを実行してビルドする
```
docker compose build
```
* 以下のコマンドを実行してコンテナを起動する
```
docker compose up -d
```
* 以下のように表示されていればOK
```
[+] Running 3/3
 ⠿ Container docker-laravel-vue_db_1    Started     6.4s
 ⠿ Container docker-laravel-vue_app_1   Started     5.0s
 ⠿ Container docker-laravel-vue_web_1   Started
```

### Composerのバージョン確認

* 以下のコマンドを実行してappコンテナに移動
```
docker compose exec app bash
```
* 以下のように`/var/www/html`ディレクトリに入っていればOK
```
root@81d2cea8efe2:/var/www/html#
```
* 以下のコマンドを実行してバージョンを確認
```
composer -V
```
* 以下のような表示になっていればOK
```
Composer version 2.0.13 2021-04-27 13:11:08
```

### Laravelのインストール
* `/var/www/html`ディレクトリのまま以下のコマンドを実行
```
composer create-project --prefer-dist "laravel/laravel=8.*" .
```
* localhost:80にアクセスする
    * ウェルカムページが表示されればOK

### Vue.jsのインストール
* `/var/www/html`ディレクトリのまま以下のコマンドを実行
```
npm -v
```
* npmバージョンが表示されていたらOK
* 以下のコマンドを実行
```
npm install -D vue
```
* 以下のような表示になっていればOK
```
+ vue-template-compiler@2.6.12
added 3 packages from 2 contributors and audited 4 packages in 1.553s
found 0 vulnerabilities
```
* 念のため`package.json`というファイルの中に以下の記述があるか確認
```
"vue": "^2.6.12",
"vue-template-compiler": "^2.6.12"
```
