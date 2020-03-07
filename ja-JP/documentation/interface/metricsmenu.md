---
published: true
layout: default.ja
title: メトリックメニュー
---
<!--
published: true
layout: default
title: The Metrics Menu
-->

<!--
This menu is not present in the Bitmap View, and the Metrics View only
contains "Center in Width" and "Thirds in Width".
-->
このメニューはビットマップビューには表示されません。
また、メトリックビューの表示では
<span class="command">幅の中央に</span>
と
<span class="command">両幅の空きを1:2に</span>
だけを含みます。


[table_of_contents]


<!--
#### Center in Width
-->
#### 幅の中央に

<!--
In the Outline and Metrics Views this centers the current glyph (makes
its lbearing be the same as its rbearing) within the current width.
-->
アウトラインビューとメトリックビューでは、このコマンドは現在のグリフを現在のグリフ幅の中で中央に配置します
(左サイドベアリングと右サイドベアリングを均等にします)。

<!--
In the Font View the same thing is done for all selected glyphs.
-->
フォントビューでは、同じことを選択中のすべてのグリフに対して行います。

<!--
Setting this value will adjust all layers so that guides in the background etc.
will be adjusted with the rest of the glyph.
-->
この値を設定すると、すべてのレイヤーが調整されることになります。
その結果、背景などにあるガイドがグリフの残りで調整されます。

<!--
#### Thirds in Width
-->
#### 両幅の空きを1:2に

<!--
This is very like Center in Width above... except that I happen to
prefer having a bit more white space after my glyphs than before them.
So this command makes the rbearing twice the lbearing (instead of making
them be the same).
-->
これは上の
<span class="command">幅の中央に</span>
と非常によく似ています…
私の好みではグリフの後ろのスペースを前のスペースより少し多めに取りたがることを除いては。
そのため、このコマンドは右サイドベアリングを左サイドベアリングの 2 倍に (均等ではなく) 設定します。

<!--
Setting this value will adjust all layers so that guides in the background etc.
will be adjusted with the rest of the glyph.
-->
この値を設定すると、すべてのレイヤーが調整されることになります。
その結果、背景などにあるガイドがグリフの残りで調整されます。

<!--
#### Window Type
-->
#### ウィンドウタイプ

<!--
In the Metrics View, the window may behave in different ways.
-->
メトリックビューでは、
ウィンドウの挙動が異なる場合があります。


<!--
##### Kerning Only
-->
##### カーニングのみ

<!--
This metrics view may only be used to adjust kerning
-->
このメトリックビューでは、
カーニングの調整のみが使用できます。


<!--
##### Advance Width Only
-->
##### 送り幅のみ

<!--
This metrics view may only be used to adjust the advance widths of
glyphs
-->
このメトリックビューでは、
グリフの送り幅の調整のみが使用できます。

<!--
##### Both
-->
##### 両方

<!--
This metrics view will adjust either the advance width or kerning
-->
このメトリックビューでは、
送り幅かカーニングのどちらか一方の調整が使用できます。


<!--
#### Set Width...
-->
#### 幅を設定...

![](/assets/img/filemenu-setwidth.png)

<!--
The Set Width command allows you to change the width of the current
glyph (in the outline view) or all selected glyphs (in the font view).
You may either set the width to an absolute value, change the width by
adding a constant value to it, or multiply it by a scale factor.
Normally the width will be expressed in em-units, but in a bitmap only
font the width will be expressed as pixels in the current displayed
font.
-->
<span class="command">幅を設定</span>
コマンドを使うと、
(アウトラインビュー内では) 現在のグリフの幅を、
または (フォントビューでは) 選択中のすべてのグリフの幅を変更することができます。
幅の絶対値を指定することもできますし、
一定の値を加えるかある拡大率を掛けるかによって現在の値を変更することもできます。
通常、幅は em ユニットで表されますが、
ビットマップのみのフォントでは、
幅は現在表示されているフォントにおけるピクセル数で表現されます


<!--
#### Set LBearing...
-->
#### 左サイドベアリングを設定...

<!--
The Set LBearing command is similar to the Set Width command above, the
dialog is pretty much the same except that it applies to the left side
bearing rather than to the width.
-->
<span class="command">左サイドベアリングを設定</span>
コマンドは、上の
<span class="command">幅を設定</span>
コマンドに似ています。
ダイアログは非常に良く似ていて、
適用されるのが幅ではなくて左サイドベアリングである点だけが違います。

<!--
Setting this value will adjust all layers so that guides in the background etc.
will be adjusted with the rest of the glyph.
-->
この値を設定すると、すべてのレイヤーが調整されることになります。
その結果、背景などにあるガイドがグリフの残りで調整されます。

<!--
#### Set RBearing...
-->
#### 右サイドベアリングを設定...

<!--
The Set RBearing command is similar to the Set Width command above, the
dialog is pretty much the same except that it applies to the right side
bearing rather than to the width.
-->
<span class="command">右サイドベアリングを設定</span>
コマンドは、上の
<span class="command">幅を設定</span>
コマンドに似ています。
ダイアログは非常に良く似ていて、
適用されるのが幅ではなくて右サイドベアリングである点だけが違います。


<!--
#### Auto Width...
-->
#### 幅の自動設定...

<!--
This command is only available in the font view. [It attempts to guess
reasonable values for the widths](../autowidth/#AutoWidth) (more
accurately the left and right bearings) of the specified glyphs.
-->
このコマンドはフォントビューでのみ使用可能です。
このコマンドは、指定された各グリフの
[適切な送り幅を推測しようと試みます](../../reference/autowidth/#AutoWidth)
(より正確には左右のサイドベアリングを推測しようと試みます)。


<!--
#### Kern By Classes...
-->
#### クラス毎のカーニング...

<!--
This command is only available from the font and metrics views. It
provides the user with a [dialog](../metricsview/#kernclass) to
manipulate kerning classes.
-->
このコマンドはフォントビューとメトリックビューでのみ使用可能です。
このコマンドによって、カーニングクラスを操作する
[ダイアログ](../metricsview/#クラス毎のカーニング)
を呼び出すことができます。


<!--
#### Remove All Kern Pairs
-->
#### カーニングをすべて削除

<!--
In the font view removes all kern pairs (and kern classes) in the font.
-->
フォントビューでは、フォント内のすべてのカーニングペア (とカーニングクラス) を削除します。

<!--
In the outline glyph view removes all kern pairs where the current
glyph is the left hand glyph.
-->
アウトライングリフビューでは、現在のグリフを左側のグリフとして含むすべてのカーニングペアを削除します。

<!--
Not present in the Metrics or Bitmap views.
-->
メトリックビューやビットマップビューではこの項目は表示されません。


<!--
#### Kern Pair Closeup...
-->
#### カーニングペアの詳細...

<!--
(Sorry about the name, I couldn't think of a better).
[Allows](../metricsview/#kernpair) you to get a look at kerning between
two glyphs at different point-sizes and to build a "[Device
Table](../metricsview/#DeviceTable)" (which allows small corrections
from the standard behavior at specified point sizes)
-->
(解りにくい名前ですみません。 
「詳細」(Closeup) よりいい名前が思いつかなかったのです)。
異なるポイントサイズにおける 2 つのグリフ間のカーニングを [見ることができ](../metricsview/#kern-pair-closeup) 、
[<span class="command">デバイステーブル</span>](../metricsview/#デバイステーブル)
を構築することができます
(このテーブルを用いると、指定されたポイントサイズにおいて標準とは少し異なるふるまいを指定することが可能です)

<!--
Not present in the Bitmap view.
-->
ビットマップビューには存在しません。


<!--
#### VKern By Classes...
-->
#### クラス毎の縦書きカーニング

<!--
This command is only available from the font and metrics views. It
provides the user with a [dialog](../metricsview/#kernclass) to
manipulate vertical kerning classes.
-->
このコマンドはフォントビューとメトリックビューでのみ使用可能です。
このコマンドによって、縦書き用のカーニングクラスを操作する
[ダイアログ](../metricsview/#クラス毎のカーニング)
を呼び出すことができます。


<!--
#### VKern From HKern
-->
#### 横書きカーニングを縦書きに

<!--
This command is only available from the font and metrics views. It
removes all current vertical kerning information, then it looks through
the font and for each pair of horizontally kerned glyphs where both have
a 'vert' or 'vrt2' feature it produces a vertical kerning pair for the
vertical versions of those glyphs. (That is: If `A`+`V` are horizontally
kerned by -50 and `A` =\> `A.vert` and `V` =\> `V.vert `then this
command will produce a vertical kerning pair between `A.vert` + `V.vert`
with a value of -50)
-->
このコマンドはフォントビューとメトリックビューでのみ使用可能です。
このコマンドは、現在の縦書きカーニング情報を削除し、
その後フォント全体を検索し、
横書き用のカーニングを持つグリフの対で、
両方のグリフが 'vert' または 'vrt2' 機能を持っている物に対して、
それらのグリフの縦書き版を作成します。
(つまりこういうことです:
`A`+`V` が横書き時に -50 だけカーニングされ、
`A` =\> `A.vert` と `V` =\> `V.vert` が存在する時にこのコマンドを実行すると、
`A.vert` + `V.vert` の組み合せに、-50 のカーニング値が設定されます。)


<!--
#### Remove All VKern Pairs
-->
#### 縦書きカーニングをすべて削除

<!--
In the font view removes all vertical kern pairs (and kern classes) in
the font.
-->
フォントビューでは、フォント内の縦書きカーニングペア (とカーニングクラス) をすべて削除します。

<!--
In the outline glyph view removes all kern pairs where the current
glyph is the left hand glyph.
-->
アウトライングリフビューでは、現在のグリフが左側のグリフであるすべてのカーニングペアを削除します。

<!--
Not present in the Metrics or Bitmap views.
-->
メトリックビューやビットマップビューには存在しません。


<!--
#### Set Vertical Advance...
-->
#### 縦書き時のグリフ幅を設定...

<!--
If vertical metrics are enabled for the font this will be active in the
font and outline glyph view.
-->
そのフォントで縦書きメトリックが使用可能なときは、
フォントビューとアウトライングリフビューでこれがアクティブになっています。

<!--
It behaves exactly like Set Width... except it works on the vertical
advance rather than the horizontal advance (width).
-->
これは
<span class="command">幅を設定...</span>
と同じですが、
横書き用の送り幅 (グリフの幅) ではなく縦書き用の送り幅を設定する点が異なります。
