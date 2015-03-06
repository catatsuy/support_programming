# pixivエンジニアが教えるプログラミング入門サポートページ

実際に作る画像投稿掲示板

  * [catatsuy/sinatra_keijiban](https://github.com/catatsuy/sinatra_keijiban)
  * [catatsuy/sinatra_simple](https://github.com/catatsuy/sinatra_simple)

## 第2章 Macを使った開発環境構築

### ターミナルの開き方

アプリケーション > ユーティリティ > ターミナル.app

#### 覚えて欲しいコマンド

  * `ls`
  * `cd`
  * `open` （Mac 限定）

### Macで開発をできるようにする

    xcode-select --install

### Git / GitHubの使い方

#### Git の便利な設定

    git config --global color.diff   auto
    git config --global color.status auto
    git config --global color.branch auto
    git config --global color.grep   auto
    git config --global core.editor  nano
    git config --global core.excludesfile $HOME/.gitignore
    echo .DS_Store >> $HOME/.gitignore
    echo Thumbs.db >> $HOME/.gitignore

#### Git の覚えて欲しいコマンド

  * `git clone`
  * `git status`
  * `git diff`
  * `git add`
  * `git commit`
  * `git pull`
  * `git push`

## 第5章 実際にコードを書いて画像投稿掲示板を作ろう

### GitHubでリポジトリをForkする

[catatsuy/sinatra_simple](https://github.com/catatsuy/sinatra_simple)

### Rubyの書き方を覚えよう

  * p
  * コメントアウト
    * `#`
  * 変数 (Variable)
  * 配列・ハッシュ (Array/Hash)
    * `[]`, `{}`
  * if
  * each

```rb:main.rb
a = 1
a = a + 3

p a # => 4

array = [1, 4, 9]

p array[0] # => 1
p array[1] # => 4
p array[2] # => 9

hash = {
  "key" => "value",
  "key2" => "value2"
}

p hash["key"] # => "value"

a = 1 + 2

if a == 3
  # もし a が 3 ならここが実行される
  p "1 + 2 は 3 です"
else
  # もし a が 3 ではないならここが実行される
  p "1 + 2 は 3 ではありません"
end

a = [1, 4, 9, 16]

a.each do |x|
  p x
end

# OR

a.each { |x| p x }
```

### SQlite とデータベースの基礎

#### テーブルの作成・確認・削除

  * `CREATE TABLE`
  * `.schema`
  * `DROP TABLE`

#### レコードの追加・確認・更新・削除

  * `INSERT`
  * `SELECT`
  * `UPDATE`
  * `DELETE`

### JavaScriptを覚えよう

```js:main.js
window.onload = function() {
  var hello = 'Hello world!';
  console.log(hello);

  var a = [1, 4, 9];
  console.log(a[0]);

  var h = {
    key: 'value',
    key2: 'value2'
  };
  console.log(h['key']);
};
```

### jQueryを使ってみる

[Download jQuery | jQuery](http://jquery.com/download/)

    <script src="/js/jquery.js"></script>

```js:main.js
$(function() {
  // ここに処理を書く
});
```
