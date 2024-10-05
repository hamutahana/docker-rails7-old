## docker-rails7の作成手順
- docker-rails7ディレクトリを作成

- docker-rails7ディレクトリに移動する

- Ruby3.2.2がインストールされたコンテナを起動してシェルを起動する
```sh
# Macの場合
docker run --rm -ti -v ./rails-practice:/app ruby:3.2.2-alpine sh
# Windowsの場合
docker run --rm -ti -v "$(pwd)/boards:/app" ruby:3.2.2-alpine sh
```

- パッケージリストを更新する
```sh
apk update
```

- Railsでアプリケーションを作成する際に必要なパッケージをインストールする
```sh
apk add g++ make mysql-dev
```


- RubyGemシステム（gemそのもの）をアップデートする
```sh
gem update --system
```

- Railsのインストールバージョンを指定する
```sh
gem install rails -v 7.0.6
```

- プロジェクトを作成する
```sh
rails new /app --force --database=mysql --skip-bundle --skip-test
```

# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
