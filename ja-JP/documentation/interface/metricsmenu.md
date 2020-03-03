---
published: true
layout: default.ja
title: メトリックメニュー
---

<!--
This menu is not present in the Bitmap View, and the Metrics View only
contains "Center in Width" and "Thirds in Width".
-->
本メニューはビットマップビューでは表示されません。
メトリックビューでは "幅の中央 (Center in Width)" と "幅の3番目 (Thirds in Width)" のみが表示されます。

[table_of_contents]


#### Center in Width

<!--
In the Outline and Metrics Views this centers the current glyph (makes
its lbearing be the same as its rbearing) within the current width.
-->
アウトラインビューとメトリックビューでは、
現在のグリフを現在の幅の中央に配置します
（左ベアリングと右ベアリングとが同じ値になるようにします）。

<!--
In the Font View the same thing is done for all selected glyphs.
-->
フォントビューでは、
選択したすべてのグリフに対して同様の処理が行われます。

<!--
Setting this value will adjust all layers so that guides in the background etc.
will be adjusted with the rest of the glyph.
-->
この値を設定すると、すべてのレイヤーが調整されることになります。
その結果、背景などにあるガイドがグリフの残りで調整されます。

#### Thirds in Width

<!--
This is very like Center in Width above... except that I happen to
prefer having a bit more white space after my glyphs than before them.
So this command makes the rbearing twice the lbearing (instead of making
them be the same).
-->
このコマンドは、グリフの後方の空白を少し多めにとる以外は、
上記の Center in Width と非常によく似ています。

<!--
Setting this value will adjust all layers so that guides in the background etc.
will be adjusted with the rest of the glyph.
-->
そのため、このコマンドは
（右ベアリングを左ベアリングと同じ値にするのではなく）
右ベアリングが左ベアリングの2倍になるよう設定します。

#### Window Type

<!--
In the Metrics View, the window may behave in different ways.
-->
メトリックビューでは、
ウィンドウの挙動が異なる場合があります。


##### Kerning Only

<!--
This metrics view may only be used to adjust kerning
-->
メトリックビューでは、
カーニングの調整のみが使用できます。


##### Advance Width Only

<!--
This metrics view may only be used to adjust the advance widths of
glyphs
-->
メトリックビューでは、
グリフの拡張幅の調整のみが使用できます。

##### Both

<!--
This metrics view will adjust either the advance width or kerning
-->
メトリックビューでは、
拡張幅かカーニングのどちらか一方が使用できます。


#### Set Width...

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
"幅の設定 (Set Width)" コマンドを使用すると、
現在のグリフ（アウトラインビューの場合）または選択したすべてのグリフ（フォントビューの場合）の幅を変更できます。
幅の設定は、絶対値を設定するか、一定の値を加算するか、倍率を設定するかのいずれかの方法が使用できます。
通常、幅は em 単位で表現されますが、
ビットマップのみのフォントでは、幅は現在表示されているフォントのピクセル数で表現されます。


#### Set LBearing...

<!--
The Set LBearing command is similar to the Set Width command above, the
dialog is pretty much the same except that it applies to the left side
bearing rather than to the width.
-->
"Set LBearing" コマンドは、上記の "Set Width" コマンドと同様ですが、
ダイアログで設定した内容は、幅ではなく、左側のベアリング（余白）に適用されます。

<!--
Setting this value will adjust all layers so that guides in the background etc.
will be adjusted with the rest of the glyph.
-->
この値を設定すると、すべてのレイヤーが調整されることになります。
その結果、背景などにあるガイドがグリフの残りで調整されます。

#### Set RBearing...

<!--
The Set RBearing command is similar to the Set Width command above, the
dialog is pretty much the same except that it applies to the right side
bearing rather than to the width.
-->
"Set RBearing" コマンドは、上記の "Set Width" コマンドと同様ですが、
ダイアログで設定した内容は、幅ではなく、右側のベアリング（余白）に適用されます。


#### Auto Width...

<!--
This command is only available in the font view. [It attempts to guess
reasonable values for the widths](../autowidth/#AutoWidth) (more
accurately the left and right bearings) of the specified glyphs.
-->
このコマンドは、フォントビューでのみ使用できます。
指定されたグリフについて、
[妥当な幅の推測を試みる](../../reference/autowidth/#AutoWidth)
正確にいうと、左右のベアリングの値の推測を試みます。


#### Kern By Classes...

<!--
This command is only available from the font and metrics views. It
provides the user with a [dialog](../metricsview/#kernclass) to
manipulate kerning classes.
-->
このコマンドは、フォントビューとメトリックビューからのみ使用できます。
ユーザーにカーニングクラスを操作するための
[ダイアログ](../metricsview/#クラスを用いたカーニング)
を提供します。


#### Remove All Kern Pairs

<!--
In the font view removes all kern pairs (and kern classes) in the font.
-->
フォントビューでは、フォント内のすべてのカーニングペア（およびカーニングクラス）が削除されます。

<!--
In the outline glyph view removes all kern pairs where the current
glyph is the left hand glyph.
-->
アウトライングリフビューでは、現在のグリフが left hand glyph であるすべてのカーニングペアが削除されます。

<!--
Not present in the Metrics or Bitmap views.
-->
メトリックビューまたはビットマップビューには存在しません。


#### Kern Pair Closeup...

<!--
(Sorry about the name, I couldn't think of a better).
[Allows](../metricsview/#kernpair) you to get a look at kerning between
two glyphs at different point-sizes and to build a "[Device
Table](../metricsview/#DeviceTable)" (which allows small corrections
from the standard behavior at specified point sizes)
-->
（すみません、もっとよい名前を思いつきませんでした）。
ポイントサイズが異なる2つのグリフ間のカーニングを求め、
（指定したポイントサイズの標準的な動作から少し修正することを許容することで）
"[デバイステーブル](../metricsview/#デバイステーブル)"
を構築することを
[許可](../metricsview/#kern-pair-closeup)
します。

<!--
Not present in the Bitmap view.
-->
ビットマップビューには存在しません。


#### VKern By Classes...

<!--
This command is only available from the font and metrics views. It
provides the user with a [dialog](../metricsview/#kernclass) to
manipulate vertical kerning classes.
-->
このコマンドは、フォントビューおよびメトリックビューからのみ使用できます。
これは、垂直カーニングクラスを操作するための
[ダイアログ](../metricsview/#クラスを用いたカーニング)
をユーザーに提供します。


#### VKern From HKern

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
このコマンドは、フォントビューおよびメトリックビューからのみ使用できます。
このコマンドは現在のすべての垂直カーニング情報を削除してから、
フォントと水平方向にカーニングされたグリフの各ペアの両方が
'vert' または 'vrt2' 機能を持つことを調べ、
それらのグリフの垂直バージョンについて垂直カーニングペアを生成します。
（つまり： `A`+`V` が -50 水平カーニングされており、
さらに `A` =\> `A.vert`　かつ `V` =\> `V.vert` の場合、
このコマンドは、
`A.vert` + `V.vert` 間に -50 の値を持つ垂直カーニングペアを生成します）


#### Remove All VKern Pairs

<!--
In the font view removes all vertical kern pairs (and kern classes) in
the font.
-->
フォントビューでは、フォント内のすべての垂直カーニングペア（およびカーニングクラス）が削除されます。

<!--
In the outline glyph view removes all kern pairs where the current
glyph is the left hand glyph.
-->
アウトライングリフビューでは、現在のグリフが left hand glyph であるすべてのカーニングペアが削除されます。

<!--
Not present in the Metrics or Bitmap views.
-->
メトリックビューまたはビットマップビューには存在しません。


#### Set Vertical Advance...

<!--
If vertical metrics are enabled for the font this will be active in the
font and outline glyph view.
-->
フォントの垂直メトリックが有効な場合、
このコマンドはフォントビューとアウトライングリフビューで有効化されます。

<!--
It behaves exactly like Set Width... except it works on the vertical
advance rather than the horizontal advance (width).
-->
"Set Width" とまったく同じように動作しますが、
水平方向の移動量（幅）ではなく垂直方向の移動量に対して作用します。
