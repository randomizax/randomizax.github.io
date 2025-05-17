# 2024/09/29 Access Dive 4解読 その7

Access Dive 4の問題を解いています。
Access Diveとは何か、解いてどんなうれしいことがあるのかは「[その1](./ad4_intro.md)」をご覧ください。

今回は上の方にある「Dolls inside dolls」です。

一応ネタバレアラートで空行入れときます。

って、空行だとスキップして表示されちゃうんですよね。なんかうだうだと書いておくといい具合に「続きを読む」になってくれると思います。

<br/><br/><br/><br/><br/><br/>

さて、Dolls inside dollsの問題は画像です。ロシアの入れ子人形、マトリョーシカの写真です。このファイルのExifデータに暗号が入っています。

```
 Opsvok01-bpqfdiu7mf14gg1 vpoivosw Tilmpd02-ytamrmz6lw60qm1 LlblfAaphrqgQtVqctzaooYmk ZPalmww03-lgyjnq6fg31tp4

 Like part of a cosmic russian doll 000
```

最初のものがいかにもパスコード風ですね。何か変換するといいのかな。ヒントをさがすために「Like part of a cosmic russian doll」でぐぐると、こんなページが見つかりました。

- [http://news.nationalgeographic.com/news/2010/04/100409-black-holes-alternate-universe-multiverse-einstein-wormholes/](http://news.nationalgeographic.com/news/2010/04/100409-black-holes-alternate-universe-multiverse-einstein-wormholes/)

ブラックホールから新しい世界が生まれ、その世界の中のブラックホールから次の世界が生まれる…という論文の紹介です。そこで「Opsvok01-bpqfdiu7mf14gg1 vpoivosw」をキー「blackhole」を使ってヴィジュネル変換してみます。英字以外のものは元のままにしておきましょう。

`nested01-nemesis7cy14sv1 roditeli`

「nested」とは入れ子になっている人形(またはブラックホール)の「入れ子」に当たる英単語です。roditeliは「両親」を意味するロシア語をローマ文字で書いたもののようです。nemesisがキーワードリストに入っていることはわかっていますね。

ちなみにNiantec Project Wiki ([http://niantic.schlarp.com/start](http://niantic.schlarp.com/start) )内を「nested parent」で検索すると、今年の8月9日に「Jojo's Word of the day」(P. A. Chapeauの「今日のおことば」)で取り上げられていたことがわかります。「Word of the day」は現在更新が止まっているのでしょうか、新しいデータがないですね…

さて、「Dolls inside dolls」に「nemesis7cy14sv1」を入力してみると、正解でした。そして以下の情報が得られました。

```
Helios Watchlist Portal discovered.
You have discovered Helios Watchlist Portal 7/15.
```

その下には□とか・を並べたような暗号っぽいものが表示されています(添付画像)。これはPigpen Cipherという換字暗号で、ぐぐると見つかる表([http://en.wikipedia.org/wiki/Pigpen_cipher](http://en.wikipedia.org/wiki/Pigpen_cipher) )をそのまま使って読むことができます。

<a href="/kaidoku/images/1a2m0nx3gysia.png"><img width="200px" src="/kaidoku/images/1a2m0nx3gysia.png/>Pigpen Cipher</a>

`lampitheatre darles JN23HQ52QT45`

JN23HQ52QT45はQTHロケータによる座標です。通常のロケータはせいぜい6桁ですが、このサイトにあるツールを使うと任意の桁数で変換ができます。

- http://jidanni.org/geo/maidenhead/

その結果、以下のポータルがHelios Watchlistポータルのひとつであることがわかりました。

- https://www.ingress.com/intel?ll=43.678394,4.63071&z=17&pll=43.678394,4.63071

フランスのマルセイユの近くアルルという街にあるアンフィテアトルムのようです。この座標がわかった日にはuncapturedだったのですが、いまこの瞬間は青が持ってるみたいです。


これで元の画像のExif情報に書かれていた「01」「02」「03」の3つの謎暗号のうち最初のひとつが解けました。あとふたつあるのですが、自分はいまのところまだ解けていません。ヴィジュネルをそのまま続けても意味不明です。nested, nemesis, parent, big bangなどを試してみましたがダメでした。

ちなみに「Dolls inside dolls」からは3本のエッジが出ていて、そのうちのひとつ、上方の「Mary」が今回の正解でアンロックされました。他の2つの正解が残りのふたつに対応していると思います。

残りの2つが解けた方は、ぜひ知らせてください。

[次回は、まだ解けていない「Causality」を解説します](./ad4_causality.md)。「自分ではここまで解けたけど、残りがわからない、みんな助けて!」という投稿になる予定です。

----

[戻る](index.html)
