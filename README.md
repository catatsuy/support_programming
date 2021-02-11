# pixivエンジニアが教えるプログラミング入門サポートページ

実際に作る画像投稿掲示板

  * [catatsuy/sinatra_keijiban](https://github.com/catatsuy/sinatra_keijiban)
  * [catatsuy/sinatra_simple](https://github.com/catatsuy/sinatra_simple)

## 正誤表

| 正誤箇所 | 誤 | 正 |
| :------------ | :--------------- | :----- |
| 88ページ      | `cd sinatra_simple_template` でこのフォルダに入って | `cd sinatra_simple` でこのフォルダに入って |
| 134ページ下   | `js:main.js` | （必要なし） |


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

#### Ruby から SQLite を操作する

本書の例を表示するための `INSERT` 文

```sql
INSERT INTO books (title, author, price) VALUES ('武器としての交渉思考', '瀧本哲史', 860);
INSERT INTO books (title, author, price) VALUES ('キャバ嬢の社会学', '北条かや', 820);
INSERT INTO books (title, author, price) VALUES ('２０歳の自分に受けさせたい文章講義', '古賀史健', 840);
```


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

## Visual Studio Codeを使う

2021/02/11現在、Sublime TextよりもVisual Studio Codeの方がメジャーなエディタだと思います。簡単に使い方を紹介します。

https://code.visualstudio.com/

こちらからダウンロードします。

インデントを調整する機能も使えます。⌘キー・Shiftキー・Pを同時に押して、"format"と入力すると様々な機能を選択できるようになるので、"Format Document"を選択してください。そうすればインデントを調整できます。

Rubyのコードのインデントを調整するには別途プラグインのインストールが必要になります。Visual Studio Codeが提案してくれるので、提案通りにインストールすれば使用できます。

## M1 Mac

Apple M1チップが使われたMacが2020年末から発売されています。M1チップのMacで開発するのは数年間は難しい状況が続くと思われるので、初心者の人は避けてください。

## sinatra-contribをインストールしてサーバーが起動しなくなった方

2015/3/24 に sinatra のバージョンアップがあり，それに 2015/06/06 まで sinatra-contrib が追従していませんでした。2015/3/24 から 2015/06/06 までに `gem install sinatra-contrib` をした方は以下の手順を行う必要があります。

  1. `sudo gem uninstall tilt` とターミナルに入力
  2. `Select gem to uninstall:` と出るので `tilt-2.0.1` の左に書かれている数字を入力して Enter を押す

![uninstall tilt](/uninstall_tilt.png)

2015/06/07 現在この手順は必要ありません。
