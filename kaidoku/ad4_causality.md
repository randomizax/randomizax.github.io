# 2014/10/05 Access Dive 4解読 その8

Access Dive 4の問題を解いています。
今回は左下の方にある「Causality」です。

さて、Causalityですが、まだ解けていません。

今回のお題も画像です。「'Stadt Lancre' by Cyrodan」とタイトルが出ますね。この情報でぐぐると元画像は以-下のものであるとわかります。
- [https://commons.wikimedia.org/wiki/File:Stadt_Lancre.JPG](https://commons.wikimedia.org/wiki/File:Stadt_Lancre.JPG)

左上にVIのロゴと、右上に「DO NOT MEDDLE WITH THE NATURE OF CAUSALITY」とうめ込まれているのがわかります。これらのキーワードからぐぐると、「Discworld」という小説に登場するものであることがわかりました。Stadt Lancreとは「ランカー市」のドイツ語ですが、ドイツ語であることに意味はないようです。画像がドイツ語版Wikipediaのディスクワールドの項目からリンクされているのでドイツ語表記なのでしょう。

ロゴとセリフ以外にも変な模様がうめ込まれているのがわかります。これはライフゲーム(Conway's Game of Life)というもののパターンの一部です。Access Diveでは過去にもライフゲームのパターンが出題されたことがあるそうです。

ライフゲームは学術的にはセルラオートマトンという分野に属し、決まったパターンで図形が変化していく、生命のシミュレーションモデルのようなものです。ライフゲーム自体は非常に面白く奥の深いものです。自分も80年代末ごろにグライダー列をつないで計算するパターンを作ってネットに投稿したりしていました。以下のニコ動のシリーズが非常によくできているので一度見てみてください。Youtubeにも転載されたものがあるようです。
- [https://www.nicovideo.jp/mylist/34610498](https://www.nicovideo.jp/mylist/34610498)

この動画でライフゲームに興味を持った人には、この本がすごくおすすめです。

- ウィリアム・パウンドストーン 『ライフゲイムの宇宙』 有沢誠訳、日本評論社、2003年6月、新装版。ISBN 4-535-78383-7
- [https://amzn.asia/d/3t63V0X](https://amzn.asia/d/3t63V0X)

ちなみに原題は「The Recursive Universe」、Ingressのストーリーにぴったりの書名ですね! 自己再生できる機械が偶然生まれることがあるだろうか? という問いがテーマになっています。

さて、お題のPNGを画像エディタで開くと、アルファチャンネル(透明ピクセル)にパターンが入っています。これをライフゲームのプログラムに読ませて実行すると、添付画像のように文字が出てきました。ライフゲームを実行するにはGollyというプログラムを使うとよいです。
- [https://golly.sourceforge.net/](https://golly.sourceforge.net/)

ちなみに、この横に流れるサインを生成するパターンは「Golly Ticker」と呼ばれています。

パターンを実行して出てきたのは「7mt95yq3」という文字列と、その鏡像でした。これはAD4のキーワードの形式、「keyword#xx##xx#」の後半部分に違いありません。そこで思いつく限りのキーワードをvi、nemesis、cortexから、グリフ単語まで30種類くらい試してみたのですが、いまのところまだ正解には出会っていません。

また、元のPNGファイルのメタデータには以下の情報が入っていました。

```
..!?!!!!!!!!!!!!!!.?....?.?!.?!.!!!!!!!!!!!!!!!!!!!.................!.!!!!!!!!!!!!!!!!!.!?!!!!!!.?..?.?!.?!!!!!!!!!.!!!!!!!!!!!!!!!!!!!!!.....................!.!!!?!!!!.?..?.?!.?!!!.!?!!!!!!.?..?.?!.?!.!!!...!?!!.?......?.?!.?!.!.!!!!!?!!.?....?.?!.?!.!!!?!!!!!!.?..?.?!.?!.!!!?!!!!.?..?.?!.?!!!!!!!.
```

「.!?」3種類の文字300文字から成るナゾのメッセージです。モールスでもないし、3進数にしては?が連続していないのが不自然です。「.?..?.?!.?」というパターンが何度かくり返されたりしていますが、どうアタックしていいのやら。いろいろいじってみたのですが、私はまだ解けていません。

AD4のノードマップ上、Causalityからは2つエッジが出ています。一方がライフゲーム、もう一方が.!?のナゾに対応しているという可能性もありますし、両方を合わせてひとつの答になるのかもしれません。

ディスクワールド関連のヒントが入っているので、ディスクワールドとIngressに共通するキーワードがありそうなのです。Causality(因果律)なんかはぴったりですが、違いました。ディスクワールドを読み込んだ人(あるいはゲームを遊んだ人)いませんかー?

ということで今回はここまでです。正解がわかった人はぜひコメントなどで教えてください。あ、パスコードがわかったら、FRになる前に近しい人と共有してからでいいですよ。

[次回も、まだ解けていない「Human knowledge」です](./ad4_human.md)。あと1歩なので、みなさんのお知恵をお貸しください。

<a href="/kaidoku/images/1a3axclf9j0ky.png"><img width="200px" src="/kaidoku/images/1a3axclf9j0ky.png"/>画像内にパターンが見えている様子</a>

<a href="/kaidoku/images/1a3axcxn4j4j6.png"><img width="200px" src="/kaidoku/images/1a3axcxn4j4j6.png"/>パターンだけを取り出したところ</a>

<a href="/kaidoku/images/1a3axd6qep8aq.png"><img width="200px" src="/kaidoku/images/1a3axd6qep8aq.png"/>実行結果</a>

----

コメント 2014/10/06

Discworldの司書はオランウータンで、その鳴き声は「Ook」です。「Ook!」というbrainfuck派生プログラミング言語があって「オランウータン用」だそうです。
- [https://ja.wikipedia.org/wiki/Ook!](https://ja.wikipedia.org/wiki/Ook!)

Ook化・復元ページがありました
- [https://www.splitbrain.org/services/ook](https://www.splitbrain.org/services/ook)

実行結果
`nemesis8hg88ly9`

これによってパスコードが得られましたが、AD4のCausalityに入力しても不正解扱いでした。

パスコードとして使うと以下がもらえるそうです。
`400XM 100AP PS*3 R4*5`

----

コメント 2016/03/04

なんと1年半ぶりで今日取れました。keyword7mt95yq3 のkeywordにある単語を入れます。当時試したはずだったんだけど…

(2025/05/17追記、ある単語とはmirrorです)

----

[戻る](index.html)
