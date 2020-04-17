# Composerをインストール！
ComposerはPHPのライブラリなどを効率的にダウンロードできる必須ツールです。
今回の教材だけでなくPHPを使うのであれば様々な場面で必要となるものなので、ここでインストールしておきましょう。

まずはそもそもcomposerがダウンロード済みではないかチェックしておきましょう。
```
$ composer -v

```

[![Image from Gyazo](https://i.gyazo.com/3881d88294d9afe6f5485b386b32deef.jpg)](https://gyazo.com/3881d88294d9afe6f5485b386b32deef)

上記のように派手にCOMPOSERと出てきたらすでにインストール済みです。
次の項目に進みましょう！

表示がされない方は早速インストールしていきます。

```
$ brew install composer

```

これだけでインストールが開始されます。

PHPとHomebrewがインストールされていればこれだけで完了です。

最後にもう一度

```
$ composer -v

```

と打つと、上記の画像のように派手にCOMPOSERと出力されます。

以上でComposerのインストールは完了です。
次回の章からLaravelの環境構築を行っていきましょう。
