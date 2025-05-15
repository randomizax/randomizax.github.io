# 2016/02/19

最近なかなかJojoさんの解読に取り組めていませんでしたが、ひさびさに2/18分ADROITの出題で一番乗り取れました!

https://plus.google.com/+JoJoStratton/posts/RErnhVhz1a3

では解説。問題文はこうでした
`MMRRWBIIRCCBYIRGCRRIRMIRCIRICBYCRCIRRCRMCB`

今週の流れのANSIカラーでエスケープシーケンスの `ESC [ 3 3 m` みたいなアレで数字に直します。でもちょっと待って、Iって何色? ここが一番時間がかかったところで、今回のポイントでした。

RGB各1ビットの3ビットカラーはこんな感じです。各色ビットの並び順は普段HTMLとかで使うR→G→Bの順とは逆で、上の桁からB→G→Rの順になります。

|数|和名|英名|
|:---:|:---:|:---|
|0|黒|black|
|1|赤|red|
|2|緑|green|
|3|黄|yellow|
|4|青|blue|
|5|紫|magenta|
|6|水|cyan|
|7|白|white|

頭文字を取ると「`BRGYBMCW`」。あー、Bが2つありますね。黒と青を区別するために、一般的には黒を「blacK」のK、青を「Blue」のBとして区別します。ですが、今回は黒をblackのB、青をindigo(インディゴ)のIにしたのですね。

というわけで、「`BRGYIMCW`」を「01234567」に対応させて変換すると

`551170441660341261141541641460361641161560`

3桁ずつ区切ってみましょう。

`551 170 441 660 341 261 141 541 641 460 361 641 161 560`

逆順で数字位置になる場所は最後の桁が0になっています。全体を逆順にしてみましょう。

`065 161 146 163 064 146 145 141 162 143 066 144 071 155`

あっこれ、今週何度も見た8進数ですね。

`http://tools.decodeingress.me/#/basic` のOctalのところにペーストすると、Textのところに正解が出ます。

`5qfs4fearc6d9m`

これで正解。ちなみにRubyで解くとこんな感じです。

```ruby
'MMRRWBIIRCCBYIRGCRRIRMIRCIRICBYCRCIRRCRMCB'.tr('BRGYIMCW','0-7').reverse.scan(/.../).map{|s|s.to_i(8).chr}.join
```

ではまた!
