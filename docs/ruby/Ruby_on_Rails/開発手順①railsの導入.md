## 前準備(Macの場合)

* railsをインストールする
* rbenv, ruby-buildをインストールする
* mysqlをインストールする
* bundlerをインストールする

```bash
# homebrewで各種ソフトウェアを追加する
brew install mysql
brew install rbenv
brew install ruby-build

# ruby2.5.1をインストールする
rbenv install 2.5.1
# rubyのバージョンを2.5.1に指定する
rbenv local 2.5.1
# rubyのバージョンの確認
rbenv versions

# bundlerをインスールする
gem install bundler
```

## railsプロジェクトを作成する

```bash
rails new rails_app --database=mysql --skip-bundle
```

* --databaseオプションを指定しない場合はSQLiteになる
* --skip-bundleオプションをつけると、最初の `bundle install` をスキップする
* --skip-testオプションをつけると、テストコードを作成しない

## プロジェクトで使用するdbを作成する

```bash
# dbを作成する
rails db:create
# mysqlにログインして確認する
rails db
mysql> show databases;
```

## gitの初期設定と最初のコミットを行う

* 事前にGitHubやGitLabでリポジトリを作成しておく

```git
git init
git remote add origin [リポジトリ名]
git add .
git commit -m "Start [rails_app] project"
```
