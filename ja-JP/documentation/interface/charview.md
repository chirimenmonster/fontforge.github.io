---
published: true
layout: default.ja
title: アウトライングリフビュー
---
<!---
published: true
layout: default
title: Outline Glyph View
--->


[table_of_contents]


![](/assets/img/windows-charview2.png)

<!--
The outline glyph view is the window in which most editing happens.
-->
アウトライングリフビューは、編集作業のほとんどが行われるウィンドウです。

<!--
At the top of the window, underneath the menu bar is an information
line. The first item is the location of the mouse pointer (in the
internal coordinate system of the glyph). If there is a single selected
point then the next item gives its location, and the next three are,
respectively, the offsets from the selected point to the current
location, the distance from the selected point, and the angle from the
horizontal (measured counter-clockwise). Then we have the current scale
factor, and the layer which is active. Finally (in the debugging view)
is an indication of whether the instruction pointer is in the glyph
program, the 'prep' program of the 'fpgm'.
-->
ウィンドウの上部、メニューバーの直下にあるのは情報表示欄です。
最初の項目は (グリフの内部座標系に換算した) マウスポインタの位置です。
選択された点が 1 個だけの場合、
2 番目の項目にその位置が表示され、
その次の 3 項目は左から順に、選択された点から現在位置までのオフセット、
選択された点からの距離および水平方向から (反時計周りに計って) 見た角度です。
その後ろに現在の拡大率と、どのレイヤがアクティブになっているかの表示が来ます。
最後に (デバッグ用ビューでは) 命令ポインタが
'fpgm' の 'prep' プログラムであるグリフプログラムのどこにあるかを示しています。

<!--
Underneath the information is a ruler showing the current pointer
location as a red line. There's a similar ruler on the left side.
-->
情報欄の下にあるのはものさしで、現在のポインタ位置がどこにあるかをその上に赤い線で示しています。
左側にも同じようなものさしがあります。

<!--
Underneath that is the glyph itself. On the left edge of the screen is a
grey line indicating the x=0 line, further right is a black line showing
where the glyph's width is currently set. There are also grey lines
showing the ascent, descent and baseline.
-->
その下にはグリフそのものがあります。
スクリーンの左端には x=0 の線を示す灰色の線があり、
そのずっと右には、現在設定されているグリフの幅の位置に黒い線が引かれています。
アセント (フォントの高さ)、ディセント (深さ) とベースラインも灰色の線で示されています。

<!--
Background images and background splines are drawn in grey. Grid lines
are also drawn in grey. Vertical hinting regions are drawn in light
blue, Horizontal hints are drawn in light green. If any hints overlap
the boundaries are drawn in cyan.
-->
背景画像と背景スプラインは灰色で描画されています。
グリッド線もまた灰色で描画されています。
垂直ヒント領域は水色で、水平ヒントは薄緑色で描画されています。
ヒントが重なり合っているときは、境界線は藍色で描画されています。

<!--
The points of the glyph are of three types, corner points drawn as
filled squares, curve points drawn as filled circles and tangent points
drawn as filled triangles. If a point is selected then it will be drawn
as an outlined square, circle or triangle and its control points are
drawn as little magenta or dull-cyan xs at the end of a similarly
colored line. (in a curved point the control points will be collinear).
(the "Next" control point will be drawn dull cyan, and the Prev point
will be magenta).
-->
グリフを構成する点には 3 つのタイプがあります。
角の点は塗りつぶされた正方形で、
曲線上の点は塗りつぶされた円で、
そして (曲線と直線の) 接点は塗りつぶされた三角形で表されます。
点が選択されたときには白抜きの正方形・円・三角形になり、
隣接する制御点がマゼンタと鈍いシアンの×印として、
同じ色の直線の端に表示されます
(曲線上の点の場合、制御点はちょうど反対方向になります)。
(「次」の制御点が鈍いシアンで、前の制御点がマゼンタになります)。

![A quadratic glyph](/assets/img/windows-charview-quadratic.png)

<!--
In a TrueType font, an on-curve point can be implied between two control
points. FontForge will draw these with an open circle.
-->
TrueType フォントでは、曲線上の点が 2 個の制御点の中点にあるときは、
暗黙の位置指定を行うことができます。
FontForge はそれらの点を開いた円として描画します。

<!--
The initial point in a contour will be drawn in green, and beside it
will be a tiny arrow pointing in the direction of the contour.
-->
輪郭の最初の点は緑色で描かれ、
そのそばに輪郭の進行方向を示す小さな矢印が表示されます。

![Showing extrema](/assets/img/windows-extrema-poi.png)

<!--
Sometimes it is important to know which points are at the extrema of
splines (postscript likes for there to be points at the extrema of all
splines), if this is important to you set the "Mark Extrema" flag in the
View menu. After that points at extrema will show up as dull purple. And
internal extrema will also be marked.
-->
スプラインの (水平・垂直に) 極大な点がどこかを知ることが重要であることがときどきあります。
(PostScript では全てのスプラインに、極大値となる場所に点が置かれていることが望ましいとしています)。
これが必要な場合は、
表示
メニューで 極大点を表示 フラグをオンにしてください。
これを行うと、極値にあたる点が鈍い紫色で表示されます。
また、中間にある極大値も同時に表示されます。

<!--
There are also two palettes, one, a layer palette, allowing you to
control [which layers are visible](#Layers), and one, a tool palette,
from which you [may pick editing tools](#Tools). Normally these are 
docked in the window, but you may choose to make them free floating
windows by unchecking View-\>Palettes-\>Dock Palettes.
-->
それに加えて、パレットが 2 個あります。
片方は [どのレイヤが表示されるか](#Layers) を制御することができるレイヤパレットで、
もう片方は [編集ツールを選択することができる](#Tools) ツールパレットです。
これらは通常はそれぞれ自由に動かすことができますが、
表示-\>パレット->パレットを連結表示
によって、ウィンドウ内に埋め込まれるように変更できます。

<!--
You select an editing tool by clicking on the appropriate button on the
tools palette, or you may depress the right mouse button and select a
tool from a popup menu (you may also change layers and do a few other
things with this menu). There are four different tools bindings
available to you (this may be a complication with no utility). The left
mouse button has a tool bound to it, and this tool will be displayed
when the program is idle. If you hold down the control key, another tool
is available, by default this is a pointer but if you click on the tools
palette with the control key down you can select something else. If you
depress the middle mouse button you get a third tool (by default a
magnifying glass), and the control key and middle button give you the
fourth (a ruler).
-->
編集ツールは、ツールパレットの対応するボタンを押して選択することも可能ですし、
右のマウスボタンを押してポップアップメニューからツールを選択することもできます
(こちらのメニューでは、レイヤー変更やその他二、三の操作が可能です)。
同時に、4 種類の異なる操作のツールを結びつけ可能です
(これは面倒なだけで役に立たないかもしれません)。
左マウスボタンにはツール操作が結びつけられていて、
プログラムのアイドル時にはこのツールが表示されるでしょう。
Control キーを押したときには、別のツールが使用可能で、
デフォルトではポインタツールとなっていますが、Control キーを押しながらツールパレットをクリックすると、
別の物を選ぶことができます。
マウスの中ボタンを押したときには 3 番目のツールを使用できます (デフォルトでは虫めがねです)。
Control キーを押しながら中ボタンを押すと 4 番目を (ものさしから) 切替えることができます。

<!--
If the mouse pointer is close to a point (within a few pixels) when you
depress the mouse, then the effective location of the press will be the
location of the point.
-->
マウスポインタの近く (約 2, 3 ピクセル以内) に点があるときにマウスボタンを押すと、その点がある位置でマウスを押したのと同じ効果になります。

<!--
If you drag a glyph from the font view and drop it into a glyph view
then FontForge will drop a reference to the dragged glyph into the view.
-->
フォントビューからグリフをドラッグしてグリフビューに置くと、
FontForge はその文字への参照をビュー上に配置します。

<!--
Warning: **If your glyph has truetype instructions then editing it may
cause those instructions to behave very oddly. If your glyph has anchor
points which depend on truetype point matching then editing the glyph
may disconnect the points. If your glyph is used as a reference in
another glyph that positions references by point matching then editing
this glyph may reposition those references.**
-->
警告: 
**編集中のグリフに TrueType 命令が含まれている場合、
グリフ編集時にそれらの命令が非常に奇妙なふるまいをもたらすことがあります。
TrueType の点の照合に依存するアンカーポイントがグリフに含まれている場合、
そのグリフを編集することにより点の関連が途切れる可能性があります。
編集中のグリフが、
点の照合により参照の位置指定を行う他のグリフへの参照として使用されている場合、
そのグリフを編集するとそれらの参照の位置が変更される可能性があります。**

<!--
### Layers
-->
### レイヤ

![](/assets/img/windows-layers.png)

<!--
There are several drawing layers in the outline view.
Each layer has an "eye box" (indicating whether it is visible or not),
curve type ("C" for cubic, "Q"for quadratic, " " for Guide layer, which
is always cubic), mode ("\#" for Guide layer, "B" for background layers,
"F" for foreground layers) and a name.
-->
アウトラインビューには幾つかのレイヤがあり、
それらのうちの 3 つが編集可能です。
各レイヤには (それを表示するかしないかの) チェックボックスがあり、
編集可能なレイヤには、
(そのレイヤが表示可能であるかを示す) ラジオボタン がついています。

<!--
The first layer is a set of guide lines/splines. These are common to all
glyphs in the font. A few lines are provided for you (the x=0 line, the
ascent, descent and baseline). Other handy lines might be the x-height
of the font, the cap-height, ascender-height, descender-height, ... When
you are working in any of the other layers, points will snap to splines
in this layer (making it easy to force a consistent x-height for
example).
-->
最初の のレイヤはガイドライン/スプラインの集まりです。
これはフォント内の全てのグリフで共通に使用されます。
最初から表示されているのは少数しかありません
(x=0 の線、アセント、ディセントとベースラインです)。
その他の助けになる線はフォントの x ハイト、キャップハイト、アセンダハイト、ディセンダハイト等があります。
その他のレイヤのどれかで作業をしているとき、
ポインタはこのレイヤに置かれた線に吸着します
(例えば、x ハイトを一定値に強制的に揃えたいときなどに役立ちます)。

<!--
Next are the background layers, these contain background images and
splines. These do not go into the font, but may be helpful to you in
tracing the outline of your glyph. It is possible to paste an image into
the background if you have an image manipulation program that supports
selection by mime type (the kde family of applications does this,
perhaps others), then FontForge will be able to read images in either
"image/png" or "image/bmp", otherwise you may import background image
files.
-->
次はは背面レイヤで、
ここには背景画像とスプラインが含まれます。
これらはフォントには書き出されませんが、
グリフのアウトラインをトレースする作業の助けになります。
画像を背面に貼りつけることも可能です。
MIME タイプによる選択が可能な画像操作プログラムがある場合、
画像を背面に貼りつけることもできます
(KDE ファミリーのアプリケーションはこれを行いますし、多分他にもあるでしょう)。
このとき、FontForge は
"image/png" または "image/bmp" のどちらかで画像を読み出すか、
そうでなければ背景画像をインポートすることができます。

<!--
When debugging truetype (`Hints->Debug)`, or showing gritfit outlines
(`[View->Show Grid Fit](../viewmenu/#Show+Grid+Fit)`) the visibility of
the gridfit outlines can be controlled by the background layer's
visibility.
-->
TrueType のデバッグ
( ヒント-\>デバッグ )
や、
アウトラインのグリッド合わせ
( [表示->グリッド合わせを表示](../viewmenu/#Show+Grid+Fit) )
を行っている時、
グリッド合わせを行ったアウトラインの表示の有無はレイヤの表示の有無によって切り替えることができます。

<!--
The last is the foreground layer, this contains the splines that
actually make up the glyph that will be placed into the font.
-->
最後が前面レイヤで、
ここにはグリフを実際に構成し、フォントに出力されるスプラインが含まれます。

One can actually have multiple foreground and background layers. They
can be created and deleted with "+" and "-" buttons. FontForge, won't
delete last layer of its type, though. And care must be taken when
generating a font to have the right foreground layer selected, if
multiple are present.

Layer curve type and visibility can be toggled freely with left mouse
button. Making the layer cubic or quadratic is a little trickier, as
it's done with right mouse button: a pop-up menu will appear, allowing
for some additional operations, like moving contents between layers.


<!--
### Tools
-->
### ツール

![](/assets/img/windows-tools.png)

<!--
There are 19 different editing tools, a mode button which
alters the behavior of 5 of them, and two others (rectangle/ellipse and
polygon/star) which come in two forms.
-->
編集ツールは 19 種類あり、
編集ツールのうちの 1 つは 5 種の挙動を変更するモードボタンで、
編集ツールのうちの 2 つ (長方形/楕円と多角形/星形) にはそれぞれ 2 種類の形状があります。

<!--
At the bottom of the palette is a list of the current bindings of the
mouse buttons. Here mouse button 1 is bound to the pointer tool, mouse
button 1 with the control key pressed is also bound to pointer, mouse
button 2 is bound to magnify, and mouse button 2 with control is bound
to ruler.
-->
パレットの一番下にはマウスボタンの現在の機能割り当ての一覧が表示されています。
この図では、マウスボタン 1 はポインタツールに割り当てられていて、
Control キー + マウスボタン 1 も同じくポインタに、
マウスボタン 2 は拡大ツールに、
Controlキー + マウスボタン 2 はものさしツールに割り当てられています。

<!--
Many of the tools have different <a name="alt-meta-capslock">behaviors</a>
if you hold the shift or alt (meta) key down when using the tool.
On the mac there is no alt/meta key, and the Option and Command keys are
usually bound to making a one button mouse look like a three button mouse.
So on the mac fontforge uses the caps-lock key rather than alt/meta.
-->
多くのツールは、
Shift または Alt (Meta) キーを押しながら選択した場合には、
通常と異なる<a name="alt-meta-capslock">挙動</a>を示します。
Mac には Alt/Meta キーは存在せず、
Option キーと Command キーは
1 ボタンマウスを 3 ボタンマウスに見せかけるために使われるのが普通です。
そこで FontForge は
Mac では Alt/Meta の代わりに
CapsLock キーを使用します。

#### The pointer tool
![](/assets/img/windows-cvarrowicon.png)

This tool is used for selecting points, images and referenced glyphs. It
can also move these and scale images and referenced glyphs.

Only things that are in the layer that is currently editable may be
selected or moved or scaled.

A simple click on an unselected point selects it and deselects
everything else. A shift click on a point toggles whether that point is
selected or not. A double click selects all points on the path
containing that point. A tripple click selects everything in the layer.
Clicking on the background will deselect everything. Clicking on the
background and dragging out a rectangle will select everything within
the rectangle. Clicking on a line or spline will select the two end
points of that line or spline. Clicking on the dark part of an image
(when in a layer with images) will select the image. Clicking on the
outline of a referenced glyph will select that reference (if a reference
glyph happens to have the same outline and bounding box, then holding
down the [meta/alt/caps-lock](#alt-meta-capslock) key will
allow you to move it once it is selected, without the meta key you will
resize it).

If a point has no visible control points, then they are at the same
location as the point itself. If you want to select one of the control
points then first select the point (to make the control points active)
then hold down the meta key (use caps-lock on the mac) and depress the
mouse on the point. This should allow you to drag one of the control
points (if you get the wrong point the first time drag it out of the
way, repeat the process to get the other control and then put the first
one back). Sadly some window managers (gnome-sawtooth for one) will
steal meta-clicks. If this happens you will need to use Element-\>Get
Info to set the control points.

![](/assets/img/windows-cpinfo.png)

When you move a control point you have the option
(`View->Show Control Point   Info`) of getting a popup box showing
information about the control point (and its opposite number on the
other side of the on-curve point). You will be told whether this is the
next or previous control point, the absolute location of the point, the
offset from the on-curve point, the slope expressed as a ratio, and as
an angle, and the curvature on this side of the base point. At the very
bottom is the difference between the two curvatures. Try to make this
number approach 0 for curved points.

Once something is selected you may drag it around. If you select
something and drag the mouse then it and everything else selected will
be moved. If you drag an open path and one of the end points happens to
fall on the end point of another open path, then the two will be merged
into one (If you don't want open paths to merge, hold down the
[Alt/meta/caps-lock](#alt-meta-capslock) key). If you drag
a control point then it will be moved (if you drag a control point
defining an implied point, then the implied point(s) will also be
moved).

If you selected a spline, then dragging it will drag the location on the
spline where you pressed the mouse (so you are changing the shape of the
spline).

If you hold the shift key down when you drag then the motion will be
constrained to be either horizontal, vertical, or at a 45° angle. (When
moving control points the combination of shift and [meta
(alt)](#alt-meta-capslock) will mean that the control point
is constrained to be the same angle from the base point as it was before
you started moving it).

If your font has an ItalicAngle set, and the ItalicConstrain preference
item is set, then motion that would normally be constrained to the
vertical is constrained to be along the ItalicAngle.

If you move the mouse to the bounding box of a selected image or
reference glyph and drag it then you will scale that object.

If you move the mouse to the advance width line, then dragging it will
change the width of the current glyph. If there are any bitmaps of this
glyph then their widths will also be updated. If there are any other
glyphs which depend on this glyph (ie. include this glyph as a
reference) and their width was the same as the glyph's, then their
widths will also be updated (so if you change the width of A, then the
width of À, Á, Â, Ã, Ä and Å might also be changed). If you are
displaying vertical metrics (in a font that has them), then you can use
the same technique to modify the vertical advance.

If you are in an accented glyph then you may not be able to change the
width, as its width is bound to that of the base glyph (By setting the
"Use My Metrics" bit in the reference containing the base glyph). This
will be displayed as a lock icon at the top of the window near the width
line.

It is also possible to use the arrow keys to move selected items around.
Each arrow will move the selection one em-unit (this can be changed in
preferences to be any number of em-units) in the obvious direction. The
selection may include the width (right bearing) line (or vertical with
line). If the last thing you selected was a control point then that
point will be moved. If you hold down the shift key at the same time the
up and down arrows will move parallel to the italic angle (be careful of
this: this leads to non-integral values). If you hold down the [meta
(alt)](#alt-meta-capslock) key, then the motion will be 10
times the normal amount.

If you hold down the control key while working with the arrows then the
view will be scrolled rather than moving the selection.

If the glyph is a ligature (and has a ligature entry in Glyph Info) then
it has the potential of having "ligature caret locations". Essentially
this means that between each ligature component it is possible to place
a caret location (so that the word processor will place be able to place
a caret between each component of the ligature). In a ligature window a
series of vertical lines will be drawn across the screen at the caret
locations. By default these lines will be placed at the origin, but you
may move one by placing the mouse pointer on it, depressing the button
and dragging the line around. See the description on [building a
ligature](editexample4.html#ligature) for a more complete description.


#### The magnifying tool
![](/assets/img/windows-cvmagicon.png)

Clicking with the magnifying tool will magnify the view and center it
around the point you clicked on. Holding down the
[Alt/Meta/CapsLock](#alt-meta-capslock) key and clicking
will minify the view, again centered around the point at which you
clicked. Again some window managers will steal meta-clicks, so you may
have to use the View menu to minify (It's called Zoom Out

If you drag out a rectangle with this tool then when you release,
FontForge will shift and scale the view so that your rectangle just fits
into the window.

If your mouse has a scroll wheel then holding down the control key with
the scroll wheel causes it to magnify or minify the window.


#### The scroll tool
![](/assets/img/windows-cvhandicon.png)

You can use this tool to scroll the window without using the scroll
bars.


#### The freehand tool
![](/assets/img/windows-cvfreehandicon.png)

![](/assets/img/windows-freehandctl.png)

You can use this tool to draw a random curve which FontForge will then
attempt to convert into a set of splines. If you hold down the
[Alt/Meta/CapsLock](#alt-meta-capslock) key then FontForge
will close the curve when you release the mouse.

If you double click on the icon in the tool palette you get a dialog
similar to the [Element-\>Expand Stroke](../elementmenu/#Expand+Stroke...) which
will give you slightly more control over the results, as you can have it
not expand the stroke you draw (ie. leave a single trace.)


#### Tools for adding curved, corner and tangent points.
![](/assets/img/windows-cvcurveicon.png) ![](/assets/img/windows-cvhvcurveicon.png) ![](/assets/img/windows-cvcornericon.png) ![](/assets/img/windows-cvtangenticon.png)

These four tools behave similarly, differing only in what kind of point
is added to the view.

If a single point is selected, and if that point is at the end of a path
then depressing the mouse button will create a new point where the mouse
was depressed and draw a spline from the selected point to new point. If
this new location happens to be the end of a path then the two paths
will be joined (or if it is the end of the current path then the path
will be closed).

Otherwise if the mouse is depressed while being on a spline then a point
will be added to that spline.

Otherwise a new point is created not on any path at the location of the
press.

Once the point has been created then it becomes selected and all others
are deselected. You may drag the point around, and if the point is on an
open path and you drag it to the end point of another open path then the
two paths will be joined.

If you double click then a point will be added as above and a [Point
Info](../getinfo/) dlg will appear to give you fine control over the
location of the point and its control points.

The four different point types are

-   curved points (where the incoming and outgoing splines have the same
    slope)
-   horizontal/vertical curved points (similar to the above except the
    slope is constrained to be either horizontal or vertical)
-   corner points (where the incoming and outgoing splines may have
    different slopes)
-   tangent points (where one spline is a line segment and the other
    spline is curved then the curved spline is constrained to start with
    the same slope as the line).


#### The pen tool
![](/assets/img/windows-cvpenicon.png)

This tool behaves differently in cubic and quadratic editing. In many
ways it is similar to the tools above as it adds a point to the current
spline.

In a cubic font the points created are curved points, and they are
initially created with the control points on the point and as you drag
you drag out the control points rather than moving the point itself
around.

In a quadratic font a point will be created half-way between the last
control point and the current location (which becomes the next control
point).

If you hold down the Alt (Meta, etc) key you change the behavior so that
cubic editing looks like quadratic and vice versa.


#### Tools for adding spiro control points
![](/assets/img/windows-cvspiroG4icon.png) ![](/assets/img/windows-cvspiroG2icon.png) ![](/assets/img/windows-cvspirocornericon.png) ![](/assets/img/windows-cvspirolefticon.png) ![](/assets/img/windows-cvspirorighticon.png)

These tools add spiro control points to the current contour, these are
only available in spiro mode, but the basic adding process is similar to
the above.

The different point types are:

-   G4 (continuous up to the fourth derivative)
-   G2 (continuous up to the second derivative)
     Basically, if you have a sharp curve you should probably use a G2
    point, and if a more gentle curve a G4.
-   corner
-   prev constraint point -- vaguely like a tangent (Raph calls this a
    "left" point)
     This type of point should be used where the contour changes from a
    curve to a straight line (where the curve is on the previous side of
    the constraint point)
-   next constraint point -- vaguely like a tangent (Raph calls this a
    "right" point)
     This type of point should be used where the contour changes from a
    straight line to a curve (where the curve is on the next side of the
    constraint point)

This is based on [Raph Levien's work](http://www.levien.com/spiro/) with
clothoid splines which provide constant curvature across points.


#### Spiro mode
![](/assets/img/windows-cvspiromodeicon.png)

This button toggles between editing contours using Bézier control
points, or between using spiro (clothoid) control points.


#### The knife tool
![](/assets/img/windows-cvknifeicon.png)

This tool is used to cut splines. As you drag it across the view
fontforge draws a line showing where the cut will happen. When you
release, every spline you intersect will be cut-- that is at the
location where this line intersects the spline two new points will be
created and the old spline will be split in two connecting to the two
new end points. These endpoints are not joined, so the spline is now
open (or if it were previously open, it is now cut in two).


#### The ruler tool
![](/assets/img/windows-cvrulericon.png)

![](/assets/img/windows-ruler.png)

This tool tells you the current position of the mouse. If the
mouse is near the outline it will give the slope and curvature there. If
the mouse is near a point on the outline will give the slope and
curvature on each side of the point.

If you depress the button and drag, the first line of the tool's pop-up shows
the distance, angle and (x-y) offsets from the first point where you depressed
the mouse to the last point, the mouse's current location. The next lines in
the pop-up show information about points along the line that intersect splines,
including the start and end points of the line itself. If there are more than
two intersections then the x, y, and total distance between the first and last
intersections are shown before the point list.

\[0\] indicates the starting point of the measure line, and the (x-y)
co-ordinates of that point. Initially \[1\] is the end point; when it
intersects with one spline then \[1\] becomes the first intersection point and
\[2\] becomes the end point, and so on. The co-ordinates are followed by the x
and y distances and then the final number is the length of the section ending
at that point; which is also shown directly on the canvas.

If you hold down the [Meta/Alt/CapsLock](#alt-meta-capslock) key then 
information will only be shown when the mouse is depressed.


#### The scale tool
![](/assets/img/windows-cvscaleicon.png)

This tool allows you to scale the selection by eye rather than by a set
amount (if there is no selection then everything in the current layer
will be scaled). The location of the press will be the origin of the
transformation, the further you move the point up and to the right the
more it will be scaled in that dimension. If you want the scaling to be
uniform or only in one dimension then hold down the shift key.

Double clicking on this will bring up the transform dialog with the
"Scale..." option selected.


#### The flip tool
![](/assets/img/windows-cvflipicon.png)

This tool allows you to flip the selection either horizontally or
vertically. Again the point at which you press the mouse is the origin
of the transformation.

Double clicking on this will bring up the transform dialog with the
"Flip..." option selected.

**Note: After flipping an outline you will almost certainly want to
apply [Element-\>Correct Direction](../elementmenu/#Correct+Direction).**


#### The rotate tool
![](/assets/img/windows-cvrotateicon.png)

This tools allows you to rotate the selection freely.

Double clicking on this will bring up the transform dialog with the
"Rotate..." option selected.


#### The skew tool
![](/assets/img/windows-cvskewicon.png)

This tool allows you to skew the selection.

Double clicking on this will bring up the transform dialog with the
"Skew..." option selected.


#### The rotate 3D tool
![](/assets/img/windows-cvrotate3dicon.png)

This tool allows you to rotate the selection in the third dimension and
project the result back onto the x-y plane. An imaginary line is drawn
from the point where you pressed to the current point, this line
determines the axis of rotation. The distance you move from the initial
press determines the amount of rotation.

Double clicking on this will bring up the transform dialog with the
"Rotate 3D..." option selected.


#### The perspective tool
![](/assets/img/windows-cvperspectiveicon.png)

![](/assets/img/windows-Eperspective.png)

This tool allows you to apply a perspective transformation to the
selection (this is a non-linear transformation). This tool uses three
points: The glyph origin, the press point, and the current location of
the cursor. In the image at right the mouse was pressed on the baseline
near the glyph's advance width, and the mouse was released in the upper
middle of the image. The glyph is transformed so that the release point
is treated as the point at infinity. The line between the origin and the
press point defines one axis of the transformation. Distances
perpendicular to this line are retained, distances parallel to it are
scaled as:

    *x' = release_x + (release_y - y)/release_y * ( x - release_x )* *y' = y*


#### The rectangle/ellipse tools
![](/assets/img/windows-cvrecticon.png) ![](/assets/img/windows-cvellipseicon.png)

By default this produces a rectangle, single-clicking on the tool
palette will toggle between rectangle and ellipse, and double clicking
in the tools palette gives you a dialog which allows you to control
whether your rectangles are drawn with round corners, and how both
rectangles and ellipses are specified.

You can choose whether the rectangle (or ellipse) will be drawn between
the point where you depressed the mouse on the view and the point where
you released it (bounding box), or whether the point where you depress
the mouse becomes the center of the rectangle and the point where you
release it provides an end-point (center out).

If you want even more control, you can double click in the glyph view
and get another dialog which allows you to define numerically where the
rectangle/ellipse should be placed, how big it should be, and whether it
should be rotated.


#### The polygon/star tools
![](/assets/img/windows-cvpolyicon.png) ![](/assets/img/windows-cvstaricon.png)

By default this draws a regular polygon, but by double clicking on the
button in the tools palette you can make it draw a star, or select the
number of verteces in your polygon.

The polygon is drawn as though it were inscribed in the circle whose
center is the point where you depressed the mouse and whose radius is
the distance between the press point and the release point. One of the
polygon's verteces will be at the release point.

A star is drawn similarly. It will be a star generated from a regular
polygon. As the number of verteces of the polygon gets larger the star
will look more and more like a circle, for this reason the dialog box
that allows you to pick the number of verteces will also allow you to
pick how far the star's points should extend beyond the circle in which
the polygon is inscribed (this will make a non-regular star, but it
might look nicer).


### Vertical View

![](/assets/img/windows-charview-vert.png)

In this view the vertical metrics of the glyph are shown. You can change
the vertical advance just as you changed the glyph's width (by selecting
the pointer tool and dragging the vertical advance line up or down).


### Grid Fit View

![](/assets/img/windows-GridFit.png)

If you have the freetype library, then you can see the
results of rasterizing your glyph. If you have freetype's bytecode
interpreter enabled you can also see how the truetype instructions in
the glyph have moved the points around (if you don't have the bytecode
interpreter enabled you will see what freetype's autohinter does to
points). This mode can be invoked with `View->Show Grid Fit`...

The Show Grid Fit command will ask you for some basic information first.
It needs to know the pointsize and resolution for which you want the
action performed (the example at right is 12pt on a 72dpi screen).

![](/assets/img/windows-ShowGridFit.png)


### The Debugging View

![](/assets/img/windows-cvdebug.png)

> "I told you butter wouldn't suit the works!" he added, looking angrily
> at the March Hare.
>
> "It was the *best* butter," the March Hare meekly replied.
>
> Alice's Adventures in Wonderland
>  Lewis Carroll

FontForge has a truetype debugger -- provided you have a version of
freetype on your machine with the bytecode interpreter enabled **(Note:
you need a license from Apple to enable this. It is protected by several
patents)**.

The image to the right shows an example of this mode. You invoke it with
`Hints->Debug`, and as with the grid-fit view above you must establish a
pointsize and and resolution. The view divides into two panes, the left
of which is similar to the grid fit view above (except that it changes
as you step through the instructions), the right pane provides a list of
the instructions to be executed.

In addition to showing you all the points in your glyph there are either
2 or 4 additional points. These are the so-called "phantom" points and
represent the horizontal and vertical metrics of the glyph (old versions
of freetype will only display 2 points -- left side bearing and advance
width, while newer versions will display top side bearing and advance
height as well).

As you step through a glyph occasionally points will light up. This is
FontForge's attempt to show you what points will be affected (usually
moved) by the current instruction. Other points will have a circle drawn
around them. These are used as reference points by the instruction.

There are a series of buttons at the top of the instruction view. The
first will single step the truetype program (step into), the second will
step over procedure calls, the third will set a break point at the
return point for the current function and continue until that is hit,
and the fourth will continue until:

-   It hits a break point
-   It hits a watch point
-   It reaches the end of the glyph program
-   An error occurs

The red "STOPPED" arrow shows the current location of the instruction
pointer (and what instruction will be executed next).

The fifth button allows you to set a watch point. You select a point (or
several points) in the left hand pane, and press this button.
Thereafter, whenever one of those points is moved FontForge will stop
the glyph program. (You may also set watch points through the points
window).

When you are in this mode there are a few special "hot keys"

    r   run/restart
    k   kill/quit debugger
    q   kill/quit debugger
    c   continue
    s   step (into)
    n   next (step over)
    f   finish function (continue until we return from the function)

Similarly you may watch storage and cvt locations by clicking on the
appropriate spot in the storage and cvt windows.

You can set a more conventional break point by clicking on an
instruction. A little red stop sign will appear on top of the address
area, and the program will halt when the instruction pointer reaches
that instruction. Clicking on the instruction again will remove the
breakpoint.

Flaw: Currently there is no way to set breakpoints outside of the
current function (or glyph).

Flaw: Currently there is no way to examine the call stack.

The sixth button brings up a menu with which you can control which of
various debugging palettes are visible. The ones available so far are:
Registers, Stack, Points, Storage, Cvt, Raster and Gloss.

![](/assets/img/windows-TTRegisters.png)

Shows the truetype graphics state.

![](/assets/img/windows-TTStack.png)

Shows the truetype stack. The value in parentheses is a 26.6 number.

![](/assets/img/windows-TTPoints.png)

Shows the points. You may choose to view the twilight points, or the
points displayed in the glyph pane (the normal points). You may view the
current location or the original location. You may view them in the
units of the current grid, or in em-units.

When debugging a composite glyph the Transformed check box indicates
whether the points of the current component have been transformed (to
show where they fit in the composite) or not (showing where they are in
the base component -- this is what the instructions are working on).

The points may have some flags associated with them: 'P' means the point
is an on curve point, 'C' means the point is an off curve point (a
control point), 'I' means the point is an on-curve point interpolated
between two control points, 'F' means a phantom point, 'T' means a
twilight point, 'X' means the horizontal touch flag has been set, 'Y'
means the vertical touch flag has been set.

A small stop sign indicates the point is being watched (that is
execution will stop if the point moves). You may change whether a point
is watched by clicking on it.

Contours are separated by horizontal lines

![](/assets/img/windows-TTStorage.png)

Shows the truetype storage locations.

A small stop sign indicates the storage location is being watched (that
is execution will stop if the location changes). You may change whether
a location is watched by clicking on it.

![](/assets/img/windows-TTCvt.png)

Shows the current values in the cvt array.

A small stop sign indicates the cvt location is being watched (that is
execution will stop if the value changes). You may change whether a
location is watched by clicking on it.

![](/assets/img/windows-TTRaster.png)

Shows the current raster with no magnificaton

![](/assets/img/windows-TTgloss.png)

This window tries to provide a gloss for the current instruction. It
gives a brief description of the instruction in the top few lines, then
explains what registers it uses, and shows their values, it shows what
use is made of the stack and attempts to interpret the data on the
stack. Finally it explains what registers will be set, and what will be
pushed onto the stack.

The final button will exit the debugger.

The debugger also responds to some single character commands common to
many debuggers:

    s   step into
    n   step over (next)
    c   continue
    r   restart (with same grid)
    f   step out (finish routine)
    k   kill the debugger
    q   kill the debugger

The Hints-\>Debug menu command can also be used to exit the debugger (by
turning off the debug check box), or to restart the debugger with
different values for the point size and resolution. This dlg can also
control whether the fpgm and prep tables are debugged. Usually debugging
will start when execution reaches the instructions associated with this
glyph.


#### Debugging composite glyphs

FontForge is not as friendly when debugging composite glyphs as it
should be -- this is influenced by the way truetype works. Suppose you
want to debug the "Atilde" glyph.

First FontForge will load and grid fit the "A" glyph, points from the
"tilde" will not be displayed and behavior will be exactly the same as
if you were debugging a stand alone "A".

Then FontForge will load and grid fit the "tilde" glyph, and now points
from the "A" glyph will not be visible. The point numbers on the "tilde"
will be the same as they are in a stand-alone "tilde" (whereas in a true
representation of "Atilde", the points numbering in the "tilde"
component will be offset by the number of points in the "A" component).
The "tilde" may appear oddly positioned, this is caused by rounding: the
"tilde" will usually be translated, and this translation will usually be
rounded to fit the pixel grid. The width line will show the width of the
"tilde" and not of the "Atilde".

Finally FontForge will execute any instructions in the composite itself,
now all sub-components will be displayed, and all points will be
numbered as they should be.

Several words of caution:

-   If a component, or the composite as a whole, has no instructions
    then FontForge will not debug that piece (there will be nothing to
    debug).
-   FontForge does not translate references which do point matching
    properly until the entire glyph has been loaded.


![](/assets/img/windows-mmcharview.png)

Intermediate version of "A" with two other styles in the background


### Multiple Master View


In a multiple master font the [MM](../mmmenu/#outline-char) menu gives
you control over which style of the font you are editing. It will also
allow you to display any (or all) of the other styles in the background.
Although the menu is called "MM" it applies equally to Apple's
distortable fonts ("\*var" fonts, like Skia).


### Multiple Layer Editing

![](/assets/img/windows-charview-multilayer.png)

If you wish to [edit type3 fonts](../multilayer/), FontForge can display a
glyph broken down into a series of strokes and fills and allow you to edit each
one.
