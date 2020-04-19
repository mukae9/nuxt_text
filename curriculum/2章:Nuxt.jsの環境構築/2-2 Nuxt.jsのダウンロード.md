# Nuxt.jsのインストール！

前回でNuxt.jsフォルダを作成するためのNode.js(npm)のインストールが完了しましたので
早速Nuxt.jsのプロジェクトを作成していきましょう。

まずはフォルダ構成の確認をします。

```
Documents
└── Laravel
    └── Laradock
    └── ECapp
    └── Client
```

すでにLaradockとECappの作成は完了していますので、
今回の章では同じ階層にClientという名前でNuxt.jsのフォルダを作成します。

laravelフォルダでターミナルを開きます。

そして

```
npx create-nuxt-app Client
```

を入力します。

するとClientという名前でNuxt.jsのプロジェクトの作成が開始されます。

```
create-nuxt-app v2.14.0
✨  Generating Nuxt.js project in Client
```
上記のような表示がされた後に
問答が始まります。
この問答はNuxt.jsのバージョンが変わるごとに順番が変わったりしますので、
順番が違う場合もあります。

もしバージョンが新しくなり違う問答が現れた場合でも、その問いについて公式ドキュメントやネット検索で調べると比較的容易に答えらえるかと思います。

それではNuxtからの問いに答えて行きましょう。

```
? Project name (Client) 
```
プロジェクト名を聞いています。
ClientでいいのでEnterを押します。


```
? Project description (My exquisite Nuxt.js project) 
```
プロジェクトの説明です。
デフォルトでいいのでEnterを押します。

```
? Author name お名前
```

あなたのお名前です。
Enterで大丈夫です。

```
? Choose the package manager 
```
Npmを選択します。

```
? Choose UI framework (Use arrow keys)
```
Noneを選択します。

```
? Choose custom server framework
```

 None (Recommended)を選択します。

```
? Choose linting tools (Press <space> to select, <a> to toggle all, <i> to invert selection)
```
ESLintを選択します。

```
? Choose Nuxt.js modules
``` 
Axiosを選択します。

```
? Choose development tools 
```
for VScodeを選択します。


以上で選択が完了しましたのでNuxt.jsのプロジェクトの作成が開始されます。
少し経つと、

```
🎉  Successfully created project Client

  To get started:

        cd Client
        npm run dev

  To build & start for production:

        cd Client
        npm run build
        npm run start
```

という表示がされます。
ご丁寧にこの後実行したい場合のコマンドが書いてありますのでやっていきましょう。

今はまだLaravelフォルダにいるので、

```
$ cd Client
``` 
で今作ったClientフォルダに入り、

```
$ npm run build
``` 
を実行します。
現在のNuxtのファイルで実際に動かすためのビルドを開始します。
もちろんまだ何も新しいファイルは作っていませんがNuxtのデフォルトの画面を表示させるための処理が行われます。

```
> nuxt build

ℹ Production build                                                                      23:25:21
✔ Builder initialized                                                                   23:25:21
✔ Nuxt files generated                                                                  23:25:21

✔ Client
  Compiled successfully in 5.07s


Hash: 06bb985b9a3399439c0c
Version: webpack 4.42.1
Time: 5070ms
Built at: 2020-04-19 23:25:27
                         Asset       Size  Chunks                         Chunk Names
../server/client.manifest.json   6.57 KiB          [emitted]              
       36c5edd528171baa4c50.js   48.8 KiB       0  [emitted] [immutable]  app
                      LICENSES  389 bytes          [emitted]              
       a7ad051dacaf2e4d8d6f.js   2.98 KiB       2  [emitted] [immutable]  pages/index
       ce7f52c42f7b5a1f99b0.js   2.31 KiB       3  [emitted] [immutable]  runtime
       f8bdba9620f7a352bfd9.js    152 KiB       1  [emitted] [immutable]  commons.app
 + 1 hidden asset
Entrypoint app = ce7f52c42f7b5a1f99b0.js f8bdba9620f7a352bfd9.js 36c5edd528171baa4c50.js
ℹ Generating pages                                                                      23:25:27
✔ Generated /       
```
ビルドが完了したので、

```
$ npm run start
```
で実際にビルドしたNuxtプロジェクトを見てみましょう。

```
> nuxt start


   ╭──────────────────────────────────────────╮
   │                                          │
   │   Nuxt.js v2.12.2                        │
   │   Running in production mode (spa)       │
   │   Memory usage: 16.1 MB (RSS: 54.8 MB)   │
   │                                          │
   │   Listening on: http://localhost:3000/   │
   │                                          │
   ╰──────────────────────────────────────────╯

```

[http://localhost:3000/](http://localhost:3000/)にアクセスします。



[![Image from Gyazo](https://i.gyazo.com/8fd8ad61501c4c9401f2d28473ebd3e0.png)](https://gyazo.com/8fd8ad61501c4c9401f2d28473ebd3e0)


Nuxtのデフォルト画面が表示されましたね。
これでNuxt.jsの構築は完了です。

次の章からいよいよ実際にECサイトの具体的な開発に入っていきますよ！
