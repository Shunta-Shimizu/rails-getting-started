# rails-getting-started
Getting Started with Rails

### 環境構築
- rbenvのインストールなど　https://qiita.com/kodai_0122/items/56168eaec28eb7b1b93b

### Webサーバーの起動
```
bin/rails server
```

### Routing
- `./config/routes.rb`
- rootルーティングの`Get /article` リクエストを`ArticlesController`のindexアクションに割り当てる
```
Rails.application.routes.draw do
  root "articles#index"
  get "/articles", to: "articles#index"

end
```

### データベースマイグレーション
- マイグレーションを実行すると, "articles"という名前のテーブルが作成させる
- title, bodyというカラムを定義
```
bin/rails db:migrate
```

### Railsコンソールの起動
```
bin/rails console
```
