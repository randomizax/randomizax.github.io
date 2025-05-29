# 2015/07/13 JavaScriptシリーズ

今回は「Jojo's Word of the Day」から、ちょっと前ですけど2015/2/6～2/13に出題された「JavaScriptシリーズ」を解説します。DECURTATEは自分が解読レースで初めて1番乗りを取れたものです。この週のテーマはJavaScriptでした。エージェントの中にはプログラマの方も多いようですから、なじみ深い、あるいは日々お仕事で書いてるよ!って人もいるかもしれません。

★Part 1: 2015/2/6 KYRIE

[https://jojoingresswotd.github.io/2015/04/KYRIE.html](https://jojoingresswotd.github.io/2015/04/KYRIE.html)

`<script type="text/javascript">[[[[[[]]]]]],[[[[]]]],[[[[[[[[]]]]]]]],[[[[[[[[[]]]]]]]]],[[[[[[[[]]]]]]]],[],[[[[[[[[[]]]]]]]]],[[[[[[[[[]]]]]]]]],[[[[[[]]]]]],[[[[[[[[]]]]]]]],[[[[[[[[]]]]]]]],[[[[[[[[[[]]]]]]]]]],[[[[[[[[]]]]]]]],[[[[[]]]]],[[[[[[]]]]]],[[[[[[[[]]]]]]]],[[[[[[[[[]]]]]]]]],[[[[[[[[[[]]]]]]]]]],[[[[[[]]]]]],[[[[[[[[]]]]]]]],[[[[[[[[]]]]]]]],[[[[[[]]]]]]]</script>`

出題はHTMLのソースに、いきなりscriptタグで出ていました。

「 `[]` 」がたくさん連なっているのは配列データです。「 `[[[]]]` 」は中身がない配列ひとつが入った配列ひとつが入った配列、みたいな感じですね。空配列のネスト(入れ子)の深さを数字化してみるとこうなります。

6 4 8 9 8 1 9 9 6 8 8 10 8 5 6 8 9 10 6 8 8 6

ん、びみょう。各数字を1ずつ減らしてみましょう。空配列を何回さらに配列に入れたか、を考えたことになります。

5 3 7 8 7 0 8 8 5 7 7 9 7 4 5 7 8 9 5 7 7 5

2桁ずつ区切って10進数のアスキーコードとして解釈すると「5NFX9OJ9Y9K」になりました。「O」はグリフハックでよく出現するアレの形に似ています。

答: 5NFX9ALLJ9Y9K

★Part 2: 2015/2/7 AUTOSCHEDIASTIC

[https://jojoingresswotd.github.io/2015/05/AUTOSCHEDIASTIC.html](https://jojoingresswotd.github.io/2015/05/AUTOSCHEDIASTIC.html)

`<script type="text/javascript">"\"'\"''''\"\"\"'\"''\"\"\"\"\"''''\"'\"'\"''\"\"\"\"'\"'''\"'''\"\"''\"\"'''\"''\"''''\"''\"\"'\"\"'''\"\"\"'\"'''\"''\"\"'''\"'''\"''\"\"''\"\"'''\"\"\"\"'\"''\"''\"\"\"''\"\"\"\"'''\"\""</script>`

バックスラッシュがややこしいですが、ダブルクォートでくくった文字列の中にダブルクォートが入っているからです。よく見るとダブルクォートとシングルクォートしか出現していません。2進数っぽいですね。こういうとき、全体の長さが5の倍数ならモールス、6とか8の倍数ならアスキーコードの2進数、と予想をつけます。とりあえず01に変換してみます。

`01011110001011000001111010101100001011101110011001110110111101100100111000101110110011101110110011001110000101101100011000011100`

ん、これは逆順にすると8桁ずつアスキーコードの2進数になりますね。

答: 8chs7strongt5x4z

★Part 3: 2015/2/8 PUSILLANIMOUS

[https://jojoingresswotd.github.io/2015/05/PUSILLANIMOUS.html](https://jojoingresswotd.github.io/2015/05/PUSILLANIMOUS.html)

`<script type="gvcg/qzezhxirkg">/*[0c4y8,0c177,0c8,0c50,0c4y8,0c13,0c8,0cv,0c13,0c14,0c23,0c1y,0c4u,0c34,0c4u,0c44,0c4u].nzk(ufmxgrlm(r) {ivgfim wlxfnvmg.tvgVovnvmghYbGztMznv('hgbov')[0].rmmviGvcg[r];}).qlrm('')*/</script>`

JavaScriptのコメント形式の中に一見ランダムな文字列が入っています。何か文字変換がされているはず。script typeが「 `gvcg/qzezhxirkg` 」となっていますが、元はここが「 `text/javascript` 」なのでヒントになります。 `ufmxgrlm` というのもJSの文法から `function` でしょう。これに合う変換はatbashです(a→z、b→y、…z→aという変換)。

`[0x4b8,0x177,0x8,0x50,0x4b8,0x13,0x8,0xe,0x13,0x14,0x23,0x1b,0x4f,0x34,0x4f,0x44,0x4f].map(function(i) {return document.getElementsByTagName('style')[0].innerText[i];}).join('')`

documentから最初のstyleタグをさがして、その中身を文字列と見て、何文字目かを順に拾うようなプログラムになっています。何かのHTML文書に対してこれを実行するのですが、当然その対象はこの日の出題ページでしょう! 実行するにはブラウザのdeveloper consoleを出し、プログラムをペーストするのがかんたんです。

答: 9zdu9advanceq2q6q

★Part 4: 2015/2/9 DECURTATE

[https://jojoingresswotd.github.io/2015/05/DECURTATE.html](https://jojoingresswotd.github.io/2015/05/DECURTATE.html)

`<script>var a = atob("c2NyaXB0WzBdW0hvS3JxL3JTVmJrU0h0TDZyVkg2OUxrZWdsRT1d");</script>`

atobというのはJavaScriptの組み込み関数で、base64デコードです。このプログラムを実行すると以下の文字列になりました。

`script[0][HoKrq/rSVbkSHtL6rVH69LkeglE=]`

配列の添字部分にある「HoKrq…」もBase64デコードしてみましょう。

`1e 82 ab ab fa d2 55 b9 12 1e d2 fa ad 51 fa f4 b9 1e 82 51`

前日の出題と同様にこれが「何文字目を拾うか」を表しているのでしょう。 `script[0]` というのは、第0番目すなわち最初のscriptタグから拾えということですね。ちなみに最初のscriptタグは、他の日の出題でマウスホバーすると問題が表示されるように制御している部分なのですが、この週のシリーズでは使われない部分です。

文字を拾ってみると「forrteisafetyuthsfou」となりました。fo, ei, th, foを数字に直すとできあがりです。

答: 4rrt8safetyu3s4u

★Part 5: 2015/2/11 RECRUDESCENCE

2/10分のEXORDIUMは解説を後回しにして、11日分に行きます。

[https://jojoingresswotd.github.io/2015/05/RECRUDESCENCE.html](https://jojoingresswotd.github.io/2015/05/RECRUDESCENCE.html)

`<script type="text/javascript">var f = function(x) {return function() {return x;};}, g = function(x, y) {return function(a) {return a(x, y);};}, car = function(a) {return a(function(a, b) {return a;});}, cdr = function(a) {return a(function(a, b) {return b;});};</script>`

`<script type="text/javascript">var _039b = g(g(g(g(g(g(g(g(g(g(g(g(g(g(g(g(g(g(g(g(g(g(g(g(g(g(g(g(f(5)),f(f(f(f(2))))),f(7)),f(5)),f(f(f(f(4))))),f(f(f(f(f(f(2))))))),f(f(7))),f(7)),f(f(f(f(f(1)))))),f(f(0))),f(7)),f(f(4))),f(f(f(f(f(f(f(1)))))))),f(f(f(4)))),f(f(f(f(f(4)))))),f(f(f(3)))),f(6)),f(f(8))),f(7)),f(f(f(f(f(f(2))))))),f(f(4))),f(f(f(1)))),f(f(5))),f(5)),f(f(4))),f(0)),f(f(8))),f(0));</script>`

scriptタグが2つありますが、ひとつめが関数を定義、ふたつめがその関数を使っています。関数f,g,car,cdrが定義されています。fとgは関数を返す関数、carとcdrは関数を引数として受け取る関数です。このように関数を値として扱う関数を高階関数といいます。Haskellなどの関数型言語では高階関数を使ってプログラムを書いていきますね。

car, cdrから連想するのはLispです。Lispというのはラムダ計算という計算モデルをベースにしたプログラム言語です。ラムダ計算はプログラム言語というよりは理論なので、データを扱う方法も決めなければなりません。例えば自然数を表現するためにチャーチ数というものを使います。 `f(f(f(1))))` の結果は「『1を返す関数』を返す関数」を返す関数の意味になりますが、これがチャーチ数をJavaScriptで表現したもののつもりなのでしょう。関数gはcarとconsをセットとしてチャーチペアというものに対応します。チャーチペアはラムダ計算でデータ構造を作るために使われます。carとcdrは「引数として受け取った関数に2引数関数を渡して評価させる関数」というなんだかややこしいものになっちゃってますが、要はgで2要素配列を作って、carでそのひとつめ、cdrでふたつめの要素を返す、と考えるとよいです。

参考: [https://en.wikipedia.org/wiki/Church_encoding](https://en.wikipedia.org/wiki/Church_encoding)

fをネストするごとに数字が1増える、gで2要素配列を作るということで、関数fとgをわかりやすく定義し直してみましょう。

```
var f = function(x) { return x+1; }
var g = function(a, b) { return [a, b]; }
```

これを使ってvar _039bの式を実行すると、2分木のデータ構造が得られました。Lispと比べるとcarとcdrの使い方が逆のようですが、ラムダ計算ではそんなものなんですかね? ここで2分木を図示するとたいへんなことになるので、配列定数の形で書いてみます。

`[[[[[[[[[[[[[[[[[[[[[[[[[[[[6, null], 6], 8], 6], 8], 8], 9], 8], 6], 2], 8], 6], 8], 7], 9], 6], 7], 10], 8], 8], 6], 4], 7], 6], 6], 1], 10], 1]`

0～9になってほしいところですが、1～10になりました。数字だけを取り出し、1ずつ減らして並べると、2桁ずつでアスキーコードの10進表現になります。2分木のたどり方にはいくつか方法がありますが、ここでは深さ優先でたどったことになります。

`5575778751757685697753655090`

答: 7kmw3kluem5a2z

長々と解説してしまいましたが、結果としてはチャーチ数とかラムダ計算とか知らなくても解ける問題になっていました。そういえば2/6分のKYRIEも、「空配列を配列に入れたものを配列に」となっていて、チャーチ数とちょっと似た構造になっていましたね。あれも1ずれてたなあ。

★Part 6: 2015/2/12 LOKA

[https://jojoingresswotd.github.io/2015/05/LOKA.html](https://jojoingresswotd.github.io/2015/05/LOKA.html)

`<script type="text/javascript">var c = {s:0x73,x:0x6d,k:0x34,v:0x37,p:0x6e,m:0x34,o:0x79,u:0x64,r:0x74,w:0x65,l:0x6a,y:0x66,q:0x69,t:0x65,j:0x71,z:0x39,n:0x70};</script>`

変数cにハッシュ定数を入れています。キーがアルファベット1文字、値が16進数ですが、どう見てもこれらの値はアスキーコードです。キーのアルファベット順にソートして値を並べると「q4j4pynitsed7emf9」になりました。逆順にしてできあがり。

答: 9fme7destinyp4j4q

★Part 7: 2015/2/13 PLENARY

[https://jojoingresswotd.github.io/2015/05/PLENARY.html](https://jojoingresswotd.github.io/2015/05/PLENARY.html)

`<script type="text/javascript" style="display: none;" id="-1">var c = {};</script>`

`<script type="text/javascript" alt="-1" name="8" id="17">var c = [0157, 0152, 0062, 0066, 0151, 0062, 0141, 0160, 0156, 0172, 0165, 0167, 0157, 0162, 0167, 0067, 0172]</script>`

ふたつめの配列は整数定数を8進数で書いています。最初のよぶんな0が8進数を表わすのはC言語由来の記法ですが、まあ割といろんなバグの元になるので気をつけましょう。YAMLで10進数を書くときとかね! cをアスキーコードとして文字列化すると「oj26i2apnzuworw7z」になります。並べかえるとpronoiaというキーワードが見えてきそうですが、前後の文字列部分の並べ方がわからないですね。

HTMLのタグ属性に「 `alt="-1" name="8" id="17"` 」がついています。こういう部分に解法へのヒントがよく書かれています。 `name="8"` は8進数であることを、 `id="17"` は全部で17文字であることを示しているのでしょう。では `alt="-1"` は? またひとつめのscriptタグで `c = {}` となっているのは? -1だからひとつ前を表わすのでしょう。ふたつscriptタグがあるからひとつ前? などいろいろ頭をめぐらしました。そういえば、前日の2/12のLOKAも並べかえでしたね。そこで2/12の順番どおりに並べ直してみると正解でした。

答: 7wjz6pronoiaz2u2w

つまり「 `alt="-1"` 」の-1は前の日ということを示していたのです(←後で出てきます)。

★Part 8: 2015/2/10 EXORDIUM

ここで日程をちょっと戻って2/10分を解説します。

[https://jojoingresswotd.github.io/2015/05/EXORDIUM.html](https://jojoingresswotd.github.io/2015/05/EXORDIUM.html)

`<script type="text/javascript" alt="-1" name="6" id="4">['BBOlTBBByUovvOBBBSBBBBC']</script>`

これはまる3日間悩みました。 `[]` があるので、また何かの要素から文字を拾ってくるのでしょう。しかし `alt="-1"` というヒントがわかりません。2/13になってPLENARYの解法で再び「 `alt="-1"` 」に出会ってこのナゾが解けました。つまり前日の出題から何かを持ってくるのです。

「 `'BBO…'` 」の部分はヒントにしたがってBase64です。ただしBase64をそのまま解いてしまわず、Base64で使われている64進数の各桁までの変換で止めます。A=0, … Z=25, a=26, … z=51ですね。

1, 1, 14, 37, 19, 1, 1, 1, 50, 20, 40, 47, 47, 14, 1, 1, 1, 18, 1, 1, 1, 1, 2

これを使って前日のDECURTATEのどれかから文字を拾ってくるとよいのですが、どれを持ってきましょう。最初のatobの中にあった「 `"c2NyaXB0WzBdW0hvS3JxL3JTVmJrU0h0TDZyVkg2OUxrZWdsRT1d"` 」の部分でした。この文字列から[1], [1], [14], …と取り出すと「 `22hkx2221LOssh222J2222N` 」になります。2や1が連続している部分は合計します。

答: 4hkx7lossh6j8n

このように、誰も解けない出題の2～3日後に、解法のヒントとなるような少しやさしい出題がされることはよくあります。Jojoさんの投稿で「○○ solve goes to 誰々」が出ていない日は、まだ誰も解けていないということです。狙い目ですよ!

★テーマ出題

さて、この週にはテーマ出題がかくされていました。毎日の出題HTML内で、「マウスホバーすると問題が表示されるように制御している部分」のJavaScriptがあるのですが、この最後の部分に使われない引数が書かれていました。

```
2/6  0x86
2/7  0x75
2/8  0
2/9  0X1D
2/10 0X8F
2/11 0XEE
2/12 "struggle"
2/13 "EOF"
```

これ全体で出題となっていて、解くと別のパスコードになるはずです。自分も解けていませんが、もしかするとまだ誰も解いていないかもしれません。キーワードが多分struggleで、あとは前後の部分がわかればいいのだと思いますが…。もし解けた人は、メールを送ってみると一番乗りになれるかもしれませんよ!

----

[戻る](index.html)
