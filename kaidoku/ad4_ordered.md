# 2014/09/17 Access Dive 4解読 その3

Access Dive 4の問題を解いています。
Access Diveとは何か、解いてどんなうれしいことがあるのかは「[その1](./ad4_intro.md)」をご覧ください。

今回はまん中の二重丸ノードの右下にある「Proceed as ordered」です。

ネタバレアラートの改行、一応入れときますね。

<br/><br/><br/><br/><br/><br/>

いいですか? では進みましょう

<br/><br/><br/><br/><br/><br/>

今回のパズルも画像です。何が書いてあるかと言うと

```
FOR YOUR EYES ONLY

YOU KNOW WHAT TO DO.
PROCEED AS ORDERED

A-KEH-DI-GLINI-TKIN-9-
DAH-NES-TSA-CLA-GI-AIH-6-
2-AH-NAH-AL-NA-AS-DZOH-1
```

指令書なので暗号で書いてあるはずです。

`A-KEH-DI-GLINI-TKIN` でぐぐると

- Navajo Code Talkers' Dictionary
- [https://www.history.navy.mil/research/library/online-reading-room/title-list-alphabetically/n/navajo-code-talker-dictionary.html](https://www.history.navy.mil/research/library/online-reading-room/title-list-alphabetically/n/navajo-code-talker-dictionary.html)

というサイトがヒットします。なんとnavy.milのサイトですね!
1945年6月改訂、って、米海軍で実際に使われていた暗号なのでしょうか。
画像は陸軍っぽい感じですけどね。

この表にしたがって上の暗号文を復号すると

```
V I 9
R P 6
2 E X 1
```

となります。小文字にしすると

`vi9rp62ex1`

パスコードの形式にも合っていますね。
キーワードが「vi」と短いですが、ちゃんと一覧にも載っています。
「vi」とはこのAccess DiveをやっているVerum Inveniriのことですね。

このまま正解でした。ノード「14-5」がアンロックされました。

発見した日に、これをパスコードとして入力すると

`50XM,50AP,4x L1 XMP, 4x L1 Reso`

がもらえました。残念ながら現在はすでにfully redeemedです。

今回はカンタンでしたね。ぐぐるのは反則じゃないですよ!
[次回は「14-5」を解説します](./ad4_14-5.md)。

----

[戻る](index.html)
