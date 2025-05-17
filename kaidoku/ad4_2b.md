# 2014/09/17 Access Dive 4解読 その2

Access Dive 4 (#AD4) の問題を解いていきます。
Access Diveとは何か、解いてどんなうれしいことがあるのかは「[その1](./ad4_intro.md)」をご覧ください。

Access Dive Console
- [http://veruminveniri.com/ad4/console](http://veruminveniri.com/ad4/console)

このURLのまん中の二重丸のノードをクリックすると「`2b | ...`」というダイアログが出ます。
「Show puzzle」をクリックすると画像が表示されます。
中央にでっかく「`2b | ¬ 2b`」と書いた茶色を主体とした画像ファイルです。
(画像ここに貼っていいと思えないので、自分でクリックしてください)

さて、ここから先はネタバレになります。
自力で解きたい人はここで読むのをやめてくださいね。

<br/><br/><br/><br/><br/><br/>

いいですか? では進みましょう

<br/><br/><br/><br/><br/><br/>

画像ファイルから隠されたメッセージを取り出す方法はいくつかありますが、
今回は画像の中にわかりにくい色で直接メッセージが描かれているのがわかります。
下の方に数字が並んでいます。画像編集ソフトのflood fillツールなどで
色をつけながら読むと、以下の文字列が読み取れます。

`1614050113110820212618b2222fb2308i`

読みにくいですね。数字を2桁ずつ区切ってみましょう。
アルファベットも混在しているので分離しておきます。

`16 14 05 01 13 11 08 20 21 26 18 b 22 22 f b 23 08 i`

この2桁の数字、01～26までしかありません。
アルファベットに対応させてみましょう。

```
16 14 05 01 13 11 08 20 21 26 18 b 22 22 f b 23 08 i
↓ ↓ ↓ ↓ ↓ ↓ ↓ ↓ ↓ ↓ ↓   ↓ ↓     ↓ ↓
 p  n  e  a  m  k  h  t  u  z  r    v  v      w  h
```

`pneamkhtuzr vv wh`

意味がわかりませんね。カエサル暗号かヴィジュネル暗号に思えます。
カエサルを試すにはここが便利です。
- `http://tools.decodeingress.me/#/rot-n`

どのnでも意味のある単語にはならないです。
さらにアナグラムになっている可能性もありますがどれもピンと来ません。

ではヴィジュネル暗号を試してみましょう。
- `http://tools.decodeingress.me/#/vigenere`

ヴィジュネル暗号にはキーワードが必要です。
このキーワードをなんとかして思いつかないといけません。
元々の画像に書いてある文字がヒントになります。

`2b | ¬ 2b`

「2b」は英語ではtwo b、「to be」と発音が同じです。
次の「`|`」(たてぼう)はプログラム言語で論理和(or)を表わす演算子として使われる記号です。
「¬」は論理学などで否定(not)を表わす演算子です。
つなげると「to be or not to be」。
もうわかりましたね。シェイクスピアの「ハムレット」に出てくる名台詞です。

ということで「hamlet」をヴィジュネル暗号のキーワードとして入れてみましょう。

```
pneamkhtuzr vv wh
↓
inspiration co wv
```

インスピレーション! びびっと来る単語ですね。
ちなみにパスコードによく出現する単語一覧というのがあって、そこにも載っている単語です。
- `http://tools.decodeingress.me/#/keywords`

さて、パスコードは通常、決まった形式をしています。
数字を#、アルファベットをx、キーワードをkeywordとすると

`#xx#keywordx#x#x`  `keyword#xx##xx#`  `xxx##keyword##xxx`

のような形になることが多いです。どこかに数字が入らないといけません。

元々の文字列で使っていない部分がありました。

`16 14 05 01 13 11 08 20 21 26 18 b 22 22 f b 23 08 i`

この「b f b i」、これを数字に対応させる方法がありそうです。
「one」「two」「three」の頭文字、ローマ数字などがよく使われますが、
今回はa=1, b=2, ...が可能性高そうです。
ヴィジュネル暗号の結果と合わせると、こうなります

```
16 14 05 01 13 11 08 20 21 26 18  b 22 22  f  b 23 08 i
↓  数字をアルファベットに、アルファベットを数字に
 p  n  e  a  m  k  h  t  u  z  r  2  v  v  6  2  w  h  9
↓  ヴィジュネル暗号(キーワードhamlet)、数字はそのまま
 i  n  s  p  i  r  a  t  i  o  n  2  c  o  6  2  w  v  9
```

「inspiration2co62wv9」という文字列が得られました。
これをSolutionに入力してみると、こんなメッセージが出ました。

```
Node unlocked.
You have unlocked "Proceed as ordered".
Congratulations. You have successfully unlocked "Proceed as ordered".
Since this node had already been unlocked, you were not the first to solve
it. Good luck!
```

正解です!次のノード「Proceed as ordered」をアンロックした、
でも一番じゃなかったね、と言われました。

これをIntelにpasscodeとして入れてみると…
「Passcode fully redeemed.」
ざんねん、正解だったけどもう使用回数の上限に達していました。

ともあれ、ひとつ解読完了です。

[次回は「Proceed as ordered」を解説します](./ad4_ordered.md)。
もう少しペースアップして短く書きますよ。﻿

----

[戻る](index.html)
