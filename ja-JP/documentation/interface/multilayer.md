---
published: true
layout: default.ja
title: Type3 および SVG フォントの複数レイヤ編集
---
<!--
published: true
layout: default
title: Multi Layered Editing of Type3 and SVG fonts
-->


[table_of_contents]

<!--
When loading a type3 font (or an svg font organized in a similar fashion)
FontForge will retain information on each stroke and fill command. Each
command is placed in a separate layer and may be edited in isolation.
-->
Type3 フォント (または同様の方法で構成された SVG フォント) を読み込むとき、
FontForge は各ストロークおよび塗りつぶしコマンドに関する情報を保持します。
各コマンドは個別のレイヤーに配置され、個別に編集できます。

<!--
A new font may be converted to a multi-layered font by navigating to
Element->Font Info->Layers, then setting the splines option to **All layers
cubic** and the font type option to **Type3 Multi Layered Font**.
-->
新しいフォントは、
要素->フォント情報->レイヤ
に移動し、
スプラインオプションを **すべてのレイヤーを 3 次** に、
フォントタイプオプションを **Type3 マルチレイヤーフォント** に設定することにより、
マルチレイヤーフォントに変換できます。

![](/assets/img/windows-charview-multilayer.png)


<!--
### Multi Layered editing in the outline view
-->
### アウトラインビューでの複数レイヤ編集

<!--
In the image at left we have a glyph drawn by stroking two paths. One
layer (containing one of the paths) is currently selected and is drawn
in full. All its points are editable. The other layer is shown as a
dashed line.
-->
左の図には、2 本のパスのストロークによって描かれたグリフがあります。
1 個のレイヤ (パスの 1 本を含む) は現在選択されており、
実線で描画されています。
そこに含まれるすべての点は編集可能です。
他のレイヤは点線で描画されています。

<!--
The Layer palette looks a little different here. There is no hinting
information (hints are irrelevant in type3 fonts), instead there are two
named layers (background and grid) which behave pretty much as they
[normally](../charview/) do. They may be made active by clicking on
their names. They may be made invisible by turning off the check box
associated with them.
-->
レイヤパレットの見かけは、通常とは少し違っています。
ヒント情報はなく (Type3 フォントではヒントは使用不能です)、
その代りに、
[通常](../charview/)
とよく似たふるまいをする
2 つの名前つきレイヤ (背面とガイド) が存在します。
それらの名前をクリックすると使用可能になります。
横にあるチェックボックスをクリックすると、それらは見えなくなります。

<!--
Under these two are the layers that make up the glyph in the font. Each
layer is identified by a small picture of what that layer looks like
when rasterized. Clicking on the layer makes it editable.
-->
それら 2 つの下にあるのは、フォントに含まれるグリフを構成するレイヤです。
各レイヤは、そのレイヤがラスタライズされたときにどのように見えるかを表す小さな画像によって識別できます。
レイヤをクリックすると、それが編集可能になります。

<!--
The layers are ordered in the list as they will be drawn on the screen.
The topmost layer is drawn first, the bottommost is drawn last. Regions
drawn earlier will be overwritten by Regions drawn later.
-->
レイヤは、画面上に描画される順番でリストに並んでいます。
いちばん上のレイヤが最初に描画され、いちばん下のレイヤが最後となります。
最初に描画した領域は、後から描画した領域によって塗りつぶされます。

<!--
Double clicking on a layer brings up the [Layer Info dialog](#Layer).
-->
レイヤをダブルクリックすると
[レイヤ情報ダイアログ](#レイヤ情報ダイアログ)
が起動します。

<!--
Clicking with the right button brings up the layer menu which contains:
-->
右ボタンでクリックすると、以下の内容を含むレイヤメニューが起動します:

<!--
#### Layer Info...
-->
#### レイヤー情報...

<!--
Brings up the [Layer Info](#Layer) dialog on the current
layer (same as double clicking)
-->
現在のレイヤに関する
[レイヤ情報](#レイヤ情報ダイアログ)
ダイアログを起動します (ダブルクリックと同じです)。


<!--
#### New Layer...
-->
#### 新しいレイヤー...

<!--
Creates a new layer and brings up the [Layer
Info](#Layer) dialog to describe it. (the new layer will
appear at the bottom of the layer list and will be drawn last)
-->
新しいレイヤを作成し、それの情報を含む
[レイヤ情報](#レイヤ情報ダイアログ)
ダイアログを起動します。
(新しいレイヤはレイヤリストのいちばん下に現れ、最後に描画されます)。


<!--
#### Del Layer
-->
#### レイヤーを削除

<!--
Deletes the current layer (you may not delete the last layer in a glyph)
-->
現在のレイヤを削除します
(グリフにレイヤが 1 つしかないときは削除できません)。


<!--
#### First
-->
#### 最初

<!--
Make the current layer the first one to be drawn.
-->
現在のレイヤを最初に描画されるように移動します。


<!--
#### Earlier
-->
#### 前に

<!--
Make the current layer be drawn earlier. (swaps it with the layer above
it)
-->
現在のレイヤの描画順を繰り上げます
(1 つ前のレイヤと入れ換えます)。


<!--
#### Later
-->
#### 後に

<!--
Makes the current layer be drawn later. (swaps it with the layer below
it)
-->
現在のレイヤの描画順を繰り下げます
(1 つ前のレイヤと入れ換えます)。


<!--
#### Last
-->
#### 最後

<!--
Makes the current layer be drawn last.
-->
現在のレイヤを最後に描画されるように移動します。


<!--
### Images
-->
### 画像

<!--
Images are allowed in Type3 fonts. You can use the
[File-\>Import](../filemenu/#Import) command to load an image into any
of the foreground layers. If the image is a bitmap image and the layer
will be filled, then it will be output with an imagemask command in
PostScript (the bitmap will be drawn with the fill color), otherwise
(and always in SVG) the image will be drawn with the colors specified in
the image (Transparent images are not supported here).
-->
Type3 フォントでは画像を使用できます (SVG フォントではできません)。
[ファイル->取り込み](../filemenu/#Import)
コマンドで画像を好きな前面レイヤに読み込むことができます。
画像がビットマップ画像であり、それが置かれたレイヤで塗りつぶしモードの描画を行う場合、
その画像は imagemask コマンドによって出力され
(ビットマップは塗りつぶし色で描画されます)、
それ以外の場合は画像で指定されている色で描画されます
(ここでは透明画像はサポートされていません)。

<!--
FontForge will not skew, flip or rotate images.
-->
FontForge は画像の歪み、反転または回転変換を行いません。


<!--
### Clipping Path
-->
### クリッピングパス

<!--
Each layer in a Type 3 font may have its own clipping path. A clipping
path is a contour (or set of contours) and only things inside the
clipping path will be drawn.
-->
Type3 フォントの各レイヤーには、独自のクリッピングパスがあります。
クリッピングパスは輪郭 (または輪郭のセット) であり、
クリッピングパス内のものだけが描画されます。

![](/assets/img/windows-ClippedA.png) ![](/assets/img/windows-ClippedARaster.png)

<!--
The above example shows the letter "A" drawn with a clipping path that
looks like a star burst (the clipping path is drawn in blue). To the
right above is the result of rasterizing this image. The star is not
drawn itself, but only the region of the A within the star will be
drawn.
-->
上記の例は、スターバーストのように見えるクリッピングパスで描画された文字
"A" を示しています
(クリッピングパスは青で描画されます)。
右上は、この画像をラスタライズした結果です。
星自体は描かれませんが、星の中のAの領域だけが描かれます。

<!--
You can change the clipping path with the `Points->Make Clip Path`
command. The clipping path will be set to any selected contour(s) in the
image. If no contour is selected then there will be no clipping path.
-->
`ポイント->クリップパスの作成`
コマンドを使用して、クリッピングパスを変更できます。
クリッピングパスは、画像内の選択した輪郭に設定されます。
輪郭が選択されていない場合、クリッピングパスはありません。

![](/assets/img/windows-layerdlg.png)


<!--
### The Layer Info dialog
-->
### レイヤ情報ダイアログ

<!--
This dialog describes various attributes of the way the splines (or
images) in the current layer are drawn.
-->
このダイアログは、現在のレイヤでスプラインが描画される際のさまざまな属性を記述しています。

<!--
A layer may be either stroked or filled. Or both. Or neither (layers
containing only images need not be filled or stroked).
-->
レイヤは、ストロークとして線を引くか、内部を塗りつぶすか、
その両方、またはどちらも使用しないかのどれかが選択できます
(画像しか含まないレイヤはストロークも塗りつぶしも必要ありません)。

<!--
You may either specify a color to be used for stroking or filling the
splines in the layer, or you may specify that the color should be
inherited (in conventional fonts the color will be inherited so that the
font user can specify the font's color). If you do want to specify a
color, you can press the color wheel button to get a color picker
dialog, or enter a 6 hex-digit rgb value "\#rrggbb".
-->
レイヤ内のストロークや塗りつぶしに用いられる色のどちらも指定することができますし、
指定された色を引き継ぐこともできます
(通常のフォントでは色は引き継がれるので、ユーザは色を指定することができます)。
自分で色を指定したい場合、
16 進 6 桁の RGB 値 "\#rrggbb" を使用してください。

<!--
SVG fonts may include an opacity level (postscript type3 fonts may not).
0 is fully transparent, 1.0 is fully opaque, .5 is translucent. Again
this value may be inherited from the environment.
-->
SVG フォントは透明度レベルを含むことができます
(Type3 フォントはできません)。
0 は完全に透明で、
1.0 は完全に不透明、
0.5 が半透明です。
この値も環境から引き継ぐことができます。

<!--
A stroke has a width (which again may be inherited, but probably should
not be). Strokes are drawn using a circular pen. An elliptical pen may
be specified by giving a transformation matrix here.
-->
ストロークには幅が指定されています
(これも引き継ぐことができますが、これは多分行うべきではないでしょう)。
ストロークは円形のペンで描画されます。
ここで変換行列を指定することにより、
楕円形のペンを使用することもできます。

<!--
A line may be dashed. Dash patterns are specified as a list of numbers,
the first number in the list will draw a line segment at most that many
em-units, the next number will skip that many em-units, the third will
be drawn, and so on. After then entire list has been used, it will start
again at the begining. If the list has an odd number of elements, then
this time through the first entry indicates that many units should be
skipped. So "10" would mean a line which alternates being drawn every 10
units, while "20 10" would draw 20 units, skip 10, draw 20 and so on.
-->
線は破線にすることもできます。
破線パターンは数値のリストによって指定されます。
リスト内の最初の数値は、指定した em ユニット分の長さの線の素片を引くことを示し、
次の数値はその em ユニット分だけのすき間が空くことを表します。
3 番目は線が引かれ、以下同様に解釈されます。
リストの最後まで使われると、再び先頭に戻ります。
リストの要素が奇数個である場合、
2 回目には最初の要素が破線の隙間の大きさを表します。
ですから "10" という指定は、10 ユニットごとに入れ替わる破線を表し、
"20 10" は 20 ユニット描画し、10 ユニットの隙間が空き、20 ユニット描画し……と続く破線になります。

<!--
A stroke needs to know how to treat the ends of paths (`Line Cap`), and
how to join non-tangent path-segments (`Line Join`).
-->
ストロークでは、パスの終端 (`Line Cap`) と、
パスが折れ曲がっている所 (`Line Join`)
をどう描画するかを指定しなければなりません。

<!--
In an additional level of complexity a contour need not be filled (or
stroked) with a constant color, you can provide a repeating pattern, or
a gradual change from one color to another (a gradient).
-->
さらに複雑なレベルでは、一定の色で輪郭を塗りつぶす (またはストロークする) 必要はありません。
繰り返しパターンを提供したり、
ある色から別の色に徐々に変化させる (グラデーション) ことができます。


<!--
### Gradients
-->
### グラデーション

![](/assets/img/windows-GradientDlg.png)

<!--
FontForge supports two kinds of gradients, linear gradients and radial
gradients. In a linear gradient the color changes along a line (as in
the example at right, and below)
-->
FontForge は、線形グラデーションと放射状グラデーションの
2 種類のグラデーションをサポートしています。 
線形グラデーションでは、線に沿って色が変化します
(右および下の例のように)。

![](/assets/img/windows-LinearGradient.png)

<!--
You can specify the color at any point along the gradient line (as a
percentage of the distance along that line). The example at left only
specifies a color (white) at the start of the line, and a color (grey)
at the end, but intermediate values could be inserted, and a full range
of RGB colors may be used.
-->
グラデーションラインに沿った任意のポイントで色を指定できます
(そのラインに沿った距離の割合として)。
左の例では、行の先頭の色 (白) 末尾の色 (灰色) のみを指定していますが、
中間値を挿入でき、
RGB 色の全範囲を使用できます。

<!--
A Radial gradient specifies a center point and a final radius, the start
position (and color) is the center point and colors change in concentric
circles until the final radius (and final color) is attained.
-->
放射状グラデーションは中心点と最終半径を指定します。
開始位置 (および色) は中心点であり、
最終半径 (および最終色) に達するまで同心円で色が変化します。

![](/assets/img/windows-RadialGradient.png) ![](/assets/img/windows-RadialGradientDlg.png)


<!--
### Patterns
-->
### パターン

![](/assets/img/windows-TilePatternDlg.png)

<!--
A contour may also be filled or stroked with a tiled pattern. That is
a pattern is repeatedly layed down until it covers the entire area
to be filled.
-->
輪郭は、タイルパターンで塗りつぶしたり、線で描いたりすることもできます。
つまり、パターンは塗りつぶされる領域全体を覆うまで繰り返し配置されます。

![](/assets/img/windows-TiledPattern.png)

<!--
In the example above the tile ![](/assets/img/windows-Tile.png) has been scaled and
replicated. The example at right is a bit more complex. Not only is the
pattern replicated, but after that it is rotated through 45 degrees
-->
上記の例では、タイル
![](/assets/img/windows-Tile.png)
が拡大縮小および複製されています。
右の例はもう少し複雑です。
パターンが複製されるだけでなく、その後45度回転します

![](/assets/img/windows-TiledPattern45.png)

<!--
The pattern is defined in another glyph in the same font. By default the
bounding box of that glyph will be used to describe the pattern's extent
(You may change change that with [Element-\>Glyph Info-\>Tile
Size](../charinfo/#Tile+Size)). You may then scale it by specifying the
Width and Height fields. You may apply other transformations as
described in the dialog.
-->
パターンは、同じフォントの別のグリフで定義されています。
デフォルトでは、そのグリフの境界ボックスを使用してパターンの範囲を記述します
([要素->グリフ情報->タイルサイズ](../charinfo/#Tile+Size) で変更できます）。
次に、幅フィールドと高さフィールドを指定して、スケーリングできます。
ダイアログで説明されている他の変換を適用できます。

<!--
FontForge's rasterization leaves much to be desired. It does not support
full color (rounding everything to a shade of grey), and its stroking
algorithm is quite poor (it does not rasterize dashes), it does not
support the full complexity of radial gradients...
-->
FontForge のラスタライズには、多くの要望があります。
フルカラーをサポートしておらず (すべてが灰色の陰影に丸められます)、
ストロークアルゴリズムは非常に貧弱で (ダッシュをラスタライズしません)、
放射状グラデーションの完全な複雑さをサポートしていません…
