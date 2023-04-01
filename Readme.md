# Setup
最初に用意するファイル
- docker-compose.yml
- infra/
- Makefile
- src
※srcは空

下記を実行
```bash
$ mkdir -p src
$ docker compose build
$ docker compose up -d
$ docker compose exec app composer create-project --prefer-dist laravel/laravel . "10.*"
$ docker compose exec app php artisan key:generate
$ docker compose exec app php artisan storage:link
$ docker compose exec app chmod -R 777 storage bootstrap/cache
```

#### DBのセットアップ
接続情報
```
Host: 127.0.0.1
User: phper
Pass: secret
Database: laravel
```


.env
```
DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=phper
DB_PASSWORD=secret
```


.env.testing作成
```
DB_CONNECTION=sqlite
DB_DATABASE=:memory:

```

