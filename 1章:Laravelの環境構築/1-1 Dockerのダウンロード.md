# PHP7.4をインストール！
今回の教材ではLaravel7を使用するためPHP7.2.5以上が必須となります。
LaravelはPHPのフレームワークですので当然にPHPのバージョンの制約を受けることになります。もしPHP7.1などしか入ってない状態でこのLaravel7を使おうとすると、一定の場面でエラーが発生します。
今後もLaravelのバージョンが上がっていくと思いますが、合わせて必要とされるPHPのバージョンも上がっていくと思われるので自分のパソコンのPHPの上げ方は覚えておきましょう。

### tips > サーバーのPHPのバージョンについて
今からPHPをダウンロードしますが、これはローカル環境（自分のパソコン）でのPHPの話です。
もしLaravel7を使ってローカル環境で開発を進めて最後の最後で「公開予定のサーバーのPHPバージョンは7.1.4です。」と言う話になると割と目も当てられない状態になります。公開を考えている場合は必ずサーバーのPHPバージョンも確認しておきましょう。

[![Image from Gyazo](https://i.gyazo.com/af491d4de5e85bd4692fcc0823540a07.png)](https://gyazo.com/af491d4de5e85bd4692fcc0823540a07)

[![Image from Gyazo](https://i.gyazo.com/1e0203fbe1103e265a2c9b7433af8d9f.png)](https://gyazo.com/1e0203fbe1103e265a2c9b7433af8d9f)

[![Image from Gyazo](https://i.gyazo.com/f5ba090560242181a36a8ed5876c218c.png)](https://gyazo.com/f5ba090560242181a36a8ed5876c218c)

Docker.dmg

ログインを求められます
[![Image from Gyazo](https://i.gyazo.com/06436e1ade20bb3a691714498f545666.png)](https://gyazo.com/06436e1ade20bb3a691714498f545666)

がまだアカウントを持っていないので、アカウントを作成します。
無料でこれだけの機能を使わせてもらってるのでアカウントくらいは登録してあげてください。

hub.docker.comにアクセスします。

[![Image from Gyazo](https://i.gyazo.com/4f4de5adfa730aa3a54f46b989a1f7da.png)](https://gyazo.com/4f4de5adfa730aa3a54f46b989a1f7da)

サインアップします。

今回は無料プランです。
[![Image from Gyazo](https://i.gyazo.com/e869d216513918a428da52e1d032266c.png)](https://gyazo.com/e869d216513918a428da52e1d032266c)

メールの送信がされますので確認してください。
これで完了です。

[![Image from Gyazo](https://i.gyazo.com/4f4de5adfa730aa3a54f46b989a1f7da.png)](https://gyazo.com/4f4de5adfa730aa3a54f46b989a1f7da)

ログインを求められた画面に戻って今登録したアカウントでログインします。
[![Image from Gyazo](https://i.gyazo.com/06436e1ade20bb3a691714498f545666.png)](https://gyazo.com/06436e1ade20bb3a691714498f545666)

するとパソコンの画面右上にクジラのマークがつきます。
こちらに画像のように緑のランプがつけばDockerの環境構築完了です。
[![Image from Gyazo](https://i.gyazo.com/e8e49485f34772a4862132544189fdcf.png)](https://gyazo.com/e8e49485f34772a4862132544189fdcf)

ちなみにこの画像の下の
Quit Docker DesktopでDockerを終了します。
RestartはDockerを終了した後に再起動します。

Dockerは再起動しないと情報が反映されなかったりするので、このRestartはよく使用します。
また、Dockerは簡単に言うとパソコンの中にもう一つパソコンを作るような仮想環境の技術ですので電力消費量がすごいです。開発を行っていないときはこのクジラマークから終了するようにしましょう。
気付いたら電力ゼロになって辛い思いをします。

ちなみにDockerを起動するときは他のアプリと同じようにLauchpadなどから起動するだけで大丈夫です！

これでDockerのダウンロードが完了しました。
次にDocker環境で簡単にLaravelを動かせるようになるLaradockをダウンロードしていきましょう。

