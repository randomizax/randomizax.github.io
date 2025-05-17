# 2014/11/02 Access Dive 4解読 その9

だいぶ間があいてしまいましたが、Access Dive 4の解説、最終回です。
今回は右上の方にある「Human Knowledge」です。

前回[その8の「Causality」](./ad4_causality.md)はコメントでひとつ解けています。まだ見ていない方はチェックしてみてください。

AD4の解説記事がDecode Ingressに出ています。ここですでに解説したものも、していないものもあります。今後も続くので期待しましょう。
- `http://decodeingress.me/2014/10/19/passcode-walkthrough-vi-access-dive-4-easy-path/`
- `http://decodeingress.me/2014/10/10/passcode-walkthrough-vi-access-dive-4-easy-path-part-2-discover/`

さて、「Human Knowledge」ですが、クロスワードパズルのヒント集のようなものが出てきました。
このヒントはほとんどここのサイトで検索することで答がわかります。
- [https://niantic.wiki/start](https://niantic.wiki/start)

右上の検索窓に単語を入れると、関連する過去の文書やキャラクター・団体のプロフィールが見つかります。

では問題をひとつずつ見てみましょう。

```
______-X____	Power cube
パワーキューブを作成したのはDr. Oliver Linton-Wolfeなので「W」

____X_		Journals
Dr. Carrie Campbellが「Carrie Journal」という日記を書いていたからCarrieの「i」?

X_____		Worked with Shannel
Nesselという人物がShannelといっしょに働いていたらしい。「N」?

_X__		Arecibo
Dr. Devra Bogdanovichが13Magnusイベントでアレシボ文書をレジスタンスに渡した。
その日付、2013年10月25日の2013の「0」か1025の「0」?

_X____		Calvin, Hank, Fiona
3人ともIQTechのメンバー。「Q」

_____X		Dead man pseudonym
死んだキャラの偽名。Victor Kuerzeの偽名Curter Zokievの「v」か、Verity Sekeの「y」か。他にpseudonymというとHenry Richard LoebのP. A. Chapauが思いつくがPACはまだ存命ではないか?

X		NIA+corporations
人数なら「9」、組織数なら「4」

X___		Leningrad Band
全然わからないけど、「1943 Leningrad」という検索結果が得られる。「1」?

X___		Visur operative
Visur Technologyの創立者Ilya Pevtsovの「I」

__X_____	Phone
わからない。2012年11月にGlitchy Phone、Retrieve the Phoneというストーリーがある。字数から言ってRetrieveの「t」?

X		Needed to make a field
Control Fieldを作るのに必要なLink数で「3」
```

以上をつなげて win0qv41it3 とか win0qy91it3 とかあたりだと思います。数字を変えたり、yをvに変えてみたり、ずいぶんたくさん試したものの正解は見つけられていません。全部わからないと正解にはならないのがつらいですね。

↑の答、これじゃない? というのを見つけたら教えてください。

おまけとして、まだ解説していなかったものも簡潔に紹介します(Decode Ingressの記事にも英語でより詳細な解法解説があります)。

- 「Unexpected side effects」
    -  文中に出てくる数字を全部つなげて、2桁ずつ区切ると10進数のアスキーコードになっている
- 「Welcome to AD4」
    -  3つヒントがあるが、ivrvtugmhrvtugsvirvyfriraをROT13するとvieightzueightfiveilsevenになり、eightやsevenなどを数字に直すと正解

Darsana AnomalyでもAccess Diveがあるのでしょうかね? 楽しみにしましょう。
Access Dive 4の解説シリーズは以上です。
Decode Ingressのほうでは音の解読もやってくれるようです。こっちも楽しみですね。

----

[戻る](index.html)
