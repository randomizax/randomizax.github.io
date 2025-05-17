<head>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Mono&display=swap" rel="stylesheet">
  <style>
    code, pre {
      font-family: 'Noto Sans Mono', monospace;
    }
  </style>
</head>


# 2014/09/22 Access Dive 4解読 その6

Access Dive 4の問題を解いています。
Access Diveとは何か、解いてどんなうれしいことがあるのかは「[その1](./ad4_intro.md)」をご覧ください。

今回は右下の方にある「Gigantic」です。

一応ネタバレアラートで空行入れときます。

<br/><br/><br/><br/><br/><br/>

今回のヒントは、テキストです。大きなVIのロゴの下に、こんなテキストがあります。

```
G I G A N T I C  C A V E  A D V E N T U R E !
Copyright ( C ) 1979 Verum Inveniri

$ PWD
/
$ VISH
LOADING MODULE /USR/5580/PAMX... DONE. PRESS [RETURN] TO CONTINUE
> ADVENT_
```

「巨大洞窟アドベンチャー」「続行するには[RETURN]を押してください」

ゲーム画面のようです。ここでRETURNを押すと、ゲームがロードされますが、
自分で遊ぶことはできず、誰かのリプレイが自動的に進んでいきます。

70年代にあった「テキストアドベンチャー」というジャンルのゲームのようです。
テキストアドベンチャーは、絵やイラスト、グラフィックが一切なく、文字だけで
状況を説明し、次の行動を英語で入力することで進めていくゲームです。

私は80年代、ZORKという有名な3部作テキストアドベンチャーに相当ハマりました。
ダンジョン内でどろぼうと格闘したり、3つの台座に3つの宝石を正しい順序で置いたり、
虹の上を歩いたり。絵がまったくないだけに、情景はすべて自分の想像力で描きます。
「手を振る」の「振る」に当たる英語の動詞がわからなくて苦労しました。
当時の攻略本を見ながらZORK I, IIはクリアしたのですが、IIIは挫折しました。

昔話はともかく。

このゲームは自分でプレイする必要はなく、リプレイを見ればいいようです。

    You awake to find yourself in a field. The entrance to a tunnel marked "TWO" beckons you forward.
    > enter

    目覚めるとあなたは野原にいる自分に気がつきました。「TWO」と書かれたトンネルの入口が誘っているようです。
    > 入る

    After crawling through the tunnel, you emerge into a small square room. A door quickly seals the entrance behind you. There are exits to the west, east, and south.
    トンネルを這って進むと、小さい正方形の部屋に着きました。あなたの後ろで、ドアが素早く入口をふさいでしまいました。出口は西、東、南にあります。

    > jump
    You jump straight up, and land in place.
    > jump
    You jump straight up, and land in place.
    > jump
    You jump straight up, and land in place.
    > east
    You are in a small square room. There are exits to the west and south.
    > jump

    > ジャンプ
    あなたはまっすぐ飛び上がり、同じ場所に着地しました。
    > ジャンプ
    あなたはまっすぐ飛び上がり、同じ場所に着地しました。
    > ジャンプ
    あなたはまっすぐ飛び上がり、同じ場所に着地しました。
    > 東
    あなたは小さい正方形の部屋にいます。出口は西、南にあります。

こんな感じのテキストが延々と続きます。途中でモンスターらしき音が聞こえたり
赤い目を見たりしつつ逃げ回り、最終的には天井の隠し扉にあった梯子から脱出しました。
でも何もお宝を得ることはできなかったので0点、というログです。
いちばん最後はこんなでした。

    You climb the ladder and carefully crawl through the tunnel, eventually making your way blinking back into the sunlight. As you exit the tunnel, you see a crudely shaped FIVE carved into the rock face.
    You have escaped the cave!
    You did not collect any treasures. You did not score any points. Your ankles ache painfully.
    GAME OVER
    > exit

    あなたは梯子を登り、注意深くトンネルを這い、ついに太陽の下に戻りました。トンネルを出るとき、岩には乱暴に「5」と刻まれていました。
    あなたは洞窟を脱出しました!
    お宝を何も獲得しませんでした。スコアは0点です。かかとがすごく痛みます。
    ゲームオーバー
    > exit

ゲームのログは長いのでここでは途中を省略しますが、
やっていることは同じような正方形の小部屋をあちこち移動し、
用もないのにjumpをくり返し、時々waitしているだけでした。

この手のゲームを遊ぶときの定石はマッピングです。
ゲーム内に訪れた部屋の順序と、部屋のつながり具合
(出口の方向)を図にするとこんなでした。
ついでに各部屋で何をしたかも書いておきます。

```
┏━━━━┓　┏━━━━┓　┏━━━━┓
┃⑱１　　┃　┃①３⑲　┃　┃②⑩２⑳┃
┃　　　　┗━┛　　　　┗━┛　　　　┃
┃　　　　┏━┓　　　　┏━┓　　　　┃
┃　　　　┃　┃　　　　┃　┃　　　　┃
┗━┓┏━┛　┗━┓┏━┛　┗━┓┏━┛
　　┃┃　　　　　┃┃　　　　　┃┃　　
┏━┛┗━┓　┏━┛┗━┓　┏━┛┗━┓
┃⑰　　　┃　┃㉔２ｗ３┃　┃③３⑨⑪┃
┃　　　　┗━┛ｗ４ｕ　┗━┛⑬３㉑　┃
┃　　　　┏━┓　　　　┏━┓　　　　┃
┃　　　　┃　┃　　　　┃　┃　　　　┃
┗━┓┏━┛　┗━┓┏━┛　┗━┓┏━┛
　　┃┃　　　　　┃┃　　　　　┃┃　　
┏━┛┗━┓　┏━┛┗━┓　┏━┛┗━┓
┃⑥３⑯　┃　┃⑤⑦１⑮┃　┃④⑧⑫２┃
┃　　　　┗━┛㉒　　　┗━┛ｗ５⑭４┃
┃　　　　┏━┓　　　　┏━┓㉒５　　┃
┃　　　　┃　┃　　　　┃　┃　　　　┃
┗━━━━┛　┗━┓┏━┛　┗━━━━┛
　　　　　　　　　┃┃　　　　　　　　　
```

丸数字は部屋を訪れた順、丸のない数字はjumpした回数、
wはwait、uはup(脱出)です。こんな風に読んでください。
```
  ①の部屋から入り、jumpを3回、eastで②の部屋に移動
  southで③の部屋に移動、jump3回、
  south, west, west で④⑤⑥と移動、jump3回…
```

⑤の部屋からさらに下にも部屋があることが出口の方向からわかりますが、
その部屋には入っていません。お宝があったかもしれないのに。
そして各部屋で無意味にjumpをくり返しています。

この部屋の並び方、一見無意味に思えるjump、何か思いつきますか。
最後の部屋㉔ではjumpと同時に天井からたれ下がっているロープを
引っぱったりしています。でもあとちょっとで出られるというときに「wait」して、
ゲームから「こんな状況でも待つっていうのかい? まあいいけど」とか
言われてしまっています。

3x3に並んだ正方形で複数回何かするというと…

携帯電話のキーですね。参考画像
-  [http://upload.wikimedia.org/wikipedia/commons/thumb/0/03/Telephone_number_pad_2.jpeg/1280px-Telephone_number_pad_2.jpeg](http://upload.wikimedia.org/wikipedia/commons/thumb/0/03/Telephone_number_pad_2.jpeg/1280px-Telephone_number_pad_2.jpeg)

パソコンのテンキーと電話のテンキーは並びが違うので注意が必要です。
そういえば入口のあった部屋には「TWO」、
脱出した部屋には「FIVE」と名前がついていましたね。
そのことから、電話の方であるとわかります。

8の部屋の南にはきっと0に対応した部屋があるのだと思います。
携帯電話で英語を入力する場合、同じボタンを何度も押す必要があります。
jumpする回数はボタンを押す回数に対応しているに違いありません。
それに、同じボタン上の文字を連続で入力する場合、
間でちょっと待たないといけません。
それが「wait」コマンドに対応しているのでしょう。

問題のゲームログでプレイヤーが取った行動のとおりに移動し、
各部屋でjumpした回数が英字を入力しているとすると、
入力したかった文字はこうなります。

`cortex9oz19kl5`

これはパスコードの形式に合っています。キーワード「cortex」は
よく使うキーワード一覧には載っていませんが、Access Dive 4が
始まるときの紹介文の中に出現していました。

これがこの問題の正解で、これによってノード「Intercepted signal」が
アンロックされました。ちなみにIntercepted signalも音の問題です。

解説した時点でパスコードはfully redeemedでした。残念。

ダンジョンゲームの基本はやはりマッピングですね!
今回、あまりに長いので全部を丹念に読むのはくじけかけたのですが、
一見無意味なjumpに意味があると考えて、マップを描いてみたことで解けました。

[次回は「Dolls inside dolls」です](./ad4_dolls.md)。
実を言うと、Dolls inside dollsには3つの答があるのですが
そのうち1つしか解けていません。

ここから先は、「ここまでわかった、残りを手伝ってほしい」という
投稿になっていきます。ぜひみなさんの力を貸してくださいね。

----

[戻る](index.html)
