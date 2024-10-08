## dockerコンテナ生成手順
```bash
# イメージを生成
docker-compose build

# コンテナを生成・軌道
docker-compose up
```


## docker-rails7環境の作成手順
```bash
# docker-rails7ディレクトリの作成
mkdir docker-rails7/

#docker-rails7ディレクトリに移動
cd docker-rails7

# Ruby3.2.2がインストールされたコンテナを起動してシェルを起動
# Macの場合
docker run --rm -ti -v ./rails-practice:/app ruby:3.2.2-alpine sh
# Windowsの場合
docker run --rm -ti -v "$(pwd)/boards:/app" ruby:3.2.2-alpine sh

# パッケージリストを更新する
apk update

# Railsでアプリケーションを作成する際に必要なパッケージをインストールする
apk add g++ make mysql-dev tzdata

# RubyGemシステム（gemそのもの）をアップデートする
gem update --system

# Railsのインストールバージョンを指定する
gem install rails -v 7.0.6

# プロジェクトを作成する
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
