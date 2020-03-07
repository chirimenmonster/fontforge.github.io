---
published: true
layout: default.ja
title: 編集メニュー
---
<!--
published: true
layout: default
title: The Edit Menu
-->


<!--
In the Metrics View this menu is greyed out. The commands are only
available in text fields.
-->
このメニューはメトリックビューでは灰色表示になっており使用できません。
このコマンドはテキストフィールドでのみ使用可能です。

[table_of_contents]


<!--
**NOTE**: In the metrics view this menu will be disabled when one of the
text fields has the focus.
-->
**注意**:
メトリックビューでテキストフィールドのどれかにフォーカスが当たっているときは、このメニューは使用できません。


<!--
#### Undo
-->
#### 元に戻す(U)

<!--
In the outline view and the bitmap view this will undo the last command.
The number of commands that may be undone for any glyph is controlled by
the [UndoDepth](../prefs/#UndoDepth) preference item.
-->
アウトラインビューとビットマップビューでは、最後に実行したコマンドを取り消します。
各グリフに対してコマンド取り消しを繰り返し行える回数は、
環境設定項目 [UndoDepth](../prefs/#UndoDepth) で変更することができます。

<!--
In the font and metrics views, this does NOT undo the last command. It
undoes the last operation on all selected glyphs.
-->
フォントメトリックビューでは、最後に実行したコマンドを取り消し「ません」。
選択中のすべてのグリフに対して、最後に行った操作を取り消します。


<!--
#### Redo
-->
#### やり直し(R)

<!--
In the outline view and the bitmap view this will redo the last command
undone. Up to twelve commands may be redone (after that they get thrown
away)
-->
アウトラインビューとビットマップビューでは、最後に取り消したコマンドを再実行します。
各グリフに対して (以前取り消したコマンドの再実行数は 12 回まで可能です。

<!--
In the font and metrics views, this does NOT undo the last command. It
undoes the last operation on all selected glyphs.
-->
フォントメトリックビューでは、最後に実行したコマンドを再実行「しません」。
選択されたすべてのグリフに対して、最後に取り消した操作を再実行します。


<!--
#### Cut
-->
#### 切り取り(T)

<!--
In the font view this command puts the foreground of all selected glyphs
into the clipboard and then deletes them. Depending on the setting of
[Copy From](#Copy.From) it will either refer all glyphs (bitmap and outline)
corresponding to this entry, or just the glyph being displayed.
-->
フォントビューではこのコマンドは選択中のすべてのグリフの前面データをクリップボードに移動し、
元のグリフから削除します。
[<span class="command">コピー元の指定(F)</span>](#Copy.From)
の設定によって、
これらのグリフに割り当てられた全データ (ビットマップとアウトライン) をコピーするか、
表示されているグリフのデータだけをコピーするかが決まります。

<!--
In the Outline View this will copy any selected points, References, or
Images into the clipboard and then delete them. If a point is removed
from a path then the path will be broken at there, see the
[Merge](#Merge) command for information on how to leave the path whole
but without the point. (if there is no selection nothing happens)
-->
アウトラインビューではこのコマンドはすべての選択中の点、参照、または画像をクリップボードにコピーし、削除します。
点がパスから削除された場合、パスはそこで分断されます。
パスをまるごと残したままその上の点を削除する方法は
[<span class="command">併合(M)</span>](#Merge)
を参照してください
(何も選択していないときには何も起こりません)。

<!--
In the Bitmap View this will copy the selection into the clipboard and
then delete it. If there is no selection nothing happens.
-->
ビットマップビューではこのコマンドは選択範囲をクリップボードにコピーしたのち、
文字から削除します。
何も選択していないときには何も起こりません。


<!--
#### Copy
-->
#### コピー(C)

<!--
In the font view this command puts the foreground and hints of all
selected glyphs into the clipboard. Depending on the setting of
[Copy From](#Copy.From) it will either copy all glyphs (bitmap and outline)
corresponding to this entry, or just the glyph being displayed. Normally
it will not copy a glyph's name, but if [Char Metadata](#Char.Metadata)
is set then it will copy the name as well.
-->
フォントビューではこのコマンドは選択中のすべてのグリフの前面データとヒントをクリップボードにコピーします。
[<span class="command">コピー元の指定(F)</span>](#Copy.From)
の設定によって、
これらのグリフに割り当てられた全データ (ビットマップとアウトライン) をコピーするか、
表示されているグリフデータだけをコピーするかが決まります。
通常はグリフの名前はコピーしませんが、
[<span class="command">グリフのメタデータ(N)</span>](#Char.Metadata)
が設定されているときは、グリフの名前も一緒にコピーします。

<!--
In the Outline View this will copy any selected points, References, or
Images into the clipboard. If there is no selection everything in the
current layer will go into the clipboard.
-->
アウトラインビューではこのコマンドはすべての選択中の点、参照、または画像をクリップボードにコピーします。
何も選択していないときには、現在のレイヤーの全内容をクリップボードにコピーします。

<!--
In the Bitmap View this will copy the selection into the clipboard, if
there is no selection everything is copied.
-->
ビットマップビューではこのコマンドは選択範囲をクリップボードにコピーします。
何も選択されていないときは、全体がコピーされます。

<!--
To external applications selected points (and associated contours) will
be exported to the clipboard with format "image/eps", while a selected
image will be exported with formats "image/png" and "image/bmp". If you
Copy a series of glyphs into the clipboard, the only the first one will
be exported to external applications. If the clipboard contains a single
point, then this will also be exported in STRING format (giving the
coordinates of the point); the intent is to make it easier to people to
identify the point. See the section on
[selections](../../reference/selections/)
-->
外部のアプリケーションのために、選択した点 (とそれに付随する輪郭) は、
クリップボードに"image/eps" でエクスポートされ、
選択した画像は "image/png" および "image/bmp" でエクスポートされます。
一連のグリフをクリップボードにコピーしたとき、
最初の 1 個のグリフだけが外部アプリケーションにエクスポートされます。
クリップボードに独立した点が含まれている場合、
それは (点の座標を指定して) STRING フォーマットでもエクスポートされます。
その理由は、点の識別を行いやすくするためです。
セクション
[選択](../../reference/selections/)
を参照してください。


<!--
#### Copy Reference
-->
#### 参照をコピー(O)

<!--
In the font view this command puts a reference to all selected glyphs
into the clipboard.
-->
フォントビューでは、このコマンドは選択中のすべてのグリフへの参照をクリップボードに追加します。

<!--
In the Outline and Bitmap Views this will copy a reference to the
current glyph into the clipboard (only available in foreground mode).
-->
アウトラインビューでは、このコマンドは現在のグリフへの参照をクリップボードにコピーします
(前面モードでのみ使用可能です)。


#### Copy Lookup Data

<!--
Copies lookup data (substitutions, ligatures, kerning, anchor points,
etc) from the selected glyphs. This command does not work quite as
expected:
-->
選択したグリフからルックアップデータ
(換字、合字、カーニング、アンカーポイントなど)
をコピーします。
このコマンドは期待どおりには機能しません。

<!--
-   The data are not actually copied. Instead fontforge makes a note of
    which glyphs it copied the data from. FontForge actually copies the
    data when the user does a Paste (so any changes in the lookup data
    will be pasted).
-   When the user does a Paste s/he will be prompted with a dialog
    asking what lookups should be copied.
-->
-   データは実際にはコピーされません。
    代わりに、FontForge はどのグリフからデータをコピーしたかを記録します。
    FontForge が実際にデータをコピーするのは、ユーザーが
    <span class="command">貼り付け</span>を行うときです
    (したがって、ルックアップデータに加えられた変更も貼り付けられます)。
-   ユーザーが
    <span class="command">貼り付け</span>
    を行うと、
    どのルックアップをコピーするかを尋ねるダイアログが表示されます。

<!--
#### Copy Width
-->
#### 幅をコピー(W)

<!--
In the Font View this command copies the widths of all selected glyphs
and stores them in the clipboard.
-->
フォントビューでは、このコマンドは選択中のすべてのグリフの幅をコピーし、クリップボードに格納します。

<!--
In the Outline View this command copies the width of the current glyph
and stores it in the clipboard.
-->
アウトラインビューでは、このコマンドは現在のグリフの幅をコピーし、クリップボードに格納します。

<!--
This command is not available in the Bitmap View.
-->
このコマンドはビットマップビューでは使用できません。


<!--
#### Copy VWidth
-->
#### 高さをコピー(V)

<!--
In the Font View this command copies the vertical widths of all selected
glyphs and stores them in the clipboard.
-->
フォントビューでは、このコマンドは選択中のすべてのグリフの縦書き時の送り幅をコピーし、クリップボードに格納します。

<!--
In the Outline View this command copies the vertical width of the
current glyph and stores it in the clipboard.
-->
アウトラインビューでは、このコマンドは現在のグリフの縦書き時の送り幅をコピーし、クリップボードに格納します。

<!--
This command is not available in the Bitmap View.
-->
このコマンドはビットマップビューでは使用できません。


<!--
#### Copy LBearing
-->
#### 左サイドベアリングをコピー(P)

<!--
In the Font View this command copies the left side bearings of all
selected glyphs and stores them in the clipboard.
-->
フォントビューでは、このコマンドは選択中のすべてのグリフの左サイドベアリングをコピーし、クリップボードに格納します。

<!--
In the Outline View this command copies the left side bearing of the
current glyph and stores it in the clipboard.
-->
アウトラインビューでは、このコマンドは現在のグリフの左サイドベアリングをコピーし、クリップボードに格納します。

<!--
This command is not available in the Bitmap View.
-->
このコマンドはビットマップビューでは使用できません。


<!--
#### Copy RBearing
-->
#### 右サイドベアリングをコピー(G)

<!--
In the Font View this command copies the right side bearings of all
selected glyphs and stores them in the clipboard.
-->
フォントビューでは、このコマンドは選択中のすべてのグリフの右サイドベアリングをコピーし、クリップボードに格納します。

<!--
In the Outline View this command copies the right side bearing of the
current glyph and stores it in the clipboard.
-->
アウトラインビューでは、このコマンドは現在のグリフ右サイドベアリングをコピーし、クリップボードに格納します。

<!--
This command is not available in the Bitmap View.
-->
このコマンドはビットマップビューでは使用できません。


<!--
#### Copy Grid Fit
-->
#### グリッド合わせをコピー(D)

<!--
Only available in the outline glyph view and only if [View-\>Show Grid
Fit](../viewmenu/#Show.Grid.Fit) is selected. This will place a copy of
the grid fit version of the glyph into the clipboard.
-->
アウトライングリフビューでのみ使用可能で、
使う時には 
[表示(V)->グリッド合わせを表示(W)](../viewmenu/#Show.Grid.Fit)
を選択していなければなりません。
このコマンドは現在のグリフにグリッド合わせを適用したものをクリップボードにコピーします。


<!--
#### Paste
-->
#### 貼り付け(P)

<!--
In the Font View this command will paste whatever is in the clipboard
into the foregrounds of all selected glyphs (exception: if the clipboard
contains an image it will usually not go into the foreground), clearing
out whatever was there. If there are more selected glyphs than there is
information in the clipboard then the clipboard will be repeated until
all selected glyphs have had something pasted in them (that is if glyphs
A and B were selected when the copy happened and now glyphs C, D and E
are selected, the C will get A, D will get B and E will also get A). If
exactly one glyph is selected but the clipboard contains more that one
glyph, the selection will be extended so that enough glyphs are selected
that something may be pasted in each.
-->
フォントビューではこのコマンドはクリップボードにある物を種類を問わず、
選択中の各グリフの前面に貼り付け
(例外: クリップボードに画像が含まれる場合は、
その画像は通常前面には貼り付けられません)、
元からあった物を消去します。
クリップボード内の情報よりも選択中のグリフの方が多い場合、
選択中のすべてのグリフにペーストが行われるまでデータを繰り返し使用します
(例えば、グリフ A と B を選択してコピーを行い、C, D, E を選択して貼り付けを行った場合、
C には A が、D には B がコピーされ、E にも A が再びコピーされます)。

<!--
If the clipboard contains outline information then that information
will go into the glyph outline regardless of the setting of Copy From.
If the clipboard contains a bitmap and the display is set to outline
then the bitmap is pasted into the bitmap font it was copied from (ie.
the one with the same pixel size), if the clipboard contains a bitmap
and the display is set to a bitmap then the bitmap will be pasted into
the currently displayed font. If the clipboard contains a bitmap of a
size which does not exist in our database, then you will be asked if you
want to create a bitmap font to put the bitmap into.
-->
クリップボードにアウトライン情報が含まれている場合、
その情報は
<span class="command">コピー元の指定(F)</span>
による設定にかかわらずグリフアウトラインに貼り付けられます。
クリップボードにビットマップが含まれていてビューがアウトライン表示になっている場合、
ビットマップはそのコピー元である
(すなわち、元と同じピクセルサイズの)
ビットマップフォントに貼り付けられます。
クリップボードにビットマップが含まれていてビューがビットマップ表示になっている場合、
ビットマップは現在表示中のフォントにペーストされます。
フォントデータベースに存在しないサイズのビットマップがクリップボードに含まれている場合、
そのビットマップを新たに作成して貼り付けを行うかどうかを確認します。

<!--
In the Outline View this command will paste whatever is in the clipboard
to the current editing layer.
-->
アウトラインビューでは、このコマンドはクリップボードにあるものを現在編集中のレイヤーに貼り付けます。

<!--
In the Bitmap View this command will flatten any floating selection and
paste the contents of the clipboard into a new floating selection.
-->
ビットマップビューではこのコマンドは可動選択範囲を現在の場所に貼り付けて固定し、
新しく作った可動選択範囲にクリップボードの中身を貼り付けます。

<!--
If the clipboard is owned by an external application FontForge will
attempt to Paste the following selection types (the bitmap view does not
currently respond to external clipboards):
-->
クリップボードが外部のアプリケーションに占有されている場合、
FontForge は以下の選択型で貼り付けを行おうと試みます
(ビットマップビューは現在外部クリップボードに反応しません)。

<!--
    "image/png", "image/bmp"                background images
    "image/eps", "image/ps", "image/svg"    as spline data
-->
    "image/png", "image/bmp"                背景画像
    "image/eps", "image/ps", "image/svg"    スプラインデータ


<!--
See the section on [selections](../../reference/selections/)
-->
セクション
[選択](../../reference/selections/)
を参照してください。


<!--
#### Paste Into
-->
#### 追加貼り付け

<!--
Only available in the fontview. Just like Paste, except it does not
clear the contents of the glyph before adding to it.
-->
フォントビューでのみ使用可能です。
<span class="command">貼り付け(P)</span>
と同じですが、
そのグリフに元からある内容を貼り付け前に消去しない点が異なります。


<!--
#### Paste After
-->
#### 隣に貼り付け

<!--
Only available in the fontview. Pastes the contents of the clipboard
into the selected glyph, shifts it over by the advance width, and then
adds the advance width of the glyph in the clip to this glyph.
Essentially this makes it easy to build up words. (If the font has
vertical metrics, then glyphs will be stacked vertically. If the glyph
is right to left then the clipboard will be added on the left).
-->
フォントビューでのみ使用可能です。
クリップボードの内容を選択されたグリフに貼り付けます。
このときまずそのグリフの送り幅だけずらしして貼り付けを行い、
貼り付けたグリフの送り幅だけずらして次の文字を貼り付けます。
本質的に、これは単語を組み立てるのを簡単に行えるようにします。
(フォントに縦書きメトリックが存在する場合、グリフは縦に積み重ねられます。
グリフが右から左へかかれる場合、クリップボードの内容は左向きに追加されます)。

<!--
This command is not present unless you modify configure-pfaedit.h
-->
現在このコマンドは、configure-pfaedit.h を変更しないと用意されていません。


<!--
#### Same Glyph As
-->
#### 同じ文字として設定(M)

<!--
Only available in the fontview. If the clipboard contains a single
reference to a glyph then applying this command makes all selected
encoding points refer to that same glyph. (For example the
non-breaking-space glyph (U+00A0) frequently uses the same glyph as the
space glyph. To accomplish this, select the space glyph, Copy Ref,
select the non-breaking-space glyph and Same Glyph As).
-->
フォントビューでのみ使用可能です。
クリップボードに文字への参照が 1 個だけ含まれているときにこのコマンドを適用すると、
選択中のすべての符号位置が同一のグリフを参照するようになります。
(例えば、ノンブレーキングスペース文字 (U+00A0) はスペース文字と同じグリフを使うことがしばしばあります。
これを実現するためには、スペース文字のグリフを選択し、
<span class="command">参照をコピー(O)</span>
を実行してからノンブレーキングスペース文字のグリフを選択して
<span class="command">同じ文字として設定(M)</span>
を実行します。)

<!--
Adobe suggests that you avoid this. Use a reference instead. In some
situations (I think pdf files is one) having one glyph with several
encodings causes problems (Acrobat uses the glyph to back-map through
the encoding to work out the unicode code point. But that will fail if a
glyph has two unicode code points associated with it).
-->
Adobe は、それを避けるように勧めています。
その代わりに参照を使ってください。
いくつかの情況 (PDF がその一例だと思われます) においては、
1 個のグリフが複数の文字符号を持っていると問題が起こります
(Acrobat は、Unicode コードポイントを算出するために、
グリフから符号位置への逆対応表を使用します。
しかし、あるグリフが 2 つの Unicode コードポイントを持っているとそれが失敗します)。


<!--
#### Clear
-->
#### クリア(L)

<!--
Similar to [Cut](#Cut) except it does not copy anything to the
clipboard.
-->
<span class="command">切り取り(T)</span>
と似ていますが、何もクリップボードにコピーしない点が異なります。


<!--
#### Clear Background
-->
#### 背景をクリア(B)

<!--
Only in the font view. This command clears the backgrounds of all
selected glyphs.
-->
フォントビューでのみ使用可能です。
このコマンドは選択されたすべてのグリフの背景を消去します。


<!--
#### Merge
-->
#### 合併(M)

<!--
This command is only available in the Outline View. If a point on a path
is selected, the merge command will remove that point from the path and
join the two points around the removed one with a new spline which
approximates the curve between the two before. The two surrounding
points will retain their slopes (unless both are corner points).
-->
このコマンドはアウトラインビューでのみ使用可能です。
パス上の 1 点が選択されているとき、
<span class="command">合併(M)</span>
コマンドはパスからその点を削除して、
削除された点の両隣にある点の間に、
今まで存在した 2 本の曲線を近似するような
1 本のスプラインを描きます。
周囲の2つのポイントは傾きを保持します
(両方がコーナーポイントでない場合)。

<!--
[How is this done?](../pfaeditmath/#Approximating)
-->
[どうやって処理しているのか?](../pfaeditmath/#Approximating)


<!--
#### Join
-->
#### 線の接合(J)

<!--
This command is not available in the bitmap view. It looks for any paths
with endpoints as the endpoints of other paths and then join those two
paths. Also if the endpoint of a path is the same as the start point it
will make that path into a loop. (The commands that move points around
will normally do this automatically, but Paste will not).
-->
このコマンドはビットマップビューでは使用できません。
このコマンドは、端点の上に他の端点が重なっているようなパスを探し、
それら 2 つをつなぎ合わせます。
同時に、あるパスの端点がそのパスの始点と同じ場所にあるならば、
そのパスをループに変換します
(点を移動するコマンドはこれを自動的に行いますが、
<span class="command">貼り付け(P)</span>
は行いません)。

<!--
In the Outline view things are slightly more complicated: If any paths
have selected points on them it will only attempt to join those paths.
-->
アウトラインビューでは事情はもう少し複雑です: 選択された点を含むパス以外は処理の対象にしません。


<!--
#### Copy Fg To Bg
-->
#### 背景にコピー(F)

<!--
This command is only available in the Outline and Font Views. It cleans
out all the splines in the background layer and replaces them with a
copy of all the splines in the foreground layer. Note: Any background
images remain.
-->
このコマンドはアウトラインビューとフォントビューでのみ使用可能です。
背景レイヤーのすべてのスプラインを削除し、
前面レイヤーのスプラインをすべてコピーしたものに置き換えます。
注意: すべての背景画像は残ります。参照はコピーされません。


#### Copy Layer To Layer

<!--
This command is only available in the Outline and Font Views. It brings
up a dialog which lets you select a base layer to copy from and another
layer to copy to. You may also choose to clear the destination layer, or
to append to it. Then it copies the contents of the source layer
(contours and references, but not images) to the destination layer.
-->
このコマンドは、アウトラインビューとフォントビューでのみ使用できます。
コピー元のレイヤーとコピー先のレイヤーを選択できるダイアログが表示されます。
宛先レイヤーをクリアするか、追加することもできます。
次に、ソースレイヤーのコンテンツ (画像ではなく輪郭と参照) を宛先レイヤーにコピーします。


<!--
#### Select
-->
#### 選択(S)

<!--
In the outline view there is a select menu, other views just have Select
All.
-->
アウトラインビューでは
<span class="command">選択(S)</span>
メニューが表示されています。
その他のビューでは
<span class="command">すべて選択(A)</span>
だけが表示されます。


<!--
##### Select All
-->
##### すべて選択(A)

<!--
In the outline view it selects all points, all references (all images if
the background is active) and the width line (and the vertical width
line if that is enabled). In the fontview it selects all glyphs. In the
bitmap view it selects the current bitmap region.
-->
アウトラインビューでは、これはすべての点、
すべての参照 (背景がアクティブな場合、すべての画像)
およびグリフ幅の線 (縦書きが使用可能な場合は縦書き用の幅の線) を選択します。
フォントビューではすべてのグリフを選択します。
ビットマップビューでは現在のビットマップ範囲を選択します。


<!--
##### Invert Selection
-->
##### 選択範囲を反転(I)

<!--
Selects anything not selected, and deselects everything selected.
-->
選択されていないすべての物を選択し、選択中の物をすべて選択解除します。


<!--
##### Deselect All
-->
##### すべて選択解除(D)

<!--
Deselects anything selected
-->
選択中の内容をすべて選択解除します。


<!--
##### First Point
-->
##### 最初の端点(F)

<!--
Deselects everything and then selects the first point on the first path
of the glyph.
-->
すべてを選択解除してから、グリフ中の最初のパスの最初の点を選択します。


<!--
##### First Point, Next Contour
-->
##### 次の輪郭の最初の点(O)

<!--
Deselects everything and then selects the first point on the next
contour. (If the last contour is selected then deselects everything).
-->
すべてを選択解除してから、次の輪郭の最初の点を選択します
(最後の輪郭が選択されている場合、すべてを選択解除します)。


<!--
##### Next Point
-->
##### 次の端点(N)

<!--
Deselects the current point and selects the next point.
-->
現在の点を選択解除して、次の点を選択します。


<!--
##### Prev Point
-->
##### 前の端点(P)

<!--
Deselects the current point and selects the previous point
-->
現在の点を選択解除して、前の点を選択します。


<!--
##### Next Control Point
-->
##### 次の制御点(X)

<!--
Selects the "Next Control Point" of the current point.
-->
現在の点の "次の制御点" を選択します。


<!--
##### Prev Control Point
-->
##### 前の制御点(R)

<!--
Selects the "Prev Control Point" of the current point.
-->
現在の点の "前の制御点" を選択します。


<!--
##### Point At
-->
##### 位置を指定して選択(T)

<!--
Allows the user to enter an X,Y coordinate and selects the point at that
location.
-->
X 座標と Y 座標を入力して、その位置にある点を選択する事ができます。


<!--
##### Points on Selected Contours
-->
##### 輪郭全体(C)

<!--
If a contour contains any selected points, then select all points on the
contour.
-->
選択中の点を 1 個でも含んでいる輪郭の全体を選択します。


<!--
##### Select All Points & Refs
-->
##### すべての点と参照を選択(P)

<!--
Just like select all, but it doesn't select anchor points or the width
lines.
-->
<span class="command">すべて選択(A)</span>
とほぼ同じですが、アンカーポイントや幅表示の線は選択しません。


<!--
##### Select Anchors
-->
##### アンカーを選択(C)

<!--
Select all the Anchor points in the glyph.
-->
グリフ内の全アンカーポイントを選択します。


<!--
##### (De)Select Width
-->
#### 幅を(選択解除)(W)

<!--
Toggles whether the width line is selected.
-->
文字幅を表す線を選択するかしないかを切り替えます。


<!--
##### (De)Select VWidth
-->
##### 高さ(を選択解除)(V)

<!--
(if vertical metrics are enabled) Toggles whether the vertical width
line is selected.
-->
(縦書きメトリックが有効になっている場合)
縦書きの送り幅を表す線を選択するかしないかを切り替えます。


<!--
##### Select Points Affected by Current HintMask
-->
##### ヒントマスクが作用する点を選択

<!--
If a single point with a hintmask is selected, then this command selects
all points affected by that hintmask.
-->
ヒントマスクを伴う点が 1 個選択されている場合、このコマンドはそのヒントマスクが作用するすべての点を選択します。


<!--
##### Select by Color
-->
##### 色で選択(S)

<!--
Only in the font view. Displays a submenu containing a list of colors
and allows you to select all glyphs which you have set to that color
with the Char Info dlg. Normally the selection is cleared before setting
the colored glyphs, but if you hold down the shift key the selection
will be extended to the colored glyphs.
-->
フォントビューでのみ使用可能です。
色の一覧を含むサブメニューが表示され、
そこで色を選ぶと、
グリフ情報ダイアログであらかじめ設定した色がそれに等しいすべてのグリフを選択することができます。
通常は、
色の指定されたグリフを選択する前に選択していたグリフは選択解除されますが、
Shift キーを押しながら選択を行うことによって、
色で指定したグリフを今までの選択内容に追加選択することができます。


##### Select by Wildcard...

<!--
Select all glyphs that match the wildcard pattern specified. A glyph may
also be mapped to more than one encoding slot. Select all encoding slots
that refer to the named glyph. I think this is primarily useful for
detaching .notdef.
-->
指定したワイルドカードパターンに一致するすべてのグリフを選択します。
グリフは、複数のエンコードスロットにマップすることもできます。
名前付きグリフを参照するすべてのエンコードスロットを選択します。
これは主に、.notdef を切り離すのに役立つのではないかと思います。


##### Select by Script...

<!--
Allows you to specify an OpenType script tag and then ff will select all
glyphs which have that script.
-->
OpenType スクリプトタグを指定すると、
FontForge はそのスクリプトを持つすべてのグリフを選択します。

<!--
In the fontview, the following menu items will have slightly different
meanings depending on whether you are holding down the Shift of Control
keys.
-->
フォントビューでは、次のメニュー項目の意味は、
Shift キーを押しながら Control キーを押しているかどうかによってわずかに異なります。

<!--
If you hold down neither, then the current selection is cleared, and the
selection is set to whatever the command specifies.
-->
どちらも押さない場合、現在の選択はクリアされ、
コマンドが指定するものに選択が設定されます。

<!--
If you hold down just the Shift key, then the current selection is
retained and any glyphs specified by the command will be merged into
that selection. (a logical or operation)
-->
Shift キーだけを押したままにすると、
現在の選択が保持され、
コマンドで指定されたすべてのグリフがその選択にマージされます。
(論理和 OR 作用)

<!--
If you hold down just the Control key, then any glyphs specified by the
command will be removed from the selection.
-->
Control キーだけを押したままにすると、
コマンドで指定されたすべてのグリフが選択から削除されます。

<!--
If you hold down both keys, then only glyphs specified in both the
command and the old selection will be selected. (a logical and
operation)
-->
両方のキーを押したままにすると、
コマンドと古い選択の両方で指定されたグリフのみが選択されます。 
(論理積 AND 作用)


##### Glyphs worth outputting

<!--
Generally this means that either the glyph's width has been set, or that
in one of its foreground layers there is some data -- a contour or a
reference.
-->
通常、これは、グリフの幅が設定されているか、
その前景レイヤーの1つに何らかのデータ (輪郭または参照) があることを意味します。


##### with only references

<!--
Select all glyphs which contain at least one reference (in the active
layer) and no contours.
-->
(アクティブなレイヤー内で) 少なくとも1つの参照を持ち、輪郭を持たないすべてのグリフを選択します。


##### Glyphs with only Splines

<!--
Select all glyphs which contain at least one contour (in the active
layer) and no references.
-->
(アクティブなレイヤー内で) 少なくとも1つの輪郭を持ち、参照を持たないすべてのグリフを選択します。


##### Glyphs with both

<!--
Select all glyphs in the active layer with both contours and references.
This is something which cannot be expressed in a TrueType font, and
fontforge has various tricks for dealing with it, but it might be
something you'd like to fix up.
-->
輪郭と参照の両方をアクティブなレイヤー内に持つすべてのグリフを選択します。
これは TrueType フォントでは表現できないものであり、
FontForge にはそれを処理するためのさまざまなトリックがありますが、
そのようなものを修正したい場合があるかもしれません。


##### Whitespace Glyphs

<!--
Select all glyphs which contain neither references nor contours (but
which have had their widths set).
-->
参照も輪郭も含まない
(しかし幅は設定されている)
すべてのグリフを選択します。


<!--
##### Changed
-->
##### 変更されたグリフ(C)

<!--
Selects all changed glyphs
-->
変更されたグリフをすべて選択します。


<!--
##### Hinting Needed
-->
##### ヒントづけが必要なグリフ(H)

<!--
Selects all glyphs which FontForge thinks need to be hinted.
-->
ヒントづけが必要だと FontForge が判断したすべてのグリフを選択します。


##### Autohintable

<!--
Selects all glyphs which FontForge thinks can be autohinted -- ie. all
glyphs not marked [Hints-\>Don't Autohint](../hintsmenu/#Don.t.AutoHint)
(this does not check whether ff thinks the glyphs in question NEED to be
autohinted)
-->
FontForge が自動ヒント付けできると考えるすべてのグリフを選択します
-- つまり、
[<span class="command">ヒント->自動ヒント付けしない</span>](../hintsmenu/#Don.t.AutoHint)
でマークされていないすべてのグリフです
(この機能は FontForge が問題のグリフを自動ヒント付けする「必要がある」と考えているかどうかをチェックしません）。

##### Select By Lookup Subtable...

<!--
Only in the font view. Brings up a [dlg](../selectbyatt/) which allows
you to select various glyphs depending on various advanced typographic
features.
-->
フォントビューでのみ使用可能です。
さまざまな拡張タイポグラフィック機能に依存するさまざまなグリフを選択するための
[ダイアログ](../selectbyatt/)
を起動します。

<!--
#### Find / Replace
-->
#### 検索 / 置換(I)

<!--
Only in the font view, this brings up a [dialog](../search/) that
allows you to find patterns within glyphs and replace them with other
patterns.
-->
フォントビューでのみ使用可能です。
これはグリフ内のパターンを検索し、
他のパターンで置換するための
[ダイアログ](../search/)
を起動します。

<!--
#### Replace With Reference
-->
#### 参照に置換

<!--
Only in the font view, this command will search the font finding any
glyph which contains an inline copy of one of the selected glyphs, and
converts that copy into a reference to the appropriate glyph. In other
words it finds things which should be references and makes them be.
-->
フォントビューでのみ使用可能です。
このコマンドは選択されたグリフのどれかの複製をアウトラインの中に含んでいるグリフをすべて検索し、
その複製部分を適切なグリフへの参照に変換します。
言い替えれば、参照にするべき物を検索し、そうするということです。

<!--
This is primarily for use after reading a postscript (type1, otf or cff)
font. The reference information will usually be lost in these formats,
and this command can find it again.
-->
このコマンドは主に、
PostScript (Type1, OTF または CFF) フォントを読み込んだ後に使用します。
これらのフォーマットでは参照情報は一般に失われますが、
このコマンドを使用するとそれを再発見することができます。

<!--
Suppose the font contains a glyph "Acircumflex" which contains an
embedded copy of "A" (a copy of the contours, not a references), then if
you select "A" and apply this command it will search all glyphs in the
font for something that looks like "A", remove it from any glyphs in
which it is found and replace it with a reference. It applies this same
algorithm for all selected glyphs. If you want to check for every
possibility, just select all glyphs first.
-->
グリフ "Acircumflex" に
"A" のアウトラインのコピー (輪郭のコピーであって、参照ではない) が埋め込まれているフォントを考えましょう。
そこで "A" を選択してこのコマンドを適用すると、
フォント内のすべてのグリフを検索して "A" に見えるものを検索し、
それが見つかったすべての文字からそれを削除して、
参照に置き換えます。
同じアルゴリズムを選択されたすべての文字に対して適用します。
すべての可能性をチェックしたい場合は、
最初にすべてのグリフをコピーするだけでチェック可能です。

<!--
After completion, the selection will be set to those glyphs which have
been changed by the command.
-->
これが終了した後、コマンドの実行で変更されたすべてのグリフが選択されている状態となります。


<!--
#### Unlink Reference
-->
#### 参照を解除(N)

<!--
This will remove a referenced glyph and replace it with the splines and
points (or bitmap raster) that make it up.
-->
参照されたグリフを削除し、それを構成するスプラインと点に置き換えます。


<!--
#### Copy From
-->
#### コピー元の指定(F)

<!--
Only available in the Font View.
-->
フォントビューでのみ使用可能です。


<!--
##### All Fonts
-->
##### すべてのフォント(A)

<!--
If this is set then Copy (and Cut and Clear) will copy from the outline
font and from all the bitmap fonts
-->
これが設定されていると、
<span class="command">コピー(C)</span>
(および
<span class="command">切り取り(T)</span>
と
<span class="command">クリア(L)</span>)
の時にアウトラインフォントとすべてのビットマップからコピーを行います。


<!--
##### Displayed Font
-->
##### 表示されているフォント(D)

<!--
If this is set then Copy will only copy from the font currently being
displayed.
-->
これが設定されていると、
<span class="command">コピー(C)</span>
は現在選択されているフォントからのみ行われます。


<!--
##### Char Metadata
-->
##### グリフのメタデータ(M)

<!--
Normally [Copy](#Copy) does not copy the metadata (name, unicode encoding,
comment, ligature info) associated with a glyph, but if this is checked
then it will.
-->
一般には
<span class="command">コピー(C)</span>
ではグリフに付随するメタデータ
(名前、Unicode のエンコーディング、コメント、合字情報)
はコピーされませんが、
これがチェックされているとそれらもコピーされます。


<!--
##### TrueType Instructions
-->
##### TrueType 命令

<!--
Controls whether truetype instructions should be copied with a glyph. If
copying glyphs from one font to another it may not be appropriate to
copy the truetype instructions (which may depend on subroutines or
values in the 'fpgm', 'prep' and 'cvt ' tables).
-->
これは TrueType 命令をグリフと一緒にコピーするかどうかを制御します。
あるフォントから他のフォントへのグリフのコピーを行う場合には、
(サブルーチンや 'fpgm', 'prep' および 'cvt' テーブル内の値に依存する可能性がある)
TrueType 命令をコピーするのは適切ではないでしょう。

<!--
This also controls the behavior of the
[Transform](../elementmenu/#Transform...) and [Build
Accented](../elementmenu/#Build.Accented.Composite.Glyph) glyph commands.
-->
この設定は、
[<span class="command">変形(T)</span>](../elementmenu/#Transform...)
および
[<span class="command">アクセントつきグリフを構築(B)</span>](../elementmenu/#Build.Accented.Composite.Glyph)
コマンドのふるまいにも影響します。


<!--
#### Remove Undoes
-->
#### アンドゥ履歴をクリア

<!--
Not available in the Metrics View. This allows you to free up some of
the memory FontForge is currently squandering on keeping track of Undoes
(and Redoes). Obviously this command cannot be undone.
-->
メトリックビューでは実行できません。
これを使用すると FontForge が編集操作の取り消し
(および再実行)
に使う履歴情報に浪費しているメモリをほぼ解放します。
当然のことながら、この操作は取り消し不可能です。

<!--
-   In the Outline Glyph view this will free up all undoes/redoes in the
    current edit mode
-   In the Bitmap Glyph view this will free up all bitmap undoes/redoes
-   In the Font View this will free up all undoes/redoes in all selected
    glyphs, outline and bitmap, background and foreground.
-->
-   アウトライングリフビューで実行すると、
    現在の編集モード内で行われた操作の取り消し/再実行に必要なすべての記憶領域を解放します。
-   ビットマップグリフビューで実行すると、
    ビットマップ編集操作の取り消し/再実行に必要なすべての記憶領域を解放します。
-   フォントビューで実行すると、
    選択中のすべてのグリフのアウトライン・ビットマップ・背景および前面の編集取り消し/再実行に必要なすべての記憶領域を解放します。
