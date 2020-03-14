---
published: true
layout: default.ja
title: 点メニュー
---
<!--
published: true
layout: default
title: The Point Menu
-->

<!--
This menu is only available in the Outline Character View.
-->
このメニューはアウトライングリフビューでのみ利用可能です。


[table_of_contents]


<!--
#### Curve
-->
#### 曲線上の点(C) (Curve)

<!--
If all the selected points are Curve points then this entry will be
checked. Selecting it will change all selected points to be Curve
points.
-->
選択中の点がすべて曲線上の点ならば、この項目にチェックマークがついています。
これを実行すると、選択中の点がすべて曲線上の点に変換されます。

<!--
#### Corner
-->
#### 角の点(O) (Corner)

<!--
If all the selected points are Corner points then this entry will be
checked. Selecting it will change all selected points to be Corner
points.
-->
選択中の点がすべて角の点ならば、この項目にチェックマークがついています。
これを実行すると、選択中の点がすべて角の点に変換されます。

<!--
#### Tangent
-->
#### 曲線の開始点(T) (Tangent)

<!--
If all the selected points are Tangent points then this entry will be
checked. Selecting it will change all selected points to be Tangent
points.
-->
選択中の点がすべて曲線の開始点ならば、この項目にチェックマークがついています。
これを実行すると、選択中の点がすべて曲線の開始点に変換されます。

<!--
#### Make First
-->
#### 開始点に設定(M) (Make First)

<!--
If exactly one point is selected and it is on a closed path and it is
not the "first point" of that path, then it will become the first point.
-->
閉じたパスに含まれる点が 1 個だけ選択されていて、
その点がパスの "最初の点" ではない場合、
選択中の点がパスの最初の点に変更されます。

<!--
#### Can Be Interpolated, Can't Be Interpolated
-->
#### 補間可能, 補間不可能 (Can Be Interpolated, Can't Be Interpolated)

<!--
When editing truetype curves, an on-curve point can be omitted from the
point list that is stored in the output font if it happens to be exactly
midway between its two control points. This makes for slightly smaller
files and is generally a good thing. However if the point is
interpolated then it cannot be referred to in instructions (or reference
point matching), so on rare occasions you will need to be able to turn
off this interpolation.
-->
TrueType の曲線を編集中に、
曲線上の点がその両側にある制御点のちょうど中間にある場合、
出力されるフォントに格納される点のリストではその点は省略可能です。
これによりファイルが僅かに小さくなるので、
一般的には望ましいことです。
しかしながら、補間によって作成された点は、
命令 (または参照点の対応づけ) の中で参照することができませんので、
そのような稀な場合のために、
この補間を行わないようにすることができる必要があるでしょう。

<!--
#### Add Anchor Point...
-->
#### アンカーを追加(A)... (Add Anchor Point...)

![](/assets/img/filemenu-agetinfo.png)

<!--
This command adds a new [anchorpoint](/en-US/tutorials/overview/#Anchors)
to the glyph. The last click in the window provides a default location
for the point.
-->
このコマンドは
[アンカーポイント](/ja-JP/tutorials/overview/#Anchors)
をグリフに追加します。
ウィンドウ内で直前にクリックした場所がアンカーの初期位置となります。

<!--
See [the overview](/en-US/tutorials/overview/#Anchors) and
the [Element-\>Get Info command](../getinfo/#Anchors) for more info.
-->
より詳しい情報については
[概要](/ja-JP/tutorials/overview/#Anchors)
と
[<span class="command">エレメント(L)->情報を得る(I)</span> コマンド](../getinfo/#Anchors)
を参照してください。


<!--
#### Acceptable Extrema
-->
#### 極地を受容する (Acceptable Extrema)

<!--
Tells the validator that it is OK for this spline to have extrema. You
select a spline by selecting its two end-points.
-->
このスプラインに極値があってもよいことを検証ツールに伝えます。
2 つの端点を選択して、スプラインを選択します。

<!--
#### Make Line
-->
#### 直線に変換(L) (Make Line)

<!--
If two adjacent points are selected then make the spline between them
into a straight line. If two points are selected and they are the
endpoints of their respective (open) contours, then join them with a
line. If a point is selected and has no adjacent selected points then
make its control points be on top of the point
-->
パス上の隣接する 2 個の点が選択されている場合、
その点の間のスプラインを直線に変換します。
2 個の点が選択されていて、
それらがそれぞれの (開いた) 輪郭の端点である場合、
それらを線で結合します。
1 個の点が選択されていて、
隣接する制御点が選択されていない場合、
その点から伸びる制御点をその点と同じ場所に設定します。


<!--
#### Make Arc
-->
#### 円弧を作成 (Make Arc)

<!--
If two adjacent points are selected then make the spline between them
into an elliptical arc. If two points are selected and they are the
endpoints of their respective (open) contours, then join them with an
elliptical arc.
-->
2 個の隣接する点が選択されている場合、
それらの間のスプラインを楕円弧にします。
2 個の点が選択され、
それらがそれぞれの　(開いた) 輪郭の端点である場合、
それらを楕円弧で結合します。

<!--
FontForge chooses an ellipse which runs through the two points and is
tangent to the slope at those points. This is not enough information to
determine an ellipse (three points and two tangents are needed) so in
general there will be an infinite number of solutions, thus FontForge
may not pick the one you had your heart set on.
-->
FontForge は、
2 個の点を通過し、かつ、それらの点の勾配に接する楕円を選択します。
これは楕円を決定するのに十分な情報ではないため
(3 点と 2 つの接線が必要です)、
一般に無限の数の解が存在します。
そのため、FontForge はあなたが心の中で思った解を選択しないかもしれません。

<!--
It is also possible to specify a set of input constraints which cannot
be met by any ellipse.
-->
楕円では満足しない入力制約の組み合わせを指定することも可能です。

<!--
FontForge will first search for ellipses so that one of the selected
points lies one of the axes of the ellipse. If it can't find one like
that it will perform a more general search.
-->
FontForgeは 最初に楕円を検索し、
選択した点の 1 つが楕円の軸の 1 つに位置するようにします。
そのようなものが見つからない場合、より一般的な検索を実行します。

<!--
(If you hold down the \<Alt\> key when you select the menu item, then
FontForge will place a copy of the full ellipse into the background
layer -- this was for debugging, but I thought it kind of cool so I left
it in).
-->
(メニュー項目を選択するときに \<Alt\> キーを押したままにすると、
FontForge は完全な楕円のコピーを背景レイヤーに配置します。
-- これはデバッグ用でしたが、ちょっとクールだと思ったのでそのままにしました)。


<!--
#### Insert Point on Spline at...
-->
#### スプラインにポイントを挿入... (Insert Point on Spline at...)

<!--
Select the two end-points of a spline, then bring up this dialog. You
can request that FontForge insert a point on the selected spline with
either a given X or a given Y coordinate.
-->
スプラインの 2 個の端点を選択して、このダイアログを表示します。
FontForge に、X 座標または Y 座標を指定して、
選択したスプラインに点を挿入するように要求できます。

<!--
#### Center Between Control Points
-->
#### 制御点の中間に移動(B)

<!--
In truetype, if an on-curve point is centered between its control
points, then that point may be omitted when written to the output file.
This command allows you to create such a point more easily.
-->
TrueType では、
曲線上の点が両側の制御点の中点にあるときには、
その点を出力ファイルに書き込むのを省略することができます。
このコマンドは、そのような点を簡単に作成することができます。

<!--
#### Name Contour
-->
#### 輪郭に名前を付ける (Name Contour)

<!--
A contour may be named. This is designed for use in the Guide line (and
Background) layer. You can attach a mnemonic name to a guide line (like
"X-Height" or "Cap-Height" or whatever strikes your fancy).
-->
輪郭には名前を付けることができます。
これは、ガイドライン (および背景) レイヤーで使用するために設計されています。
ガイドラインには
("X-Height" や "Cap-Height" などのイメージしやすい)
呼び名を付けることができます。

<!--
#### Make Clip Path
-->
#### クリップパスの作成 (Make Clip Path)

<!--
Only meaningful in Type3 fonts. For a more complete description see the
section on [Type3 editing](../multilayer/#ClipPath). The clipping path
will be set to any selected contour(s) in the glyph. If no contour is
selected then there will be no clipping path.
-->
Type3 フォントでのみ意味があります。
より完全な説明については、
[Type3 編集](../multilayer/#クリッピングパス)
のセクションを参照してください。
クリッピングパスは、グリフ内の選択された輪郭に設定されます。
輪郭が選択されていない場合、クリッピングパスはありません。
