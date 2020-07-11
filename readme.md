# Speedy

Development environment for static pages using Gulp - Pug & Sass & browser-sync & babelify & browserify

SPEEDY = Static Pug Easy Early Develop YAT

## 依存アプリケーション等

* [npm](https://www.npmjs.com/)
* [gulp](http://gulpjs.com/)
* [normalize.css](https://necolas.github.io/normalize.css/)
* [sass](http://sass-lang.com/)
* [pug](https://pugjs.org/language/conditionals.html)

* Node version v12.13.1 or more
* Gulp 4

## 設定ファイル

* .editorcoding 文字コード設定


### インストール

#### npmインストール
` npm install `

### Usage

* 開発を行うファイルはdevディレクトリの中に入れてください。
* htmlの吐き出し元となる、pugファイルをpugフォルダの中にいれて開発してください。監視中、pugフォルダのファイルが更新されると、devフォルダに吐き出されます。
  * 例）dev/pug/index.pug → dev/index.html
* `index.pug`、レイアウトテンプレート用の`_layout.pug`、共通テンプレート用の`_head.pug`、`_header.pug`、`_foot.pug`、スクリプト読み込み用の`_script.pug` を入れています。
* コンパイル時にcss、jsファイルは結合されます。デフォルトで入っているものを利用すれば、コンパイル時の書き出しの設定をコメントにして入れています。
  * JavaScriptは必要となるモジュール用にファイルを作成し、`main.js`で`require`してください。コンパイル時`bundle.js`として`dev/js/`の中に吐き出されます。
  * cssファイルは開発用にscssファイルが`dev/styles/`の中に入っています。吐き出し先は`dev/css/common.css`となり、同時にmapファイルが吐き出されます。
* リセットにnormalize を使用しています。
* 開発が終わったら、 `npx gulp build` コマンドを利用し、devフォルダに吐出さているファイルを元に、htdocsのフォルダに全ファイルが吐出されます。
  * 例）dev/index.html → htdocs/index.html
* scss ディレクトリはFLOCSSを元に構成しています。お好みで構成を変えてください。[FLOCSSについてはこちら](https://github.com/hiloki/flocss)
* サイト情報は`json`で管理。ファイルは`dev/pug/_data/site.json` の内容を編集することで、meta情報等を一括で編集が可能です。
* Gulpのlocals.relativePathにて各ページのルートパスを取得しています。

readmore [link:yatのBlog](https://wp.yat-net.com/?p=5898)

### 起動コマンド
gulp 4 への移行によりコマンドを npx 推奨としています。
` npx gulp `　- defaultで設定しているtaskが起動する

` npx build `　- htdocsへの吐き出し。ドキュメントルートへ設置用ファイル

` npx gulp *** ` - *** のtaskを起動する

### Author

YAT [http://wp.yat-net.com](http://wp.yat-net.com)

#### 2.1.1
* Node の対応バージョンを12.13.1にアップデート

#### 2.0.1
* JavaScriptファイルの監視バグ修正

#### 2.0.0
* Gulp 4 に対応

#### 1.7
* babel-coreを追加しました

#### 1.6
* 各種モジュールをアップデートしました

#### 1.5
* グローバルナビゲーションを追加 アクティブクラスが付くようになっています

#### 1.4
* モジュールのアップデート

#### 1.3
* normalize.css をpug側で読み込むように変更。normalizeのバージョンアップ

#### 1.2
* add path 追加。ルートパス情報取得

#### 1.1
* add favicon

#### 1.0
* First release