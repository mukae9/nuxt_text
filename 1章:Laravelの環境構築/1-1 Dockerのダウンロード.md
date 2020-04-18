# Dockerのダウンロード！

今回Laravel側の環境は最近主流となりつつあるDockerで行います。

この仮想化技術であるDockerを利用することで
- Dockerfileを共有することで、誰でも同じ開発環境が作れる。
- 環境の切り替えも容易。

などなど多くのメリットを享受する事が可能となります。
より具体的なメリットについては次章以降で説明したいと思いますので、まずはとにかくダウンロードを済ませて行きたいと思います。

## 実際にインストールを開始します。

まずは[Docker](https://www.docker.com/)の公式HPヘアクセスします。
[![Image from Gyazo](https://i.gyazo.com/af491d4de5e85bd4692fcc0823540a07.png)](https://gyazo.com/af491d4de5e85bd4692fcc0823540a07)

GetStartedから次に進んでください。

[![Image from Gyazo](https://i.gyazo.com/1e0203fbe1103e265a2c9b7433af8d9f.png)](https://gyazo.com/1e0203fbe1103e265a2c9b7433af8d9f)

Download for Macをクリックします。

[![Image from Gyazo](https://i.gyazo.com/f5ba090560242181a36a8ed5876c218c.png)](https://gyazo.com/f5ba090560242181a36a8ed5876c218c)

Get DockerをクリックするとDocker.dmgがダウンロードされますので実行してください。

実行後はログインを求められますが、、、
[![Image from Gyazo](https://i.gyazo.com/06436e1ade20bb3a691714498f545666.png)](https://gyazo.com/06436e1ade20bb3a691714498f545666)

がまだアカウントを持っていないので、アカウントを作成します。
無料でこれだけの機能を使わせてもらってるのでアカウントくらいは登録してあげてください。
（必須です）

[hub.docker.com](https://hub.docker.com/)にアクセスします。

[![Image from Gyazo](https://i.gyazo.com/4f4de5adfa730aa3a54f46b989a1f7da.png)](https://gyazo.com/4f4de5adfa730aa3a54f46b989a1f7da)

SignUpをクリックして会員登録を行います。
ご自身のメールアドレスやパスワードを設定してSignUpをクリックしてください。

[![Image from Gyazo](https://i.gyazo.com/e869d216513918a428da52e1d032266c.png)](https://gyazo.com/e869d216513918a428da52e1d032266c)

今回は無料プランで大丈夫です。

次へ進むと登録したメールアドレスへ認証メールが送信がされますので確認してください。
これでアカウント登録は完了です。

ログインを求められた画面に戻って今登録したアカウントでログインします。
もし閉じてしまっていた場合はLauchpadなどからDockerを探して通常のアプリと同じように起動すれば大丈夫です。
[![Image from Gyazo](https://i.gyazo.com/06436e1ade20bb3a691714498f545666.png)](https://gyazo.com/06436e1ade20bb3a691714498f545666)

ログインに成功するとパソコンの画面右上にクジラのマークがつきます。
こちらに画像のように緑のランプがつけばDockerのダウンロードは完了です。
[![Image from Gyazo](https://i.gyazo.com/e8e49485f34772a4862132544189fdcf.png)](https://gyazo.com/e8e49485f34772a4862132544189fdcf)

ちなみにこの画像の下の
Quit Docker DesktopでDockerを終了します。
RestartはDockerを終了した後に再起動します。

Dockerは再起動しないと情報が反映されなかったりするので、このRestartはよく使用します。
また、Dockerは簡単に言うとパソコンの中にもう一つパソコンを作るような仮想環境の技術ですので電力消費量がすごいです。開発を行っていないときはこのクジラマークから終了するようにしましょう。
気付いたら電力ゼロになって辛い思いをします。

なお繰り返しにもなりますがDockerを終了した場合、再度起動するときは他のアプリと同じようにLauchpadなどから起動するだけで大丈夫です！

これでDockerのダウンロードが完了しました。
次にDocker環境で簡単にLaravelを動かせるようになるLaradockをダウンロードしていきましょう。

