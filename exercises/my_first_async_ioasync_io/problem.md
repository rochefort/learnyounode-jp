一回だけ一つの**ASYNC**のファイルシステムのメソードを使ってファイルの改行数を出すアプリを書いてください。`cat file | wc -l`と同じようなアプリ.

アプリの一つ目のコマンドラインアーギュメントはそのファイルのパスです。

----------------------------------------------------------------------
# ヒント

このソルーションは前のとほとんど一緒です。ただ今回はNodeのいい方法を使わないといけないです：**ASYNC**。

`fs.readFileSync()`の代わりに`fs.readFile()`を使わないといけないしメソードの返事の代わりにコールバックのメソードを二つ目のアーギュメントとして使わないといけません。コールバックについて勉強したい場合はこれを読んでください： https://github.com/maxogden/art-of-node#callbacks

Nodeの普通のコールバックのイディオムの書き方を忘れないでください：

```js
function callback (err, data) { /* ... */ }
```

それならエラーの場合は`err`がnullではない。エラーがなければ二つ目のコールバックアーギュメントは大切な`Buffer`オブジェクトが入っています。`readFileSync`と同じようにファイルパスとコールバックの間に`"utf8"`入れてもいいです。それなら`Buffer`のかわりに`String`は返事になります。

`fs`のモジュールドキュメントはブラウザーを使ってこのリンクにアクセスできます:
  {rootdir:/node_apidoc/fs.html}

----------------------------------------------------------------------