# Hatena-Blog-Theme-Ember-Notes

Ember Notes は、はてなブログのデザインCSSカスタマイズの土台に適したデザインテーマです。

# CSSのダウンロード

最新のバージョンから `ember-notes.css` をダウンロードしてください。

- <https://github.com/hatena/Hatena-Blog-Theme-Ember-Notes/releases>

# セットアップ

SCSSで開発する場合は、下記の手順でリポジトリのcloneとモジュールのインストールを行います。

## 必須コンポーネント

- [Node.js](https://nodejs.org/)

## モジュールのインストール

``` console
$ git clone https://github.com/hatena/Hatena-Blog-Theme-Ember-Notes.git
$ cd Hatena-Blog-Theme-Ember-Notes
$ npm install
```

# テーマ開発の手順

## 開発サーバーの利用

開発サーバーを利用することで、SCSSの変更をリアルタイムにブログに反映させながらテーマの開発を行えます。

まずは[はてなブログ](https://blog.hatena.ne.jp/)の設定を行います。

1. テーマの動作確認に使うブログを1つ用意します。（普段お使いのブログとは別にブログを作成してください。）
2. 1.のブログの「デザイン設定」にアクセスし、「カスタマイズ」タブの「デザインCSS」の内容を下記に置き換えて保存します。
    ``` css
    /* Responsive: yes */
    ```
3. 1.のブログの「設定」->「詳細設定」にアクセスし、「&lt;head&gt;要素にメタデータを追加」を下記に置き換えて保存します。
    ``` html
    <script type="module" src="http://localhost:5173/@vite/client" crossorigin="anonymous"></script>
    <link rel="stylesheet" type="text/css" href="http://localhost:5173/scss/ember-notes.scss" crossorigin="anonymous" />
    ```

つづいて下記のコマンドで、開発サーバーを起動します。`BLOG_DOMAIN_NAME` の部分には、上で用意した動作確認に使うブログのドメイン名 (例: `example.hatenablog.com`) を入力してください。

``` console
$ npm start -- BLOG_DOMAIN_NAME
```

コマンド実行例:

``` console
$ npm start -- example.hatenablog.com
```

以上が完了すると、動作確認用のブログに開発中のテーマが反映されます。ブログにアクセスし、表示を確認しながらテーマの開発を行なってください。

## コンパイル

テーマの開発が完了したら、下記のコマンドでSCSSをコンパイルします。コンパイルの結果は `build/ember-notes.css` に出力されます。

``` console
$ npm run build
```

# 構成

```
ember-notes/
   ├── assets/
   │   └── images/
   │       ├── header
   │       └── source
   ├── build/
   │   └── ember-notes.css
   ├── scss/
   │   ├── ember-notes.scss
   │   └── lib/
   │       ├── _components.scss
   │       ├── _core.scss
   │       ├── _header.scss
   │       └── _variable.scss
   ├── server.js
   └── vite.config.js
```

## License / Copyright

This repository is based on a fork of Hatena's `Hatena-Blog-Theme-Boilerplate`.

- Portions derived from the original boilerplate are subject to the original copyright
  and license notices provided by Hatena.
- Modifications and additions in this repository are Copyright (c) 2026 yassan.

This project is distributed under the MIT License. See `LICENSE.md`.