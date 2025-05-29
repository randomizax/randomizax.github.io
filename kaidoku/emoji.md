# 2015/07/12 絵文字シリーズ

今日は「Jojo's Word of the Day」から、2015/7/2～7/8に出題された「絵文字シリーズ」を解説します。長文ですよ! 最後の2つ、DAPOCAGINOUSとDAGGLEは解読レースで一番を取って名前が載りました!

★Part 1: 2015/7/2 CONNATE

[https://jojoingresswotd.github.io/2015/24/CONNATE.html](https://jojoingresswotd.github.io/2015/24/CONNATE.html)

出題はHTML内に埋め込まれています。

```
d7 60 9b bd a8 2b a8 ec a7 a7 11 60 9d ef 80 ae 
d9 e0 be 2a c5 76 19 de ae a3 de 6d f7 d9 9d ec 
7e 52 b9 e2 97 c1 ab 9d ea 9e 6d c1 5c 6f 1a ea 
09 e6 dc af 2c ab 78 d7 e0 ad eb df c7 ef 06 ae 
77 aa 79 b7 05 71 bc 6b a8 27 9b 72 bc b2 ad e3 
5f 82 b7 af 7f 1f bc 09 bb da 82 ba 82 bd a8 ee 
ae bc 85 82 77 be 52 b9 e2 97 c1 ab 9d ea 9e 6d 
c1 5c 6f 1a ea 09 e6 dc af 2c ab 78 d7 e0 ad eb 
df c7 e3 de 6d f7 d9 9d ec 7e 26 eb e0 ad 19 29 
ca 7c e7 82 f6 da 66 77 b1 05 e6 a7 ce b6 a0 f8 
6b ed ba 01 9e be c6 f2 be 78 2b 15 a6 e3 b3 29 
f1 af e3 b2 9e 9c 43 86 b7 e0 bd b6 99 9d ec 41 
79 a9 f3 ad a8 3e f0 26 ef 6a 0a ea 0a f6 a3 ba 
ba f2 16 09 de f9 4a e7 8a 51 ab 9d ea 9e 6d c1 
5c 6f 1a ea 0a f6 a3 ba ba f2 35 f8 2b 7a f7 f1 
fb a0 9b bd a8 2b a8 ec a7 a7 11 60 9d ef 8f bd 
ea 72 ae a0 5c ad a3 eb 6a 07 ab f0 26 ef 6a 0a 
ea 16 09 de
```

うわー、16進ダンプですね。しかも長い。276バイト分もあります。いろいろ試してみると、Base64した後にrot13すると意味のある文字列になりました。

`12PointedBlackStar+NegativeSquaredCrossMark+Heavy8TeardropSpokedPropellerAsterisk+8TeardropSpokedPropellerAsterisk+8PointedPinwheelStar+Heavy8TeardropSpokedPropellerAsterisk+CrossMark+WhiteExclamationMarkOrnament+TightTrifoliateSnowflake+BlackQuestionMarkOrnament+8PointedPinwheelStar+HeavyTeardropSpokedPinwheelAsterisk+6PointedBlackStar+CircledOpenCentre8PointedStar`

+で区切られた文字列が14個ありますが、それぞれは文字の名前です。その文字と文字のユニコードコードポイント(16進)を並べてみます。

|コード|文字|文字の名前|
|:---|:---:|:---|
|2739|✹|12PointedBlackStar|
|274e|❎|NegativeSquaredCrossMark|
|274b|❋|Heavy8TeardropSpokedPropellerAsterisk|
|274a|❊|8TeardropSpokedPropellerAsterisk|
|2735|✵|8PointedPinwheelStar|
|274b|❋|Heavy8TeardropSpokedPropellerAsterisk|
|274c|❌|CrossMark|
|2755|❕|WhiteExclamationMarkOrnament|
|2745|❅|TightTrifoliateSnowflake|
|2753|❓|BlackQuestionMarkOrnament|
|2735|✵|8PointedPinwheelStar|
|2743|❃|HeavyTeardropSpokedPinwheelAsterisk|
|2736|✶|6PointedBlackStar|
|2742|❂|CircledOpenCentre8PointedStar|

この16進数の下2桁をアスキーコードとして変換するとパスコードが得られました。

答: 9NKJ5KLUES5C6B

★Part 2: 2015/7/3 FARDEL

[https://jojoingresswotd.github.io/2015/25/FARDEL.html](https://jojoingresswotd.github.io/2015/25/FARDEL.html)

```
00 2D 20 22 20 13 20 10 22 15 00 B7 25 AA 22 C5 
00 2D 20 14 FE 31 22 C5 20 13 00 2D 20 44 20 10 
20 13 20 22 00 B7 20 22 22 15 00 2D 00 B7 20 13 
20 44 22 C5 25 AA 20 22 20 44 22 C5 20 14 FE 31 
25 AA 22 C5 FE 31 00 2D 20 22 20 44 25 AA 20 10 
20 44 00 B7 22 15 20 22 20 10 22 C5 20 44 20 14 
00 2D 25 AA FE 31 20 13 00 B7 22 C5 20 22 25 AA 
22 15 20 14 00 B7 25 AA 22 C5 20 44 00 B7 20 22 
20 10 20 44 00 2D 20 14 20 22 22 15 20 14 00 2D 
22 C5 25 AA 22 C5
```

また16進ダンプです。00 と 20 がたくさん見えるので、00で区切ってさらに20で区切るのかと思いきや、それではうまく合いません。2バイトペアでユニコードコードポイントと見なすと(UTF-16BE)、以下のような文字列になりました。

`-•–‐∕·▪⋅-—︱⋅–-⁄‐–•·•∕-·–⁄⋅▪•⁄⋅—︱▪⋅︱-•⁄▪‐⁄·∕•‐⋅⁄—-▪︱–·⋅•▪∕—·▪⋅⁄·•‐⁄-—•∕—-⋅▪⋅`

ハイフンっぽいもの、ドットっぽいもの、区切りっぽいもの(スラッシュと縦棒)が見えます。ドットとハイフンが出てくると思いつくのは? トン、ツー、そう、モールス符号です。ドットっぽい4種類、ハイフンっぽい4種類の違いは無視してモールスと思って読むと「y3w7ksainaerg6bug7」になりました。逆順にしてできあがりです。

答: 7gub6greaniask7w3y

★Part 3: 2015/7/4 FORSWUNKE

[https://jojoingresswotd.github.io/2015/25/FORSWUNKE.html](https://jojoingresswotd.github.io/2015/25/FORSWUNKE.html)

```
1F 55 21 F1 96 1F 42 81 F5 57 1F 17 F1 F9 84 1F 
1F F1 F1 F2 1F 1F F1 F1 FC 1F 1F 11 F1 E6 1F 41 
81 F1 71 1F 55 81 F1 7E 1F 55 11 F4 0D
```

これはやられました。2桁ずつで16進ダンプに見えるのにすっかりだまされ、相当な時間をムダにしました。これ、5桁ずつ区切るのが正解です。

```
1F552 1F196 1F428 1F557 1F17F 1F984 1F1FF 1F1F2 1F1FF 
1F1FC 1F1F1 1F1E6 1F418 1F171 1F558 1F17E 1F551 1F40D
```

これをユニコードコードポイントと思って文字にするとこんな風になります。絵文字ですね!

🕒🆖🐨🕗🅿🦄🇿🇲🇿🇼🇱🇦🐘🅱🕘🅾🕑🐍

[P]の次の文字はパソコンによっては見えないかもしれません。ユニコーンです。時計は数字に対応しそうです。国旗は面白くて、1F1F2 1F1FFがそれぞれ「z」「m」を表わす文字符号なのですが、2文字でISO1366国コードに対応する国を表わす、となっています(ユニコードのregional indicator symbolというそうです。こんな仕様があるんですねー)。国旗は左から、ザンビア、ジンバブエ、ラオスのものです。コアラ、ユニコーン、エレファント、スネーク、全部頭文字を取りましょう。NGマークだけは2文字のままNGにするとフォーマットに合います。

答: 3ngk8puzzleb9o2s

★Part 4: 2015/7/5 SOMATIC

[https://jojoingresswotd.github.io/2015/25/SOMATIC.html](https://jojoingresswotd.github.io/2015/25/SOMATIC.html)

```
E2 9E A1 20 E2 9C 9D 20 F0 9F 85 B0 20 E3 80 B0 
20 E2 AC 85 20 F0 9F 8E 81 20 F0 9F 85 BF 20 E2 
AC 85 20 C2 AE 20 E2 86 96 20 E2 93 82
```

UTF-8文字列です。かんたんですね。

➡ ✝ 🅰 〰 ⬅ 🎁 🅿 ⬅ ® ↖ Ⓜ

最初と最後は→tAW←、P←R(左上)Mと読めます。まん中はプレゼントの絵文字です。矢印を数字に対応させるには、格ゲーの技入力と同じ方法を使います。

```
789
456 (パソコンのテンキー配列です。
123  電話のテンキーとは上下逆ですね)
```

答: 6taw4presentp4r7m

★Part 5: 2015/7/6 SWEVEN

[https://jojoingresswotd.github.io/2015/25/SWEVEN.html](https://jojoingresswotd.github.io/2015/25/SWEVEN.html)

```
02 89 4A F9 0F 02 A8 19 F9 0F 02 C8 19 F9 0F 02 
68 19 F9 0F 02 89 4A F9 0F 02 A8 C9 2E 02 C8 19 
F9 0F 02 A8 19 F9 0F 02 69 69 F9 0F 02 A8 C9 2E 
02 C8 C9 2E 02 D9 89 2E 02 A8 C9 2E 02 C8 C9 2E 
02 C8 19 F9 0F 02 A8 C9 2E 02 A8 19 F9 0F 02 D9 
89 2E 02 69 69 F9 0F 02 68 19 F9 0F 02 A8 C9 2E 
02 68 19 F9 0F 02 C8 19 F9 0F 02 D9 89 2E 02 C8 
C9 2E 02 C8 19 F9 0F 02 89 4A F9 0F 02 68 19 F9 
0F 02 D9 89 2E 02 C8 C9 2E 02 C8 C9 2E 02 D9 89 
2E 02 68 19 F9 0F 02 69 69 F9 0F 02 C8 C9 2E 02 
D9 89 2E 02 C8 19 F9 0F 02 69 69 F9 0F 02 89 4A 
F9 0F 02 68 19 F9 0F 02 69 69 F9 0F 02 A8 C9 2E 
02 C8 C9 2E 02 68 19 F9 0F 02 C8 19 F9 0F 02 D9 
89 2E 02 69 69 F9 0F 02 A8 19 F9 0F 02 69 69 F9 
0F 02 A8 C9 2E 02 C8 19 F9 0F 02 D9 89 2E 02 89 
4A F9 0F 02 A8 C9 2E 02 89 4A F9 0F 02 68 19 F9 
0F 02 A8 19 F9 0F 02 A8 C9 2E 02 69 69 F9 0F 02 
68 19 F9 0F 02 C8 C9 2E 02 A8 19 F9 0F 02 C8 19 
F9 0F 02 A8 19 F9 0F
```

これもかなり苦戦しました。実は16進ダンプとして解釈する前に、全体を逆順にします。するとUTF-8になります。手の形の絵文字がたくさん出てきました。

👊 👌 👊 ✌ 👆 🖖 ✊ 👊 👆 🤘 ✊ 🤘 ☝ 👌 ✊ 🖖 👊 🖖 ☝ 👌 👆 ✌ ✊ 🖖 👆 🤘 🖖 👌 ☝ ✌ 🖖 👆 ☝ ✌ ✌ ☝ 👆 🤘 👌 ✌ ☝ 👌 👆 ✊ 👆 🖖 ☝ 👊 ✊ 👌 ✌ ✊ ☝ ✌ ✊ 🖖 👊 👌 ✊ 🤘 👆 👌 👊 🤘

「🤘」はSign Of The Hornsという絵文字で、グーから人差し指と小指を立てたサインです。「🖖」はRaised Hand with Part Between Middle and Ring Fingersという文字です。形を説明する名前になってますが、ようするにミスタースポックのサインです。

立てている指の数を数字に直すと「0302130012021303031312031233123112211232131013100320120303021302」となります。4桁ずつに区切って4進数とみなすとアスキーコードになります。

答: 2pbs7comintt8c2r

★Part 6: 2015/7/7 DAPOCAGINOUS

[https://jojoingresswotd.github.io/2015/25/DAPOCAGINOUS.html](https://jojoingresswotd.github.io/2015/25/DAPOCAGINOUS.html)

```
D8 3D DC 09 D8 3D DC 10 D8 3D DC 12 D8 3D DC 0D 
D8 3D DC 12 D8 3D DC 10 D8 3D DC 12 D8 3D DC 02 
D8 3D DC 09 D8 3D DC 05 D8 3D DC 13 D8 3D DC 10 
D8 3D DC 12 D8 3D DC 13 D8 3D DC 13 D8 3D DC 12 
D8 3D DC 13 D8 3D DC 0E D8 3D DC 12 D8 3D DC 0D 
D8 3D DC 13 D8 3D DC 09 D8 3D DC 15 D8 3D DC 05 
D8 3D DC 09 D8 3D DC 0E D8 3D DC 13 D8 3D DC 13 
D8 3D DC 09 D8 3D DC 05 D8 3D DC 13 D8 3D DC 12
```

UTF-16表現された絵文字です。UTF-16には、16ビットにおさまらないコードポイントを表現するためにサロゲートペアという仕様があり、それを使っています。

🐉🐐🐒🐍🐒🐐🐒🐂🐉🐅🐓🐐🐒🐓🐓🐒🐓🐎🐒🐍🐓🐉🐕🐅🐉🐎🐓🐓🐉🐅🐓🐒

動物がずらっと並びました。ひとつが数字1桁に対応しそうです。2桁ずつペアにしてアスキーコードになるはずです。数字位置に必ずドラゴンがいますから、10進数ならこれが5、16進数なら3になるはず。しかしbrute forceしてみてもうまく合いません。よく見ると、動物は全部干支でした! 12個あるから12進数だっ! ということで子=0、…亥=11の番号を振って、2桁ずつ12進数と解釈するとアスキーコードになりました。

答: 7ega2sitrepz6u2t

★Part 7: DAGGLE

[https://jojoingresswotd.github.io/2015/25/DAGGLE.html](https://jojoingresswotd.github.io/2015/25/DAGGLE.html)

```
f7 cd 3a f7 cd 3c f7 cd 3c f7 cd 3d f7 cd 3c f7 
cd 3d f7 cd 3a f7 cd 74 f7 cd 3c f7 cd 3d f7 cd 
3c f7 cd 3d f7 cd 3d f7 cd 74 f7 cd 39 f7 cd 3c 
f7 cd 39 f7 cd 3d f7 cd 3a f7 cd 74 f7 cd 39 f7 
cd 3d f7 cd 38 f7 cd 39 f7 cd 38 f7 cd 35 f7 cd 
38 f7 cd 39 f7 cd 3d f7 cd 74 f7 cd 3a f7 cd 3d 
f7 cd 39 f7 cd 75 f7 cd 3b f7 cd 3a f7 cd 3c f7 
cd 3d f7 cd 3c f7 cd 3d f7 cd 3d f7 cd 74
```

Base64エンコードするとこうなりました。

`980698089808980998089809980698109808980998089809980998109805980898059809980698109805980998049805980498019804980598099810980698099805981198079806980898099808980998099810`

4つずつに区切ると 9800～9811 という10進数です。これがユニコードコードポイントなのでしょう。

♎♐♐♑♐♑♎♒♐♑♐♑♑♒♍♐♍♑♎♒♍♑♌♍♌♉♌♍♑♒♎♑♍♓♏♎♐♑♐♑♑♒

十二宮の絵文字が出てきました! 干支のときと同じように、おひつじ座=0、うお座=11を振って12進数と解釈します。逆順にして「viiZGQv515EREDviiRiiP」となりました。ローマ数字を数字に、数字をローマ数字にすると「7zgq5vivered7r2p」です。vivereはイタリア語で英語のliveに対応します。

答: 7zgq5lived7r2p

★おまけ: ユニコードと絵文字について

ユニコードに絵文字が入ったおかげで、世界が広がりましたね。このあたりの歴史は小形克宏さんのすばらしい記事がいくつかあるので、興味のある方はぜひ読んでみてください。

- [https://japan.cnet.com/sp/column_emojipandora/20389042/](https://japan.cnet.com/sp/column_emojipandora/20389042/)
- [https://internet.watch.impress.co.jp/docs/special/20150530_704559.html](https://internet.watch.impress.co.jp/docs/special/20150530_704559.html)

ちなみに小形さんは、まんが家の青木光恵さんの旦那さんだそうですね。

----

[戻る](index.html)
