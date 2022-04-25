# Laravel-Vue

## 環境構築手順

### イメージの構築（buid）
* 作業ディレクトリに移動する
    * `cd ~/`作業ﾃﾞｨﾚｸﾄﾘ名
* 以下のコマンドを実行してビルドする
    * `docker compose build`
* 以下のコマンドを実行してコンテナを起動する
    * `docker compose up -d`
    * 以下のように表示されていればOK

```
[+] Running 3/3
 ⠿ Container docker-laravel-vue_db_1    Started     6.4s
 ⠿ Container docker-laravel-vue_app_1   Started     5.0s
 ⠿ Container docker-laravel-vue_web_1   Started
```

### Composerのバージョン確認

* 以下のコマンドを実行してappコンテナに移動
    * `docker compose exec app bash`
    * 以下のように`/var/www/html`ディレクトリに入っていればOK
```
root@81d2cea8efe2:/var/www/html#
```
* 以下のコマンドを実行してバージョンを確認
    * `composer -V`
    * 以下のような表示になっていればOK
```
Composer version 2.0.13 2021-04-27 13:11:08
```