RailsGirls福岡ワークショップ
===================

# 目的 #

# 前提 #
| ソフトウェア   | バージョン   | 備考        |
|:---------------|:-------------|:------------|
| ruby           |2.4.0    |             |
| rails          |5.0.2    |             |
| vagrant        |1.8.7    |             |
| docker         |1.12.5    |             |
| docker-compose |1.8.0    |             |

# 構成 #
1. [構築](#構築)
1. [開発](#開発)
1. [配置](#配置)

## 構築
### 「 Rails インストールガイド」で,Ruby,Ruby on Rails,テキストエディタをインストール
#### 仮想マシンの起動とログイン
```bash
$ vagrant up
$ vagrant ssh
$ cd /vagrant
```

#### Railsのインストール
```bash
$ gem install rails --no-document
```

#### テキストエディタをインストール
+ [ATOM](https://atom.io/)
+ [Sublime Text](https://www.sublimetext.com/)
+ [Visual Studio Code](http://railsgirls.jp/install)

### 簡単な動作確認 (rails new 、 rails g scaffold コマンドがエラーなく終了するところまで)
```bash
$ cd /vagrant
$ rails new railsgirls
$ cd railsgirls
$ rails server -b 0.0.0.0
```
[http://localhost:3000/](http://localhost:3000/)に接続して動作を確認する。
確認できたらCtr-cで動作を停止する。

### ブラウザ(Google Chrome)インストール
[https://www.google.co.jp/chrome/browser/desktop/](https://www.google.co.jp/chrome/browser/desktop/)

### GitHub アカウント取得
[https://github.com/](https://github.com/)

### アプリケーション開発の準備
#### サンプルアプリケーションをスキャッフォルドで作成する
```bash
$ cd /vagrant/railsgirls
$ rails g scaffold sample comment:string
$ bin/rails db:migrate
$ rails server -b 0.0.0.0
```
[http://localhost:3000/samples](http://localhost:3000/samples)に接続して動作を確認する。
確認できたらCtr-cで動作を停止してアプリケーションを削除する
```bash
$ cd ..
$ rm -rf railsgirls
```

#### サンプルアプリケーションをデバッグできるようにする(Visual Studio Code)
`Gemfile`に以下のGemを追加して`bundle install`を実行する
```ruby
  gem 'better_errors'
  gem 'binding_of_caller'
  gem 'ruby-debug-ide'
  gem 'debase'
```

Visual Studio Codeに構成を追加する

```bash
bundle exec rdebug-ide --host 0.0.0.0 --port 1234 --dispatcher-port 26162 -- bin/rails s -b 0.0.0.0
```
Visual Studio Codeでブレークポイントを設定してListen for rdebug-ideを実行する
注意：仮想マシン経由だとブレークポイントにうまくアタッチされないのでローカルで実行する

**[⬆ back to top](#構成)**

## 開発
### A.「はじめてのRails アプリ」 「アプリにページを追加する」まで

### B.「あなた アプリをインターネットに公開しよう -heroku-」 完了

### C.「GitHub であなた アプリ コードを公開しよう」 で GitHub にコードを公開するまで
**[⬆ back to top](#構成)**

## 配置
**[⬆ back to top](#構成)**

# 参照 #
+ [Rails Girls ガイド](http://railsgirls.jp/)
+ [Rails Girls インストール・レシピ](http://railsgirls.jp/install)
