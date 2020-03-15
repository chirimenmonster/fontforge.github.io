---
published: true
layout: default.ja
title: 点、参照情報
---
<!--
published: true
layout: default
title: Point, Reference Information
-->

[table_of_contents]


<!--
In the Outline View the Get Info command can generate one of four
different dialogs depending on what is selected. If a single thing is
selected, and that thing is a point then the [point
info](#Point+Info) dialog is brought up, if it is a reference then
the [reference dialog](#Reference+Info) is brought up, if
it is a background image then the [image dialog](#Image+Info) is
brought up. If it is an anchor point then the [anchor
point](#Anchor+Points+Info) dialog is brought up.
-->
アウトラインビューでは、
<span class="command">情報を得る(I)</span>
コマンドを実行すると、
その時選択している内容によって異なる 4 種類のダイアログを生成することができます。
1 個の物だけを選択している場合、
それが点であれば
[点の情報](#点の情報-point-info)
ダイアログが起動し、
参照であれば
[参照](#参照の情報-reference-info)
ダイアログが起動し、
背景画像であれば
[画像](#画像情報-image-info)
ダイアログが起動します。
選択されているのがアンカーポイント 1 個だけのときは
[アンカーポイント](#アンカーポイント情報-anchor-points-info)
ダイアログが起動します。


<!--
### Point Info
-->
### 点の情報 (Point Info)

![](/assets/img/dialogs1-pointinfo.png)

<!--
This shows information about the current point. The Base position is 
where the point itself is.
-->
ここでは現在の点に関する情報を表示します。
<span class="command">基点(B)</span> (Base)
は、その点自身の置かれた位置を表します。

<!--
The Next CP shows both the location of the next control point, and the
offset to that point from the base (and whether this setting is the
default for that point, if this point is the last on an open contour
then the [] Default button will be grey), underneath the offsets it
shows the same information in a different format -- as a distance from
the point itself, and the angle to it.
-->
<span class="command">次の点</span> (Next CP)
は次の制御点の位置と、基準点からのオフセット
(および、その位置設定がその点に対するデフォルトかどうか。
もしその点が開いたパスの最後に位置する場合は、
<span class="command">\[] デフォルト</span>
ボタンは灰色表示になります)
の両方を表示します。
その下に表示されているのは、同じ情報を異なる表現
-- 点自体からの距離と、その角度
-- で表した物です。

<!--
The Prev CP does the same for the previous control point.
-->
<span class="command">前の点</span> (Prev CP)
は同じ情報を前の制御点に対して表示します。

<!--
You may change any of these and the change is reflected in the outline
view. Your changes are constrained by the point type (for instance with
tangent points, you may not change the angle fields as these are fixed).
-->
これらの値はすべて変更可能で、
変更はアウトラインビューに反映されます。
可能な変更は、点の型によって制約されています
(例えば、曲線の開始点では、
角度フィールドは固定されているので変更できません。

<!--
FontForge also shows you the curvature of the two splines on either side
of the point. In a perfect world these will be equal for curve points
and the join will appear smooth. It also shows the difference between
the two. The curvature is the reciprical of the radius of the circle
tangent to the curve (a straight line has curvature 0 because it is a
circle with infinite radius so its reciprical is 0). For most curves in
letters this radius is fairly large when expressed in em-units (and its
reciprical is correspondingly small). To make it easier to read,
FontForge scales it by the em-size of the font -- this is equivalent to
expressing it in units where 1 corresponds to an em (rather than 1000 or
2048).
-->
また、FontForge は 2 本のスプラインのそれぞれの側の曲率を表示します。
理想上は曲線上の点の場合、これらは同じ値になり、結合箇所は滑らかに見えるでしょう。
また、2 つの間の違いも表示します。
曲率とは、曲線への接触円の半径の逆数です
(直線の曲率は 0 となります。なぜならそれは無限の半径をもつ円となり、その逆数が 0 となるからです)。
文字に用いられる曲線のほとんどにおいてはこの曲率は em ユニット表示でかなり大きな値になります
(曲率はそれに応じて小さい値となります)。
読みやすくするために、FontForge はそれにフォントの em サイズを掛けます
-- これは、em が (1000 や 2048 ではなくて) 1 になる単位系で表現するのと同じことです。

<!--
You may also change whether a point is a curve, corner or tangent point
(Caution: Changing from a corner point to a curve point and back to a
corner point is NOT a no op. It may change the control points) You may
move on to the next or previous point on the path, or the next/previous
point of the current contour. If you cancel then all changes to all
points are canceled.
-->
点が曲線上の点か、角の点、それとも曲線の開始点のどれであるかを変更することもできます。
(警告: 角の点を曲線上の点に変換し、また角の点に戻すのは何もしないのと同じでは「ありません」)。
パス上の前または次の点に移るか、現在の輪郭上の次/前の点に移動することができます。
操作をキャンセルすると、すべての点に対するすべての動作が取り消されます。

<!--
The colors of the labels reflect the colors of the items they refer to.
The point itself will be drawn in red, the previous control point will
be drawn in magenta and the next control point will be drawn in dull
cyan.
-->
ラベルの色は、それが参照しているものの色を反映しています。
点そのものは赤で表示され、前の制御点はマゼンタ、次の制御点は鈍いシアンで表示されます。

![](/assets/img/dialogs1-pointinfo-interp.png)

<!--
When editing truetype interpolated points it is more important to view 
the control points and let the base point continue to be interpolated.
The Normal and Interpolated radio buttons control which view is active.
-->
TrueType の補完された点を編集しているときには、
制御点を見て、基点が依然補完されるように調整することがより重要となります。
どちらの表示法を有効にするかは、
<span class="command">通常(N)</span>
ラジオボタン、または
<span class="command">補完される点(I)</span>
ラジオボタンで切替えます。

<!--
Pressing Interpolated may move the point to position it correctly
for interpolation.
-->
<span class="command">補完される点(I)</span>
を押すと、補完される正しい位置まで点が移動されるでしょう。


<!--
### Hint Mask
-->
### ヒントマスク (Hint Mask)

![](/assets/img/dialogs1-hintmaskinfo.png)

![](/assets/img/dialogs1-charwithhintmask.png)

<!--
If you want to control what hints are active at a given point (and at all
subsequent points until an new hintmask is given) you can use the hint
mask pane. This provides you with a list of all hints in the current glyph,
you should select the ones which you want active.
-->
もし、指定された点
(および、この後で、新しいヒントマスクが作成される前に作成されるすべての点)
でどのヒントが有効になっているかを制御したいならば、
ヒントマスク 画面を使うことができます。
これは、現在のグリフ内のすべてのヒントのリストを提供します。
その中から、有効にしたいヒントを 1 つ選んでください。

<!--
As you select hints, the glyph view will darken those hints so you can
see what you've selected.
-->
ヒントを選択すると、グリフビューのヒントが暗い色で表示されるので、選択されたヒントを目で確認できます。

<!--
Points with circles drawn around them have hintmasks.
-->
丸で囲まれた点は、ヒントマスクがあることを示しています。

<!--
According to Adobe's documentation you should never have two hints which
conflict active at the same time. FontForge will warn you if you do
this. Unfortunately there are fonts (even fonts from Adobe) which do not
follow this rule, so I have made this a warning rather than an error.
-->
Adobe の文書によると、同時に有効となっていて矛盾する 2 つのヒントが含まれることは全く禁じられています。
FontForge は、それを行うと警告を発します。
残念なことにこのルールに従わないフォント (Adobe が販売しているフォントですら) が実在するので、
これをエラーとはせずに警告に止めています。

<!--
Remember to hold the control key down when making disjoint selections.
-->
連続していない複数の要素を選択するときには Control キーを押すことに留意してください。

<!--
Sadly the direction in which hintmasks apply is backwards from what you
would expect (the hintmask applies to this point an all previous points
on the contour, rather than all subsequent ones).
-->
残念ながらヒントマスクが適用される方向は普通に考える向きとは逆さまです
(ヒントマスクは、この点から輪郭上のすべての前の点に対して適用されるのであって、
その後の点に対して適用されるのではありません)。


<!--
#### Active Hints
-->
#### 有効なヒント (Active Hints)

<!--
This looks just like the hint mask, except you cannot change anything it
in. It shows you what hints are currently selected at this point. If a
point has a hint mask then the two will be identical.
-->
これはヒントマスクと見た目上同じですが、ここでは何も変更できない点が異なります。
現在の点においてどのヒントが現在選択されているかを表示します。
点にヒントマスクが設定されているならば、これら 2 つは同一になります。


<!--
### Spiro Point Info
-->
### スピロポイント情報 (Spiro Point Info)

![](/assets/img/dialogs1-spiropointinfo.png)

<!--
If you are editing in spiro (clothoid) mode rather than Bezier mode,
then there are no control points and the get info dialog is much
simpler. Just the location of the point and the point type.
-->
ベジエモードではなくスピロ (クロソイド) モードで編集している場合、
制御ポイントはなく、情報の取得ダイアログははるかに簡単です。
ポイントの位置とポイントタイプのみです。


<!--
### Anchor Points Info
-->
### アンカーポイント情報 (Anchor Points Info)

![](/assets/img/dialogs1-agetinfo.png)

<!--
This dialog shows the selected [anchor point](/en-US/tutorials/overview/#Anchors)
with the anchor class, location, type and (for ligatures) the ligature
index. You may change any of these attributes (as long as your changes
are reasonable). You may create new points or delete the current one. As
with normal points above you may step through all the anchor points in
your glyph.
-->
このダイアログは選択中の
[アンカーポイント](/en-US/tutorials/overview/#Anchors)
をアンカークラス、位置、タイプと (合字については) 合字のインデックスを表示します。
これらの任意の属性を変更可能です
(その変更が筋が通っている場合)。
点を新規に作成したり現在ある点を削除したりできます。
上で説明した通常の点と同様、
グリフ内に存在するアンカーポイントを順次切り替えて表示することができます。

<!--
In a truetype font you can force the anchor to track a contour point in
the truetype glyph. This point can then be manipulated with truetype
instructions to grid fit it properly with the current rasterization.
-->
TrueType フォントでは、
TrueType グリフ内の 1 個の輪郭点を保持するためにアンカーを強制することができます。
この点はその後 TrueType 命令によって現在のラスタライズ処理に適したグリッド合わせ操作を行うことができます。

<!--
Anchor points may also be created with the [Point->Add Anchor](../pointmenu/#Add+Anchor+Point...) command. 
-->
アンカーポイントは
[<span class="command">点(P)->アンカーを追加(A)</span>](../pointmenu/#アンカーを追加a-add-anchor-point)
コマンドで作成することもできます。

<!--
### Reference Info
-->
### 参照の情報 (Reference Info)

![](/assets/img/dialogs1-rgetinfo.png)

<!--
This dialog shows the name of the selected reference, its encoding in
the font and its postscript transformation matrix. You may alter the
transformation matrix if you desire.
-->
このダイアログは選択された参照の名前、そのフォント内でのコード位置と PostScript 変換行列を表示します。
必要ならば変換行列を変更することもできます。

<!--
The transformation matrix maps points in the glyph being refered to into
their location in the current glyph: 
-->
変換行列はグリフ内の点を、参照されているグリフでの元の位置から、現在のグリフ上の位置に変換します:

	xcurrent = TM[1,1]*xref +   TM[2,1]*yref + TM[3,1]
	ycurrent = TM[1,2]*yref +   TM[2,2]*yref + TM[3,2]

<!--
The Use My Metrics checkbox is useful in truetype fonts where it forces
the metrics (width) of a composite glyph (for exampe acute a) is the
same as the metrics of one of its components (for example a). This is
especially important in fonts containing instructions that might modify
a glyph's width.
-->
<span class="command">この参照を使用</span> (Use My Metrics)
チェックボックスは、
TrueType 複合グリフ (例えば a アキュート) のメトリック (幅) が、
その構成要素の一つ (例えば a) の幅と等しいことを強制したいときに役立ちます。
これは、グリフの幅を変更する可能性のある命令を含んだフォントにおいて特に重要です。

<!--
The Round To Grid checkbox is also used in truetype hints and indicates
that the translation should be rounded to the rasterizer's grid before
being applied to the points of the reference. This means that the
grid-fitting done by the reference's instructions will still be useful
in the composite.
-->
<span class="command">グリッド単位に丸める</span> (Round To Grid)
チェックボックスは TrueType ヒントでも用いられ、
平行移動を参照の点に適用される前に、
移動量をラスタライズ時のグリッドに丸める必要があることを表します。
その結果、参照の命令によって行われたグリッド合わせが複合グリフでも有効に利用できます。

<!--
In a truetype font a reference may be positioned by matching two points,
one in the base character, and one in the reference itself. In the
example at right, the reference to "acute" will be moved until point 12
in "acute" is at the same place as point 33 in the base glyph. The glory
of this method is that the truetype instructions assocated with the
glyphs can move these points around to an appropriate location for the
current pixelsize.
-->
TrueType フォントでは、
参照の位置指定を、基底文字と参照それ自体から 1 個ずつ選んだ 2 個の点を重ね合わせることによって行うことができます。
右の例では、参照 "acute" は、
基底グリフ (その如何を問わず) の点 0 に "acute" の点 2 が重なり合うまで移動されます。
この方法の素晴らしいところは、
グリフに付随する TrueType 命令が、
現在のピクセルサイズにふさわしい位置までそれらの点を移動することができることです。

<!--
Points in a composite glyph are numbered by counting the points of the
first component, adding 4 (for the 4 phantom (metric) points), then
counting the points in the second composite, adding 4, etc. The first
composite is the one which is drawn first, not the one which is added
first. The Base numbering scheme is from the full composite, while the
reference point is numbered by the current reference. The current
reference must be drawn after the base point. You may use
[Element->Order](../elementmenu/#Order) to reorder the references.
-->
複合グリフに含まれる点は、
最初の要素に含まれる点の個数を数え、
それに 4 (ファントム (メトリック) ポイント 4 個分) を加える、
次に 2 番目の構成要素の点の個数を数え、
4 をくわえ、
というようにして番号づけされます。
最初の構成要素は最初に描画される要素であり、
最初に追加される要素ではありません。
基底グリフの番号づけ方式は複合グリフ全体に由来しますが、
参照点は現在の参照により番号づけられた物を用います。
現在の参照は基底文字の後に描画しなければなりません。
参照の並び順は
[<span class="command">エレメント(L)->順序</span](../elementmenu/#Order)
を使って変更することができます。

<!--
(You should probably not set Round To Grid when doing point matching)
-->
(おそらく、点の重ね合わせを行う時は、
<span class="command">グリッド単位に丸める</span>
をチェックしておくべきでしょう)

<!--
The bounding box information is informative only and displays the
current location and size of the reference.
-->
境界ボックス情報は参考情報であり、参照の現在の位置とサイズを表示します。

<!--
The [Show] button will open a glyph outline view showing the glyph being
referred to.
-->
<span class="command">表示(S)</span>
ボタンを押すと、参照されているグリフのアウトラインビューを開きます。


<!--
### Image Info
-->
### 画像情報 (Image Info)

<!--
This dialog gives the offset to the lower left corner of the image and
the scale factors applied to the image. Currently you may not alter
anything here, it is purely informational.
-->
このダイアログは、画像の左下隅のオフセットと、画像に適用された拡大/縮小率を表示します。
現在のところ、ここでは何も編集できません。単に情報提供の役にしか立ちません。
