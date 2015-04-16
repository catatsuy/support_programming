# pixivエンジニアが教えるプログラミング入門サポートページ

実際に作る画像投稿掲示板

  * [catatsuy/sinatra_keijiban](https://github.com/catatsuy/sinatra_keijiban)
  * [catatsuy/sinatra_simple](https://github.com/catatsuy/sinatra_simple)

## 第1章 Web サイト作りの基本のキ

  * [index.html](https://github.com/catatsuy/support_programming/blob/master/index.html)
  * [style.css](https://github.com/catatsuy/support_programming/blob/master/style.css)

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

名前・メールアドレス

    git config --global user.name "catatsuy"
    git config --global user.email "catatsuy@catatsuy.org"

名前とメールアドレスは GitHub に登録したものを使ってください


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

```rb
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

```js
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

```html
<script src="/js/jquery.js"></script>
```

```js
$(function() {
  // ここに処理を書く
});
```

## sinatra-contribをインストールしてサーバーが起動しなくなった方

2015/3/24 に sinatra のバージョンアップがあり，それに 2015/04/16 現在 sinatra-contrib が追従していません

以下の手順で回避できます

  1. `sudo gem uninstall tilt` とターミナルに入力
  2. `Select gem to uninstall:` と出るので `tilt-2.0.1` の左に書かれている数字を入力して Enter を押す

![uninstall tilt](/uninstall_tilt.png)
