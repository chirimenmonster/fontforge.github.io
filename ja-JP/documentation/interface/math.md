---
published: true
layout: default.ja
title: 数学組版情報
---
<!--
published: true
layout: default
title: MATH typesetting information
-->


[table_of_contents]


<!--
In summer of 2007 (as I write) MicroSoft is proposing an extension to
OpenType which will allow fonts to contain information useful for
mathematical typesetting. The information all lives in a new
`'MATH' `table. FontForge now allows you to perform basic editing on
this table.
-->
2007年夏に (私が書いているように)、
MicroSoft は OpenType の拡張機能を提案しています。
これにより、フォントに数学的な組版に役立つ情報を含めることができます。
情報はすべて新しい
`MATH` テーブルに格納されます。
FontForge では、このテーブルで基本的な編集を実行できるようになりました。


<!--
### Constants
-->
### 定数 (Constants)

![](/assets/img/dialogs1-MATH-Constants.png)

<!--
The table is divided into several parts. One part
provides information on font-wide constants (And I do not mean "pi" or
2.71828... when I say constant here). These have to do with the size of
various elements of mathematical formulae with respect to one another,
and the spacing between them. So `FractionNumeratorGapMin` specifies the
minimum gap (white space) between the bottom of the numerator of a
fraction and the fraction bar (the rule between the numerator and
denominator.
-->
テーブルはいくつかの部分に分かれています。
1つの部分は、フォント全体の定数に関する情報を提供します
(ここで定数と言っているのは、"pi" や 2.71828.. という意味ではありません)。
これらは、数学の式に現れるさまざまな要素のサイズと、それらの間隔に関係しています。
したがって、`FractionNumeratorGapMin` は、
分子の下端と分数の線 (分子と分母の間の線) との間の最小間隔 (空白) を指定します。

<!--
I will not describe all of these constants here, there are about 60 of
them (and they take up 8 panes in the dialog). Most are fairly
self-explanatory, but some I do not understand myself. FontForge has
little popup messages plagerized from the specification which try to go
into more detail.
-->
ここではこれらすべての定数については説明しませんが、
それらはおおよそ 60 個あります
(ダイアログでは 8 つのタブを占有します)。
ほとんどはかなり自明ですが、一部は私自身も理解していません。
FontForge には、詳細を示すべく仕様から持ってきたポップアップメッセージはほとんどありません。

<!--
Some of these constants are stored as percentages of some other size
(ScriptPercentScaleDown is and means that sub-elements should be drawn
at a pointsize 73% of the current one -- I think). But most constants
are represented in em-units, and most of these may also have device
table adjustments specified. (At small pixel sizes (such as those used
for screen fonts) the rounding error introduced by converting from
em-units to pixels may be as large as the movement itself. A device
table allows you to specify that (in the case of AxisHeight above) when
the font is rasterized to be 10 pixels high the Axis should be moved up
by one pixel).
-->
これらの定数の一部は、他のサイズに対する比率 (百分率) として格納されます
(ScriptPercentScaleDown は、サブ要素が現在の 73% のポイントサイズで描画されることを意味します)。
ただし、ほとんどの定数は em 単位で表され、
これらのほとんどにはデバイステーブルの調整が指定されている場合もあります。
(スクリーンフォントに使用されるような) 小さなピクセルサイズでは、
em 単位からピクセルへの変換によって生じる丸め誤差は、
移動量そのものと同じくらい大きくなる可能性があります。
デバイステーブルを使用して、それを指定できます
(上記の AxisHeight の場合)
フォントの高さが 10 ピクセルになるようにラスタライズすると、Axis は 1 ピクセル上に移動します)。

<!--
FontForge is not always configured to support device tables, so if these
columns are missing you just need to reconfigure and rebuild it.
-->
FontForge は常にデバイステーブルをサポートするように構成されているわけではないため、
これらの列が欠落している場合は、再構成して再構築する必要があります。


<!--
### Glyph specific information
-->
### グリフ固有の情報 (Glyph specific information)

<!--
In addition to the constants there are various bits of data that
potentially pertain to each glyph.
-->
定数に加えて、潜在的に各グリフに関係するさまざまなビットデータがあります。


<!--
#### Extended Shapes
-->
#### 拡張シェイプ (Extended Shapes)

![](/assets/img/dialogs1-MATH-Exten.png)

<!--
The simplest of these per-glyph data is a flag which
indicates whether a glyph is an extended shape. Extended shapes tend to
be taller than normal characters and need to have superscripts raised
higher than normal shapes.
-->
これらのグリフごとのデータの最も単純なものは、グリフが拡張シェイプあるかどうかを示すフラグです。 拡張シェイプは、通常の文字よりも高くなる傾向があり、上付き文字を通常のシェイプよりも高くする必要があります。

<!--
This sub-table consists of a list of glyph names and an indication of
whether this glyph is an extended shape (you may add additional glyphs
at the bottom of the list, order is irrelevant here).
-->
このサブテーブルは、グリフ名のリストと、このグリフが拡張シェイプであるかどうかの表示で構成されます
(リストの下部にグリフを追加でき、順序はここでは関係ありません)。


<!--
#### Italic Correction
-->
#### イタリック補正 (Italic Correction)

![](/assets/img/dialogs1-MATH-Italic.png)

<!--
The concept of "Italic correction" will be familiar
to users of TeX. Basically when an upright glyph is placed after an
italic (or oblique) glyph the slanted glyph may overlap the upright one
slightly (since it is designed to fit next to another slanted glyph).
The italic correction is a small addition to the glyph's advance width
applied when followed by an upright glyph (and in some other cases too).
-->
"イタリック補正" の概念は、TeX のユーザーにはおなじみです。
基本的に、イタリック体 (または斜体) グリフの後に直立したグリフを配置すると、
傾斜したグリフが直立したグリフとわずかに重なる場合があります
(次にくる別の傾斜したグリフに収まるようにデザインされているため)。
イタリック補正は、直立したグリフが続くときに (ときには他の場合にも) 適用されるグリフの送り幅への小さな追加です。

<!--
If you allow the mouse cursor to hover over an entry a small window will
pop up showing the glyph, the normal advance width (as a dotted line),
and the corrected advance width.
-->
マウスカーソルをエントリの上に置くと、
グリフ、通常の送り幅 (点線)、
および修正された送り幅を示す小さなウィンドウがポップアップ表示されます。

<!--
Here again you are allowed to specify a device table to adjust the
correction.
-->
ここでも、デバイステーブルを指定して修正を調整できます。


<!--
#### Top Accent Attachment
-->
#### トップアクセントの添付 (Top Accent Attachment)

![](/assets/img/dialogs1-MATH-TopAccent.png)

<!--
When positioning an accent above a glyph
Mathmatical typesetting follows complex rules to determine how high
about the glyph it should go. The standard Mark To Base GPOS lookup is
inappropriate here.
-->
グリフの上にアクセントを配置する場合、
数学組版は複雑なルールに従って、グリフの高さを決定します。
ここでは、標準の Mark To Base GPOS 照合テーブル適当ではありません。

<!--
Instead all that needs to be specified is the horizontal position at
which the glyph and accent should attach.
-->
代わりに、指定する必要があるのは、グリフとアクセントを付加する水平位置だけです。

<!--
This table can be used to specify that position in both the base glyph
and the accent. In the example at right I show one of each. The vertical
line indicates the attachment position in each, and the glyphs will be
adjusted so the two lines match up.
-->
このテーブルを使用して、基本グリフとアクセントの両方でその位置を指定できます。
右の例では、それぞれの 1 つを示しています。
垂直線はそれぞれの添付位置を示し、グリフは 2 本の線が一致するように調整されます。

<!--
Again a device table may be specified to control positioning at small
pixel sizes.
-->
この場合も、小さなピクセルサイズでの位置決めを制御するためにデバイステーブルを指定できます。


<!--
### Math Kerning
-->
### 数学カーニング (Math Kerning)

![](/assets/img/dialogs1-MATH-MathKern.png)

<!--
This subtable is used when positioning subscripts
and superscripts at various corners of a glyph. A glyph may have a
superscript attached to either its top left or top right edge (limits
for integral signs use the same mechanism, and probably other concepts
will as well), and a subscript at the bottom left or right.
-->
このサブテーブルは、グリフのさまざまなコーナーに下付き文字と上付き文字を配置するときに使用されます。
グリフには、左上または右上の端に上付き文字が付いている場合があり
(整数記号の制限は同じメカニズムを使用し、おそらく他の概念も同様です)、
下付き文字が左下または右にあります。

<!--
In a slanted glyph it is clear that the horizontal positioning of a
subscript should be different from the horizontal positioning of a
superscript -- A problem similar to the italic correction. But this is
more complex as the positioning point may depend on the size of the
sub/superscript and exactly where it attaches vertically.
-->
傾斜したグリフでは、下付き文字の水平方向の位置が上付き文字の水平方向の位置と異なる必要があることは明らかです。
これはイタリック体の修正と同様の問題です。
ただし、これは、位置決めポイントが下付き/上付き文字のサイズと正確に垂直に接続する場所に依存する可能性があるため、より複雑です。

<!--
This subtable allows you to specify a list of glyph kerning/height pairs
for each corner of the glyph. Click on the word "Change" above to get a
new dialog. These data may be specified textually:
-->
このサブテーブルを使用すると、グリフの各コーナーに対するカーニング/高さのペアのリストを指定できます。
上記の "変更" をクリックして、新しいダイアログを取得します。
これらのデータはテキストで指定できます：

 ![](/assets/img/dialogs1-MATH-MathKernText.png) 

<!--
At any given height a kerning value may be specified. This value is
relative to the default position of the subscript (and I'm not entirely
sure what that is). As always device table adjustments may be
specified.
-->
任意の高さでカーニング値を指定できます。
この値は、添え字のデフォルトの位置に相対的です
(そして、それが何であるかは完全にはわかりません)。
常にデバイステーブルの調整を指定できます。

<!--
FontForge also allows you to specify these data graphically
-->
FontForge では、これらのデータをグラフィカルに指定することもできます

![](/assets/img/dialogs1-MATH-MathKernGraph.png)

<!--
FontForge displays bottom right attachments relative to the advance
width line of the glyph  
FontForge displays top right attachments relative to the advance width
plus the italic correction.  
FontForge displays bottom left attachments relative to the origin of
the glyph.  
FontForge displays top left attachments relative to the italic
correction.
-->
FontForge は、グリフの有効幅の線に対して右下の添付ファイルを表示します。<br>
FontForge は、有効幅に加えて斜体の修正に関連する右上の添付ファイルを表示します。<br>
FontForge は、グリフの原点を基準にして左下の添付ファイルを表示します。<br>
FontForge は、イタリック修正に関連する左上の添付ファイルを表示します。

<!--
Note: If you are familiar with the MATH table spec you will recall that
the last kern value does not have a height attached to it. FontForge
tries to guess a reasonable value for the unspecified height (because it
makes editing easier if I let the user move a point around), but have no
fears, that guessed at value will never show up in the MATH table
itself.
-->
注： MATH テーブルの仕様に精通しているのであれば、
最後のカーニング値には高さが付加されていないことを思い出してください。
FontForge は、指定されていない高さに対しては妥当な値を推測しようとします
(ユーザーにポイントを移動させると編集が容易になるため) が、恐れることはありません。
推測された値は MATH テーブル自体には表示されません。


#### 垂直および水平のグリフバリアント (Vertical and Horizontal Glyph Variants)

![](/assets/img/dialogs1-MATH-VertVariants.png)

<!--
Some glyphs, like parentheses and brackets
need to be drawn in many sizes depending on the size of the formula they
are enclosing. One possibility is just to draw them at a larger
pointsize, but that is non-optimal because then the glyph will be
symetrically scaled and so much bolder than it should be. Another
solution is to design several variants of these glyphs at steadily
increasing sizes. A third solution (which we will come to in the next
section) is to design the glyph in sections so that it can be composed
at any size.
-->
丸括弧や角括弧などの一部のグリフは、
それらが囲む式のサイズに応じて多くのサイズで描画する必要があります。
考えられる 1 つの方法は、より大きなポイントサイズとして描画することですが、
グリフが縦横ともに拡大され、本来あるべきよりもすっと太くなってしまうので、適当ではありません。
別の解決方法は、これらのグリフのいくつかのバリエーションを実際にサイズを大きいものとしてデザインすることです。
3番目の解決方法 (次のセクションで説明します) は、任意のサイズで生成できるように分割した状態でグリフをデザインすることです。

<!--
In this sub-table you may specify a normal sized glyph (here
"leftparen") and then a list of variants in increasing sizes.
-->
このサブテーブルでは、
通常サイズのグリフ　(ここでは "leftparen") を指定してから、
サイズが大きくなるバリアントのリストを指定できます。

<!--
Glyphs may be grow along either the vertical axis (as here) or the
horizontal axis.
-->
グリフは、垂直軸 (この例のように) または水平軸に沿って成長する場合があります。


#### 垂直および水平のグリフ構造 (Vertical and Horizontal Glyph Construction)

![](/assets/img/dialogs1-MATH-GlyphConstruction.png)

<!--
As I said above, it is also possible to build a glyph out of bits of 
other glyphs.
-->
上で述べたように、他のグリフのビットからグリフを構築することもできます。

<!--
Each such constructed glyph has (potentially) and Italic Correction (and
device table adjustment). This value should be independent of the size
of the glyph.
-->
そのように構築された各グリフには、
(可能性として) イタリック補正 (およびデバイステーブル調整) があります。
この値は、グリフのサイズに依存しません。

<!--
The components are rather difficult to specify in this display, but if
you scroll the dialog to the far right you will find a little
rectanglular box, and clicking on this will produce the dialog below. 
-->
この表示でコンポーネントを指定するのはかなり困難ですが、
ダイアログを右端までスクロールすると、
小さな長方形のボックスが表示され、
これをクリックすると下のダイアログが生成されます。

![](/assets/img/dialogs1-MATH-GlyphConstructionDlg.png) 

<!--
Every component is either an "Extender" component -- which means it may be 
stuck in the composed glyph as often as needed (or not at all) to make the 
glyph be as big as needed.
-->
すべてのコンポーネントは "拡張" コンポーネントのいずれかです
-- つまり、グリフを必要なだけ大きくするために、
必要に応じて何度でも (またはまったく使用せずに) 合成グリフに固定することができます。

![](/assets/img/dialogs1-MATH-GlyphConstructed.png)

<!--
Component glyphs may overlap one another. You may specify a maximum
overlap for each end of each component. You may also specify how much
the component adds to the total height (or width) of the composed glyph.
-->
コンポーネントのグリフは互いに重なり合う場合があります。
各コンポーネントの各端に最大オーバーラップを指定できます。
また、構成されたグリフの合計の高さ (または幅) にコンポーネントが追加する量を指定することもできます。

<!--
Finally there is a font-wide constant (in the Connectors pane of the
Constants section) called MinConnectorOverlap which specifies that
glyphs must overlap by at least this amount.
-->
最後に、MinConnectorOverlap と呼ばれるフォント全体の定数
(<span class="command">定数</span>
セクションの
<span class="command">コネクタ</span>
タブ) があり、
グリフが少なくともこの量だけ重なり合う必要があることを指定します。

<!--
The per-glyph information may also be specified from the [Glyph
Information dialog.](../charinfo/)
-->
グリフごとの情報は、
[グリフ情報](../charinfo/)
ダイアログから指定することもできます。

<!--
I wish to thank Sergey Malkin at MicroSoft who provided me with a copy
of the spec, and Apostolos Syropoulos who provided me with a test font
containing a 'MATH' table.
-->
MicroSoft の仕様書のコピーを提供してくれた Sergey Malkin と、
'MATH' テーブルを含むテストフォントを提供してくれた Apostolos Syropoulos に感謝します。
