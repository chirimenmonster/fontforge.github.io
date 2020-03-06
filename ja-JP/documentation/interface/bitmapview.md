---
published: true
layout: default.ja
title: ビットマップグリフビュー
---
<!--
published: true
layout: default
title: Bitmap Character View
-->


[table_of_contents]


![](/assets/img/windows-BitmapReference.png)

<!--
A bitmap glyph composed of two bitmap references
-->
2つのビットマップ参照で構成されるビットマップグリフ

![](/assets/img/windows-BitmapView.png)

<!--
The bitmap view is vaguely similar to the [outline view](../charview/).
It is also designed for editing glyph shapes, but here bitmap glyph
shapes.
-->
ビットマップビューは少しだけ
[アウトラインビュー](../charview/)
に似ています。
これもグリフの形を編集するように設計されていますが、
ここではビットマップグリフの形が対象です。

<!--
At the top of the view is a small region showing an unmagnified view of
the glyph, to the right of that are two information displays, the first
shows the current location of the mouse pointer, and the second shows
(if the mouse button has been depressed and not released yet) the offset
from the place where the mouse was pressed to the current pointer
location. The coordinate system here is in pixels with the origin at the
glyph's origin. Next to this is a button (here truncated) that allows
you to recalculate the bitmap (rasterize the outline and place the
result in the window for editing).
-->
ビューの上部には、グリフを拡大しないで表示した領域があり、
その右には 2 個の情報表示欄があります。
最初の情報表示欄はマウスポインタの現在位置を示し、
2 番目は
(マウスボタンが現在押したままになっているならば)
マウスが押された位置から現在位置までのオフセットを表示します。
この座標系はピクセルを単位とし、
原点はグリフの原点に置かれています。
その隣にあるボタン (図では一部隠れています) を押すと、
ビットマップの再計算を行います
(アウトラインをラスタライズし、結果を編集用にこのウィンドウに表示します)。

<!--
Underneath is the main display, showing the bits in the image, the
outline of the glyph and a grid.
-->
下にあるのはメイン画面で、画像内のビット、文字のアウトラインとグリッドを表示しています。

<!--
As in the outline view you may choose to make the palettes free floating
windows by unchecking View-\>Palettes-\>Dock Palettes.
-->
アウトラインビューと同様に、
<span class="command">表示->パレット->パレットを連結表示</span>
でウィンドウ内にパレットを埋め込むかどうかを選べます。


<!--
### Layers
-->
### レイヤ

![](/assets/img/windows-bvlayers.png)

<!--
There are three layers to the bitmap view, the bitmap itself, the
outline glyph and the grid lines. You are always editing in the bitmap
layer so there is no control over what layer is editable, just which
ones are visible.
-->
ビットマップビューには 3 つのレイヤがあります。
ビットマップそれ自身、アウトライングリフとグリッドの線です。
編集はつねにビットマップレイヤで行うので、
どのレイヤを編集するかを選択することはできず、
どれを表示するかだけが選択できます。


<!--
### Tools
-->
### ツール

![](/assets/img/windows-bvtools.png)

<!--
There are only six tools on the bitmap palette (there are some others
available by right clicking in the view, this generates a popup menu.
-->
ビットマップビューには 6 つしかツールがありません
(ビューを右クリックすることにより、
ポップアップメニューを起動することができ、
これによりいくつかの追加の機能を使うことができます)。

<!--
The pointer tool allows you to select a region of the screen, and move
it around or copy it (a copy when nothing is selected copies the entire
bitmap). The arrow keys will also move the selection around. In a bitmap
only font the pointer tool can change the advance width.
-->
ポインタツールを使うと、スクリーン上の範囲を選択して、それを移動するかコピーすることができます
(何も選択せずにコピーを行った場合、ビットマップ全体をコピーします)。
選択範囲の移動には矢印キーを使用することもできます。
ビットマップのみのフォントでは、ポインタツールは送り幅の変更に使うことができます。

<!--
The if you click with the magnifying tool the view is magnified,
centered around the point at which you clicked. If you hold down the
[Meta (or Alt or CapsLock)](../charview/#alt-meta-capslock) key during
the click then the view will be minified.
-->
拡大ツールでクリックすると、クリックした点を中心にビューが拡大されます。
[Meta (または Alt か CapsLock)](../charview/#alt-meta-capslock)
キーを押したままクリックすると、ビューは縮小されます。

<!--
The pencil tool allows you to set or clear bits. If you depress the
mouse button then the pencil will toggle the bit under the cursor, if
you then drag it over other bits they will be set if the first bit was
set, and cleared if the first was cleared.
-->
鉛筆ツールはビットを塗りつぶすか消すかすることができます。
マウスボタンを押すと、鉛筆ツールはカーソル位置にあるビットを反転します。
そのままドラッグすると、その他のビットは最初のビットが塗りつぶされた場合は塗りつぶされ、
消された場合は消されます。

<!--
The line tool (the pencil with the line beside it) will draw straight
lines. It behaves like the pencil tool on whether it sets or clears a
line. The Shift key does not constrain this window.
-->
直線ツール (横に線が引かれている鉛筆) は直線を引きます。
ビットを塗りつぶすか消すかに関しては、これも鉛筆ツールと同様にふるまいます。
このウィンドウでは、Shift キーを押しても移動方向は制限されません。

<!--
The four-arrow tool moves the entire bitmap.
-->
四方矢印ツールはビットマップ全体を移動します。

<!--
The hand scrolls the screen.
-->
手のひらツールは画面をスクロールします。

<!--
#### Additional tools from the popup menu.
-->
#### ポップアップウィンドウから使える追加ツール

<!--
-   Draw an open rectangle
-   Draw a filled rectangle
-   Draw an open ellipse
-   Draw a filled ellipse
-   Rotate the bitmap 90° Counter Clockwise.
-   Rotate it 90° Clockwise.
-   Rotate it 180°.
-   Flip it horizontally
-   Flip it vertically.
-   Set Width
     This is only available if there is no outline font (ie. if you
    opened a bdf file directly).
     It sets the width (glyph advance) of the bitmap.
-->
-   枠だけの長方形を描く
-   塗りつぶされた長方形を描く
-   枠だけの楕円を描く
-   塗りつぶされた楕円を描く
-   反時計回りに 90°回転する
-   時計回りに 90°回転する
-   180°回転する
-   水平方向に反転する
-   垂直方向に反転する
-   幅を設定する  
     アウトラインフォントが存在しないとき (例. BDF ファイルを直接開いた場合) のみ利用可能。
    ビットマップの幅 (グリフの送り幅) を設定する。

<!--
### Anti-Aliased Glyphs
-->
### アンチエイリアス表示のグリフ

![](/assets/img/windows-greymapedit.png)

<!--
This window may also be used to edit anti-aliased
glyphs (glyphs which are represented by shades of grey rather than by
black and white. In the information area there is a little rectangle
which shows the current color that will be used by the pencil (line,
rectangle, etc.) tool.
-->
このウィンドウは、アンチエイリアス表示のグリフ
(白黒 2 色でなく、灰色の階調で表現されたグリフ)
を編集するのにも使うことができます。
情報表示領域に、
鉛筆 (直線・長方形等)
ツールで使用される色が小さな長方形で表示されています。

<!--
The behavior of the drawing tools is slightly different here. In a
bitmap glyph the color used for drawing is the opposite of whatever
color is currently under the cursor, but that doesn't work in an
environment with more than two colors. So you must select what color you
are going to draw with manually.
-->
描画用ツール群のふるまいは、ここではわずかに異なります。
ビットマップグリフでは、現在カーソル位置の色が何であってもそれを反転しますが、
2 色よりも多い環境ではこの方法は使えません。
そのため、どの色で描画するかを手動で選ばなければなりません。

<!--
There are two ways to select the drawing color:
-->
描画色を選ぶには 2 つの方法があります:

<!--
-   With the pencil tool selected, hold down the Alt (Meta) key. The
    cursor changes to an eyedropper. Position the cursor over a pixel
    with the right color and click the mouse.
-   Use the [Shades](#Shades) palette.
-->
-   鉛筆ツールを選んで Alt (Meta) キーを押します。
    カーソルがスポイトに変わります。
    カーソルを描画したい色に合わせてマウスをクリックします。
-   [階調](#階調) パレットを使います。


<!--
### Shades
-->
### 階調

![](/assets/img/windows-Shades.png)

<!--
Shades of grey available with 8 bits/pixel
-->
8 ビット/ピクセルで利用可能な階調

![](/assets/img/windows-Shades4.png)

<!--
Shades of grey available with 4 bits/pixel
-->
4 ビット/ピクセルで利用可能な階調

![](/assets/img/windows-Shades2.png)

<!--
Shades of grey available with 2 bits/pixel
-->
2 ビット/ピクセルで利用可能な階調

<!--
The shades palette is only visible in an anti-aliased glyph. The palette
displays all the possible shades of grey available to this glyph. Glyphs
with more bits per pixel will have more shades of grey.
-->
階調パレットはアンチエイリアスグリフだけで使用可能です。
パレットは、このグリフで利用可能な灰色の階調を全て表示します。
1 ピクセルあたりのビット数が多いほど、多くの階調の灰色を使用できます。

<!--
The currently selected drawing color is outlined in green. To select a
new color, move the cursor to the desired color and click the mouse.
-->
現在選択されている描画色は緑の枠線で囲まれています。
新しい色を選択するには、目的の色にカーソルを合わせてマウスをクリックします。

<!--
As the cursor moves over the bitmap in the bitmap view, the color under
the cursor will be outlined in white.
-->
カーソルがビットマップビュー内のビットマップ上を移動すると、
カーソルの下にある色は白い枠線で囲み表示されます。
