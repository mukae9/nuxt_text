# Laravel7をインストール！

前章までで、Laravelを動かすための環境が整いました。
それでは実際にLaravelのファイル群をインストールしていきましょう。

再確認ですがフォルダの構成はこのようになります。

```
Documents
└── Laravel
    └── Laradock
    └── ECapp
```

つまりこの章ではECappを作成することとなっていきます。

### Laravel7をComposerでインストール

また登場したComposerです。
この人がいないとかなり苦労するのが分かってきたのでは無いでしょうか。

まずはLaravelフォルダへ移動してください。

```
$ ls
```

を打つと
```
laradock
```
だけがあるのが確認できるかと思います。

このLaravelフォルダ上で以下のコマンドを実行しインストールを開始します。
（ネット環境が遅すぎると時間がかかりますので注意してください。）

```
composer create-project laravel/laravel ECapp "7.*"
```
少し反応が遅いですが処理が始まります。

[![Image from Gyazo](https://i.gyazo.com/dd9c8371cafd3bb2ce91a842ee3153c6.png)](https://gyazo.com/dd9c8371cafd3bb2ce91a842ee3153c6)

1分ほど待つと、

[![Image from Gyazo](https://i.gyazo.com/ff882d5939f635ccbba88afd5a58e17a.png)](https://gyazo.com/ff882d5939f635ccbba88afd5a58e17a)

上記のようにインストールが完了します。

再度Laravelフォルダで

```
$ ls
```
を入力すると、

```
ECapp
laradock
```
となっているかと思います。
無事にインストールが完了しましたね。

### データベース接続の設定をしよう

Laravel自体のフォルダ（ECapp）をインストール出来たところで一点だけ変更をします。

LaravelフォルダをVScodeで開いていますので、その中にあるECappフォルダは自動で反映されているかと思います。

（もし反省されていない場合は一度VScodeを再起動してみてください。）

そこからECappフォルダの中の.envをVScodeで開いてください。

また.envが出てきましたがこれは「Laravel側」の環境設定です。前章で調整したLaradockの.envとは全くの別物ですので認識しててください。

ECapp/.envで以下の記述を探します。

```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=
```

そして以下に修正して下さい。

```
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=default
DB_USERNAME=default
DB_PASSWORD=secret
```
Laradockの.envで設定した情報と一致させています。

なんでこんなに.envが出てくるんだと思う方がいるかもしれませんがイメージとしては


Laradockの.envが鍵穴


Laravelの.envが鍵です。


ここが一致するからLaravelのアプリ側からLaradockが構築したデータベースにアクセスする際に許可が出ます。もしここが一致しないとエラーが出てしまうのです。


さて、これでlaravel側の設定も完了しました。
いよいよ表示の確認です！

### Laravelをブラウザで表示しよう

それでは今までの苦労を確かめる瞬間がやってきました。

http://localhost/

にアクセスしてみましょう。


[![Image from Gyazo](https://i.gyazo.com/db4f596de8a8f3fd06b032186872bed7.png)](https://gyazo.com/db4f596de8a8f3fd06b032186872bed7)

表示されましたでしょうか？

残念ながら404 NOT FOUNDの画面になってしまった方は、
1-3 Laradockの設定で調整したnginx/site/default.confをいじった部分をよーーく見てください。
多分そこのミスです！


本当にあなたが作ったLaravelのフォルダ名とdefault.confの情報が一致していますか？
(筆者が決めたECappというフォルダ名から変えているなら、default.confの中身も変える必要がありますよ！）

間違ってた場合は、default.confを編集後に保存してから

laradockフォルダで、

$ docker-compose restart
でコンテナを変更後の情報で再稼働させましょう。

するときっとLaravelのトップページが表示されるはずです！


以上でサーバーサイド側のLaravelの設定は完了しました。

それでは次の章でNuxt.jsのインストールを始めましょう！