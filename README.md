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

### モデルの生成
```
bin/rails generate model model_name
```

### データベースマイグレーション
```
bin/rails db:migrate
```

### モデルの削除
  - データベースマイグレーションしていない場合
    ```
    bin/rails destroy model model_name
    ```
  - データベースマイグレーションしている場合
    - データベースをrollbackしてから削除する 
    ```
    bin/rails db:rollback
    bin/rails destroy model model_name
    ```

### コントローラの生成
```
bin/rails generate controller model_name
```

### Railsコンソールの起動
```
bin/rails console
```

# 画像をアップロードする機能
 作成したブログ記事のWebアップリケーションに文章だけでなく，画像を掲載できるように機能を追加した．また，自分のPCのフォルダから画像を選択し，複数枚ある場合は横並びで表示させるようにした．
画像は，記事の新規作成，編集時にアップロード可能．
### セットアップ
- Active Storageを使用
```
brew install imagemagick
```

- Gemfileを編集．以下の2つを追記し，`bundle install`を実行．
```
gem 'mini_magick'
gem 'image_processing'
```
- ActiveStorageのインストール
```
bin/ails active_storage:install
bin/rails db:migrate
```

### 参考文献
- https://takapinosuke.hatenablog.com/entry/2020/10/21/234140
- https://zenn.dev/redheadchloe/articles/6a8d78d0a903a3
- https://qiita.com/oak1331/items/830755889a37ceee1bc6
- https://zenn.dev/tya0116/articles/1d05bb09ad43f0
- https://qiita.com/trafford_777/items/339ac0416b1505fa0fc6
