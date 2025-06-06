# 2014/09/19 Access Dive 4解読 その5

Access Dive 4の問題を解いています。
Access Diveとは何か、解いてどんなうれしいことがあるのかは「[その1](./ad4_intro.md)」をご覧ください。

今回は上の方にある「Signal Anomaly」です。

もうネタバレアラートいらないですよね? いる?

<br/><br/><br/><br/><br/><br/>

今回のパズルはまた画像です。なにやら端末画面のようですね。

画像ファイルのEXIFなどからは特別な情報は見つけられませんでした。
映っている内容を調べてみます。

```
>>> beginning session traceback for operator@wwvi

>>> rxradio: version 0.31.4 starting. Built: 2014-09-05 04:34:00 UTC
>>> rxradio: waiting for carrier signal...
>>> rxradio: high-intensity signal anomaly detected!^C^C^C^C

>>> unknown error: 159245742536988826570878829473835753015633340429114017924166366007565
914240551645530765911314420989441694491039748194986432767761787396265

>>> Segmentation fault (core dumped)
>_
```

まずですね、↑このテキストを間違いなく書き写すのが大変でした。
OCR(文字認識)技術とか使うという手はあったのかなあ?

さて、長い数字列があります。2桁ずつ区切っても92とか74とかあるので、
そのままアルファベットに対応しなさそうです。3桁ずつに区切って
アスキーコードの10進表現、というわけでもないようですねえ。

いや、さっきから、2桁に区切るとか3桁に区切るとか言っていますけど、
本当はもっとやりたいことがあるでしょう? 長い整数と言えば?

そう、素因数分解です!

映画「コンタクト」でも宇宙人がメッセージを送るとき、
素数に乗せて送ることで「これは偶然ではない、
知能のある存在からのメッセージだ」というストーリーになっていましたね。

いまどきはEmacsでもRubyでもババンと素因数分解できるので楽ちんですよ。

```
159245742536988826570878829473835753015633340429114017924166366007565914240551645530765911314420989441694491039748194986432767761787396265
 = 3 * 5 * 11 * 13 * 17 * 29 * 31 * 43 * 53 * 61 * 67 * 73 *
   79 * 89 * 101 * 103 * 113 * 131 * 139 * 149 * 151 *
   167 * 173 * 181 * 191 * 197 * 223 * 229 * 233 * 239 *
   257 * 263 * 277 * 281 * 293 * 317 * 331 * 337 * 353 *
   373 * 379 * 383 * 397 * 401 * 431 * 433 * 443 * 467 *
   479 * 503 * 521 * 523 * 541 * 547 * 569 * 577 * 587 *
   601 * 631 * 641 * 647
```

これはすごい! 素因数のべき数が全部1です!!
この興奮は、伝わらない人には伝わらないでしょうが、
伝わる人にはきっと伝わりますw
そして2、7、19、23などいくつかヌケがあることに気づきます。

素数を小さい方から並べて、上の表に出現するものを1、
しないものを0と対応づけてみましょう。

```
2 → ない → 0
3 → ある → 1
5 → ある → 1
7 → ない → 0
11 → ある → 1
13 → ある → 1
17 → ある → 1
19 → ない → 0
```

こんな感じで最後までいくと、0と1の並びが得られます。

`0110111001100101011011010110010101110011011010010111001100110100011100100111011000110100001100010111100101100100001101`

8桁ずつ区切って16進数に直してみましょう

```
01101110 6e
01100101 65
01101101 6d
01100101 65
01110011 73
01101001 69
01110011 73
00110100 34
01110010 72
01110110 76
00110100 34
00110001 31
01111001 79
01100100 64
00110100 34
```

最後は2桁足りないので、「出現しない」という意味で0を補いました。

アスキーコードに慣れている人にはもう読めているかもしれませんが、
慣れていない人はこのツールを使って文字に直せます。

`http://tools.decodeingress.me/#/basic`

このページの「Binary」のところに0、1の文字列を入力する
(最後に追加した「0」ふたつも必要です)か、または、
「Hex」のところに「6e656d657369733472763431796434」と入力しましょう。
左上の「Text」のところに変換結果が表示されます。

`nemesis4rv41yd4`

これはパスコードの形式に合っています。「nemesis」もよく出るキーワード
一覧に含まれている単語です。ということでこれが正解でした。

この答を入力すると以下のメッセージが表示されました。

```
Helios Watchlist Target Portal discovered.
You have discovered Helios Watchlist Target Portal 1/2.
PORTAL 1 INITIALS REHM QTH LOC EM02JC99ID68 GOOD LUCK
```

Helios Watchlistというポータルがいくつかあり、
hackするとHelios AnomalyないしArtifactに関する
情報が得られるようなのですが、その中でもターゲットポータル
というもののうちひとつを教えてもらえました。

ポータルのイニシャルがREHM、GPS座標がEM02JC99ID68。
この場所には「Robert E. Howard Museum」というポータルがあるようです
ここから何か情報を取れるかどうかはアメリカのテキサス州まで行かないと
わからないようですね。

ちなみに、「nemesis4rv41yd4」は、いまはfully redeemedですが、
HS, T, CS, X8, R6など、割といいアイテムがもらえました。

整数なら素因数分解、とは安直かと思いつつ、
素因数分解せずにはいられないですよね!
今回もうまく解けました。

[次回は「Gigantic」を解説します](./ad4_gigantic.md)。
…そろそろネタ切れです…

----

[戻る](index.html)
