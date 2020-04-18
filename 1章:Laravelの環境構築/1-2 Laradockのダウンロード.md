# Laradockをインストール！

[![Image from Gyazo](https://i.gyazo.com/d2fc7f7d43efa72ae513295c110d4a93.png)](https://gyazo.com/d2fc7f7d43efa72ae513295c110d4a93)


今回の章ではLaradockというDocker環境でLaravelを動かすためのバラエティパックのようなものをインストールします。

まずはそのLaradockを落とすためのフォルダを作成していきたいと思います。

### 開発するためのフォルダの作成。

まずは自分がLaravelのフォルダを保存したいところまでコマンドを使って移動します。

まずは、一旦ルートディレクトリに移動します。

```
cd
```
だけですぐに移動ですね。

```
ls
```
を押すと見慣れたファイル群が存在してると思います。

この教材ではオーソドックスにここにある
「Documents」のなかにLaravelと言うフォルダを作成し、その中でLaradockをインストール、同じ階層にECappという名前でLaravelフォルダを作成しアプリ開発を進めて行きたいと思います。
(Nuxt.jsの配置は後ほど説明します。)

分かりやすくするとこう言うことです。

```
Documents
└── Laravel
    └── Laradock
    └── ECapp
```


ECappの方は自分の好きな名前でフォルダを作ってもらっても構いませんが、Dockerの環境ファイル等でフォルダを指定したりしますので初心者の方は無難に教材通りに進行することをお勧めします。

それではまずは

```
cd Documents
```
でDocumentsに移動してください。
これでDocumentsフォルダ内に移動することができました。

次にLaravelと言うフォルダを作成します。

作成にはmkdirコマンドを使用します。

```
mkdir Laravel
```
これでLaravelフォルダが完成しました。
偉そうに書いていますが、右クリックで「新規フォルダの作成」と同じことをやっています。

ただこっちの方が慣れると楽ですので、もし慣れていない方はこの機会に慣れていってみてください。

今作ったLaravelフォルダに移動します。

```
cd Laravel
```

ここで、

```
ls
```
を打つともちろん何も入っていません。
ここにLaradock（環境側サーバー・DB）とECapp（実際のLaravelフォルダ）を作成して行きます。

### Laradockって？

それではまずはLaradockをダウンロードしていきたいと思います。

まずそもそもLaradockとは何か？と言うのを説明するとLaravelをDocker環境で簡単に使用できるようにしてくれている何でも入っているファイル群です。

Dockerという仮想環境を使う際にはDockerFileやdocker-compose.yamlなどの簡単に言うと設計図・指示書のようなものが必要です。

これを１から作るとなるとDocker自体の知識も必要となり非常にコストがかかってしまいますが、そこをカバーしていきなりLaravelを動かす環境（今回の教材ではNginx/Mysql/phpMyadmin/Mailhogなど）を提供してくれるのがLaradockです。


必要のない環境を多数保持しているLaradockですのでそこにクレームが入ることもありますが、
世界各国のエンジニアが有志でDockerのバージョンなどに合わしてこのDockerFileなどの環境を更新し
、すぐに使える状態にしてくれていることを考えると非常に有用な存在ではないでしょうか。

### いよいよLaradockをダウンロードします！

それでは実際にインストールします。
インストール自体は簡単です。（ネット環境が遅すぎると時間がかかりますので注意してください）

laravelフォルダ上で、

```
git clone https://github.com/laradock/laradock.git
```

これだけでインストールが始まります。
少し時間がって以下が表示されます。

```
Cloning into 'laradock'...
remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (5/5), done.
remote: Total 10378 (delta 1), reused 5 (delta 1), pack-reused 10372
Receiving objects: 100% (10378/10378), 9.30 MiB | 998.00 KiB/s, done.
Resolving deltas: 100% (5623/5623), done.
```
これでLaradockがダウンロードされました。
laravelフォルダで

```
ls
```
を押すとlaradockと言うフォルダが存在するのが分かると思います。

それでは次の章でlaradockの設定を行って行きたいと思います！