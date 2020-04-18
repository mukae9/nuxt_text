# Laradockの設定を行おう

前章で簡単にLaradockをダウンロードしましたが、ここから設定を変更していく必要があります。

少し複雑な部分もありますのでこの教材ではなるべく簡単に設定の変更が行えるような道筋で説明をしています。

Laradockに慣れてきたら自分でより詳細な設定にもチャレンジしてみてください。

### 舞台をVscodeに移します

ここからはファイルの変更等がありますので、少しでも分かりやすく行うためにVscodeも使用して行きます。
LaravelフォルダをVscodeで開いて行きましょう。

Vscodeを開き、左上のファイルが二重になっているアイコンをクリックしてください。
（最初から下の画像のようになっている場合もあります。）

[![Image from Gyazo](https://i.gyazo.com/0347eda8a4757a7a3a5f2276d321c966.png)](https://gyazo.com/0347eda8a4757a7a3a5f2276d321c966)


フォルダから開くを選択して前章で作ったLaravelフォルダを開きます。
[![Image from Gyazo](https://i.gyazo.com/d0b3f12ba162b37c3da251c525c1ec84.png)](https://gyazo.com/d0b3f12ba162b37c3da251c525c1ec84)

Laravelフォルダが無事に開けましたね。
[![Image from Gyazo](https://i.gyazo.com/84eea25e2fc647fcc8d49ddd49412200.png)](https://gyazo.com/84eea25e2fc647fcc8d49ddd49412200)

laradockフォルダにすごい量のフォルダがあることも確認できます。
（今回の教材では一部しか触りませんのでご安心ください）


### laradockの環境設定を行います

まずはlaradockフォルダで「右クリック」→「ターミナルで開く」を選択して下さい。
[![Image from Gyazo](https://i.gyazo.com/60782a2d3c24b1e9a4e803ff7baf0e9b.png)](https://gyazo.com/60782a2d3c24b1e9a4e803ff7baf0e9b)

すると右下にターミナルが開きました。
便利なことに最初からlaradockフォルダに居てくれてますのでcdなどを使って移動する手間が省けますね。

[![Image from Gyazo](https://i.gyazo.com/ddb87662b1bc0f81565ff64bf958a04d.png)](https://gyazo.com/ddb87662b1bc0f81565ff64bf958a04d)

それでは設定していきましょう。

### .envファイルを作成する

laradockフォルダ上で

```
$ cp env-example .env
```
を打ちます。

env-exampleファイルは最初からlaradockが準備してくれている環境設定のためのexampleファイルです。
これを .envという名前で複製してします。

```
ls -a
```
を打つとlaradockフォルダに.envファイルが作成することが分かると思います。
なお、.envの「.」は隠しファイルであることを表しています。
それだけ大事な情報をここには書きます。（例えばデータベースのパスワードとか）
なのでlsだけではこのファイルは表示されず-aをつけてあげると表示されます。


複製が完了したところで、
.envをクリックしてファイルを表示させてみましょう。

[![Image from Gyazo](https://i.gyazo.com/2e87141f5e269d8c6afd4ac3b82f1ccd.png)](https://gyazo.com/2e87141f5e269d8c6afd4ac3b82f1ccd)

記述が多すぎて絶望しそうですが、
基本的には編集する必要はありません。
1点だけ確認を行います。

以下「PHP MY ADMIN」の箇所を探してください。
command+fで検索できますので、PHP MY ADMINで探せばすぐに見つけられるかと思います。

```
### PHP MY ADMIN ##########################################

# Accepted values: mariadb - mysql

PMA_DB_ENGINE=mysql

# Credentials/Port:

PMA_USER=default
PMA_PASSWORD=secret
PMA_ROOT_PASSWORD=secret
PMA_PORT=8080

```

上記のPMA_PORT=8080と言う部分を、

```
PMA_PORT=8081
```
に変更してください。

また、もしPMA_USER、PMA_PASSWORD、PMA_ROOT_PASSWORDの値が上記の値と違った場合は
下記のように書き換えてください。

```
PMA_USER=default
PMA_PASSWORD=secret
PMA_ROOT_PASSWORD=secret
```

最終的に以下のようになります。

```
### PHP MY ADMIN ##########################################

# Accepted values: mariadb - mysql

PMA_DB_ENGINE=mysql

# Credentials/Port:

PMA_USER=default
PMA_PASSWORD=secret
PMA_ROOT_PASSWORD=secret
PMA_PORT=8081

```
これで.envの環境の作成と確認は終了です。

### nginxの設定

laradockの設定もこれで最後です！
laradockフォルダの中から
nginx/sites/default.confを画像を参考に開いて下さい。

[![Image from Gyazo](https://i.gyazo.com/3da71f1304b72e275c1e2db31ac795f9.png)](https://gyazo.com/3da71f1304b72e275c1e2db31ac795f9)

また色々と書いてありますが、
編集する場所は一部です。

まずこちらの記述を編集します。13行目くらいにあります。

```
    root /var/www/public;
```
こちらの記述を、

```
    root /var/www/ECapp/public;
```
に変更します。

ECappというのは、次の章で作成するLaravel自体のフォルダの名前です。
ここを変更する場合は連動して次の章のフォルダの名前も変える必要がありますので注意してください。
（以降の説明もECappという名称で説明しますので初心者の方は無難にECappでいいかと思います。）

これでnginxがlocalhostにアクセスされた際に
ECapp/publicを見に行ってくれるような設定になりました。
ECapp/publicとは具体的には次章で落とすLaravelフォルダの中にあるpublicフォルダのindex.phpの事です。

### Dockerのコンテナを立ち上げる

laradockの調整も完了したので、実際にDockerのコンテナ(環境)を立ち上げましょう！
（ネット環境が悪いとこだと時間がかかりすぎるので注意！）

まずはDockerアプリの再起動を行います。
パソコンの画面右上にクジラのマークがあるかと思いますが、
画像の通りrestartを押してください。

[![Image from Gyazo](https://i.gyazo.com/db4d4b0a826864a833c2806d18c70046.png)](https://gyazo.com/db4d4b0a826864a833c2806d18c70046)

上記で変更した点を反映させます。

もしクジラのマークが無い方は、launchpadなどからDockerを起動させるだけで大丈夫です。

Dockerの立ち上げを

laradockフォルダ上で、以下のコマンドを打ちます。

```
$ docker-compose up -d nginx mysql phpmyadmin
```
dockerに慣れてない方はこのコマンドは今は謎かと思いますが、
簡単に言うとlaradockに準備されているnginxとMysql、phpmyadminの情報をもとにこれらのコンテナ（環境）を構築して！と言う命令になります。

```
ERROR: Couldn't connect to Docker daemon. You might need to start Docker for Mac.
```

って出た方はDockerサービス自体の起動を忘れてるだけだったり、Dockerがまだ起動完了していないだけです。落ち着いてもう一度コマンドを打つか、macのアプリケーションにあるDockerを起動してください。

うまくいった方は環境の構築が始まるかと思います。

数分経って、、、

[![Image from Gyazo](https://i.gyazo.com/213ae3f5820f756f0025deacfabd6199.png)](https://gyazo.com/213ae3f5820f756f0025deacfabd6199)

こちらが表示されたらサーバー/MySQL/phpMyadminが動き始めています。

もし、mysqlなどがExitとなった方は、
XAMPPやMAMP、他のDockerが起動していませんか？？
ポートが被っているのが原因なことが多いです！90%はそうです！
全てOFFにして、再度docker-compose up -d nginx mysql phpmyadminをすると動くと思います。

### 立ち上げた環境を確認する

それでは、
試しに

http://localhost/

にアクセスしてみましょう。

[![Image from Gyazo](https://i.gyazo.com/b5a5fea9e35fd0092e5bda6652ea63b6.png)](https://gyazo.com/b5a5fea9e35fd0092e5bda6652ea63b6)

しっかり404 Not Foundが出たでしょうか？
まだ表示させるファイルを作っていないのでファイルが無いと言われるのは当然なのですが、
小さくnginxと書いていることでサーバーが稼働していることがわかります。

続いて

http://localhost:8081/

にアクセスしてみましょう。

[![Image from Gyazo](https://i.gyazo.com/4d736e291094c6ff464530048572c413.png)](https://gyazo.com/4d736e291094c6ff464530048572c413)

phpMyadminが表示されましたね。

先ほどのlaradockの.envファイルで確認した値を入力すればログインも出来ます。
今回教材通り進めてくれている方は

サーバー：mysql
ユーザー名:default
パスワード:secret

でログインが可能です。

[![Image from Gyazo](https://i.gyazo.com/e96e848030834f8fa9d6d2abc817c681.png)](https://gyazo.com/e96e848030834f8fa9d6d2abc817c681)

真っさらなデータベースが確認できました。一緒に立ち上げたMySQLもちゃんと構築できた証拠ですね。

これで今回の教材で必要な環境を構築することが出来ました。

初心者の方の勘違いが多い点としては、
LaradockはあくまでLaravel自体ではなく、Laravelで使う環境を提供しているだけです。

今の段階では一切Laravelのことは触っていません。
全く別のものですので今は「Laravelを動かすための土台が作れたんだな」と認識してもらえたらと思います。

また、Dockerという技術を使うことでこんなにも早く「他人が作った設計書」をもとにLaravelを動かすローカル環境を構築することが出来ました。

10人いる開発チームがあるとしたら、
もしこれがXamppとかですと一人一人が0からダウンロードや編集を繰り返す必要があります。
おそらくPCに導入しているソフトの違いなどで思わぬエラーも発生するでしょう。

しかしDockerですとLaradockのように必要な情報を共有し微調整するだけで簡単に10人が全く同じ開発環境を作り出すことが出来ます。

チーム開発時に重宝される理由が分かりますね。

それでは、Laravelを動かす環境が構築できましたので
次の章でLaravel自体をインストールしていきたいと思います。