---
published: true
layout: default.ja
title: 表示メニュー
---
<!--
published: true
layout: default
title: The View Menu
-->


[table_of_contents]


<!--
#### Fit
-->
#### 枠に揃える(F) (Fit)

<!--
In the outline and bitmap views this will scale the current glyph to the
largest setting where it all fits in the view.
-->
アウトラインビューとビットマップビューでは、
このコマンドは現在のグリフがすべてビューに収まるような最大の設定に拡大・縮小します。


<!--
#### Zoom Out
-->
#### 縮小(O) (Zoom Out)

<!--
Not in the font view. Centered on the middle selection if there is one,
else the middle of the view.
-->
フォントビューでは使用できません。
選択範囲があればそこが中心に、なければ現在のビューの中心がそのまま中心になります。


<!--
#### Zoom In
-->
#### 拡大(I) (Zoom In)

<!--
Not in the font view. Centered on the middle selection if there is one,
else the middle of the view.
-->
フォントビューでは使用できません。
選択範囲があればそこが中心に、なければ現在のビューの中心がそのまま中心になります。


<!--
#### Next Glyph
-->
#### 次のグリフ(N) (Next Glyph)

<!--
In the metrics, outline and bitmap view this changes the current glyph
to be the next one in the font.
-->
メトリックビュー、アウトラインビューとビットマップビューでは、
現在グリフをフォント内の次のグリフに変更します。

<!--
In the font view this selects the next glyph in the font (and scrolls,
if necessary, to display that glyph).
-->
フォントビューでは、フォント内の次のグリフを選択します
(必要に応じて、次のグリフを表示するために画面をスクロールします)。


<!--
#### Prev Glyph
-->
#### 前のグリフ(P) (Prev Glyph)

<!--
In the metrics, outline and bitmap view this changes the current glyph
to be the previous one in the font.
-->
メトリックビュー、アウトラインビューとビットマップビューでは現在グリフをフォント内の前のグリフに変更します。

<!--
In the font view this selects the next glyph in the font (and scrolls,
if necessary, to display that glyph).
-->
フォントビューでは、フォント内の前のグリフを選択します
(必要に応じて、前のグリフを表示するために画面をスクロールします)。


<!--
#### Next Defined Glyph
-->
#### 次の定義済みグリフ(D) (Next Defined Glyph)

<!--
Similar to Next Glyph, except it moves to the next glyph defined in the
font.
-->
<span class="command">次のグリフ(N)</span>
と同様ですが、フォント内の次の定義済みグリフに移動する点が異なります。


<!--
#### Prev Defined Glyph
-->
#### 前の定義済みグリフ(A) (Prev Defined Glyph)

<!--
Similar to Prev Glyph, except it moves to the previous glyph defined in
the font.
-->
<span class="command">前のグリフ(P)</span>
と同様ですが、フォント内の前の定義済みグリフに移動する点が異なります。


<!--
#### Former Glyph
-->
#### 前に編集したグリフ(E) (Former Glyph)

<!--
Changes the glyph window to look at whatever glyph was being edited
there before this one (one level of history).
-->
現在の文字よりも 1 つ前に何らかの編集を行った (編集履歴で 1 段階前の) グリフを探して、
グリフウィンドウを更新します。


<!--
#### Substitutions
-->
#### 置換一覧(S) (Substitutions)

<!--
Brings up a sub menu showing all the GSUB type 1 and type 3
substitutions (simple and alternate) you have defined for the selected
glyph and allows you to change the glyph as directed by the
substitution. Also contains an entry to return you to the original
glyph.
-->
(訳注: メトリックビューのみ)<br>
選択中のグリフに対して定義されている
GSUB のタイプ 1 と 3 の置換 (単純置換と選択型置換) のすべてを表示するサブメニューを表示し、
置換先のグリフを編集することができます。
オリジナルのグリフに戻るための項目も表示されています。

<!--
Substitutions may be set with the [Element-\>Glyph Info](../charinfo/)
command.
-->
置換の設定は
[<span class="command">エレメント(L)->グリフ情報(I)</span>](../charinfo/)
コマンドで行うことができます。


<!--
#### Goto / Replace Glyph...
-->
#### 移動(G) / グリフを入れ換える(R)... (Goto / Replace Glyph...)

<!--
In the Font, Outline, Bitmap and Metrics views this brings up a dialog
in which you may type either:
-->
フォントビュー、アウトラインビュー、ビットマップビューとメトリックビューでは、
以下の好きな書式でキー入力できるダイアログを表示します。

<!--
-   A name of a glyph in the current font
-   A number (in either decimal or hex) indicating the glyph you are
    interested in, in the current encoding
-   A hex number ,preceded by "U+" or "uni" or "u", indicating the
    character you are interested in in unicode.
-   A decimal number, preceded by "glyph" ,indicating the glyph index in
    the original glyph list.
-   A ku ten representation of a CJK font (two comma separated numbers)
-   A standard name (which need not be used in the current font) but
    which can be mapped to a unicode value.
-   For 2/4 byte encodings you will also be shown a pull-down list of
    unicode ranges (Things like "Greek", "Katakana", "Hangul
    Compatibility Jamo") and you can select one of the range names.
-   Arabic letters may also be named as: `afii57442.isolated `or
    `0x642.initial`
-   A single unicode character
-->
-   現在のフォントに含まれるグリフの名前
-   現在の符号化方式で、注目しているグリフのコードを示す (10 進または 16 進の) 数値
-   "U+" または "uni" または "u" の後ろに 16 進数を続けたもの。
    対象とする文字の Unicode でのコードを表します。
-   "glyph" の後ろに 10 進数。元のグリフリスト内のグリフインデックスを示します。
-   CJK フォントの区点番号 (カンマで区切られた 2 個の数値)
-   Unicode 値に対応づけることができる標準の名称 (現在のフォントで使用されていなければなりません)。
-   2 バイトまたは 4 バイトのエンコーディングに対しては、
    Unicode の範囲を表すプルダウンリスト
    ("Greek", "Katakana", "Hangul Compatibility Jamo" など)
    が表示され、それらの範囲名から 1 個を選択することができます。
-   アラビア文字は `afii57442.isolated` や `0x642.initial` のように指定することができます。
-   Unicode の文字 1 文字

<!--
In the font view the view will scroll so that this glyph is visible and
it will be selected
-->
フォントビューでは、そのグリフが見える所までビューがスクロールして、選択された状態になります。

<!--
In the bitmap, outline and metrics views, the current glyph will change
to be the one specified.
-->
ビットマップビュー、アウトラインビューとメトリックビューでは、現在のグリフが指定したグリフに変更されます。


<!--
#### Insert Glyph Before... / Insert Glyph After...
-->
#### 現在位置の前に挿入(B)... / 現在位置の後に挿入(C)... (Insert Glyph Before... / Insert Glyph After...)

<!--
In the metrics view this brings up a dialog similar to the previous one
allowing you to enter a glyph by name or encoding either before or after
the currently selected position.
-->
メトリックビューでは、上記のダイアログによく似たダイアログをこれで起動して、
現在選択中の位置の前か後ろに挿入するグリフをグリフ名やコードで指定できます。


<!--
#### Layers
-->
#### レイヤ (Layers)

<!--
A submenu which only appears in the font view. It lets you chose which
layer to display in the font view.
-->
フォントビューでのみ表示されます。
フォントビューで表示レイヤを選択できます。

<!--
#### Find In Font View
-->
#### フォント表示から探す(V) (Find In Font View)

<!--
In the outline, bitmap and metrics views this will scroll the associated
font view so that the current glyph is displayed (and selected) in the
fontview.
-->
アウトラインビュー、ビットマップビューとメトリックビューでは、対応するフォントビューをスクロールして、
現在のグリフがフォントビュー内に表示されるように移動します (そして選択します)。


<!--
#### Show ATT
-->
#### ATTを表示(S) (Show ATT)

<!--
Only in the font view. Brings up a [dlg](../showatt/) showing the
advanced typographic tables (GPOS/GSUB or morx/kern) that FontForge
supports.
-->
フォントビューでのみ使用可能です。
FontForge がサポートする高度な組版機能に関するテーブル
(GPOS/GSUB または morx/kern)
を表示する
[ダイアログ](../showatt/)
を起動します。


<!--
#### Display Substitutions
-->
#### 置換グリフを表示(U)... (Display Substitutions)

<!--
Only in the font view. This allows you to select a simple substitution,
any glyph with that substitution attached will be displayed as the
substituted glyph. Any glyph without such a substitution will be left
blank. Double clicking on a glyph will either go the substituted version
or will create a substituted version and go to that. (However almost no
other commands will be aware of this mapping, which will probably be
confusing).
-->
フォントビューでのみ使用可能です。
このコマンドでは単純置換を選択することができ、
その置換を各グリフに適用した結果が、
置換されたグリフの位置に表示されます。
そのような置換が存在しないグリフは空白のままで残ります。
そのグリフ上でダブルクリックすると、
置換結果のバージョンがあればそれを開き、
無ければ新しく作成した置換結果のグリフを開きます。
(しかしながら、混乱の元になりそうなので、他のほとんどのコマンドはこの対応づけに関知しません)。

<!--
-> `Displaying small caps ('smcp' substitution)`  
![](/assets/img/filemenu-fv-normal.png)
![](/assets/img/filemenu-fv-smallcaps.png) <-
-->
スモールキャップスの表示 ('smcp' による置換)
![](/assets/img/filemenu-fv-normal.png)
![](/assets/img/filemenu-fv-smallcaps.png)


<!--
#### Combinations
-->
#### 複合グリフを表示(B) (Combinations)

<!--
A submenu containing
-->
以下のサブメニューを含みます。

<!--
##### Kern Pairs
-->
##### カーニングペア(K) (Kern Pairs)

<!--
This [brings up a dialog showing all kerning pairs](../kernpairs/) in
the current font (or, if invoked from the outline glyph view, a list of
all kerning pairs involving that glyph). You may alter kerning pairs
here too.
-->
このコマンドは現在のフォントに含まれる
[全てのカーニングペアを表示するダイアログ](../kernpairs/)
を起動します。
(または、アウトライングリフビューから起動した場合は、
そのグリフに関連する全てのカーニングペアのリストを表示します)。
カーニングペアをそこで改変することもできます。

<!--
##### Anchored Pairs
-->
##### アンカーつきペア(A) (Anchored Pairs)

<!--
This may have a sub-menu of its own containing all the anchor classes
for this font and an entry "All". You may choose to see all combinations
of glyphs from a given anchor class, or all combinations from all
anchored classes.
-->
ここには、このフォントが含んでいる全てのアンカークラスおよび項目
"All" からなるサブメニューが含まれるはずです。
特定のアンカークラスに含まれるすべてのグリフの組合せを見るか、
すべてのアンカークラスに含まれるすべての組合せを見ることができます。

<!--
If invoked from the outline glyph view it will provide a list of all
anchored combinations involving that glyph.
 Selecting a combination and double clicking on it will bring up an
[Anchor Control](../anchorcontrol/) dialog.
-->
アウトライングリフビューから呼び出したときは、
そのグリフに関するすべてのアンカーつき組合せを表示します。<br>
 組合せを選択し、その上でダブルクリックすると
[アンカーの制御](../anchorcontrol/)
ダイアログが起動します。

<!--
##### Anchor Control
-->
##### アンカーの制御 (Anchor Control)

<!--
Only in the outline view. Has a submenu of all anchor points in this
glyph. Selecting one brings upt the [Anchor Control](../anchorcontrol/)
dialog.
-->
アウトラインビューでのみ使用できます。
このグリフ内のすべてのアンカーポイントのサブメニューがあります。
そのうちの 1 つを選択すると
[アンカーの制御](../anchorcontrol/)
ダイアログが起動します。

<!--
##### Anchor Glyph at Point
-->
##### ポイントのアンカーグリフ (Anchor Glyph at Point)

<!--
Only in the outline view. Allows you to attach and display another glyph
at the selected anchor point.
-->
アウトラインビューでのみ使用できます、
選択したアンカーポイントに別のグリフをアタッチして表示できます。

<!--
##### Ligatures
-->
##### 合字(L) (Ligatures)

<!--
This brings up a dialog showing the names of all ligatures and of the
glyphs that compose them (if invoked from the outline glyph view, a list
of all ligatures containing that glyph). Double clicking on an entry
will bring up a window showing that ligature.
-->
このコマンドは、すべての合字とそれらを構成するグリフの名前を表示するダイアログを起動します
(アウトライングリフビューから呼び出したときは、そのグリフを含むすべての合字のリストを表示します)。
表示された項目の上でクリックすると、その合字を表示するウィンドウを起動します。

<!--
#### Label Glyph By
-->
#### グリフへのラベルづけ(L) (Label Glyph By)

<!--
In the font view each glyph has a label above it. This may be either:
-->
フォントビューでは、各グリフの上にはラベルが表示されています。
それは以下のいずれかです:

<!--
-   An image of the glyph (from a conventional font)
-   The name of the glyph
-   The unicode code point associated with the glyph
-   The glyph's encoding (in hex)
-->
-   グリフの画像 (通常のフォントによる)
-   グリフの名前
-   そのグリフに割り当てられた Unicode のコードポイント
-   グリフの符号位置 (16 進数で)

<!--
Note that when the glyphs are small (the 24 pixel view, for example)
there may not be room for the entire name of each glyph (or even for the
encoding), so the labels may be truncated.
-->
グリフが小さいとき (例えば、24 ピクセル表示のとき)
各グリフの名前 (またはエンコーディングですら) を全部表示するだけの場所がないことに留意してください。
そのような場合には、ラベル表示は切り詰められるでしょう。


<!--
#### View H. Metrics...
-->
#### 横書きメトリックの表示法(H)... (View H. Metrics...)

<!--
In the font view this will control which of the horizontal metrics lines
are draw across the displayed glyphs. In the outline glyph view the same
functionality is available from one of the palettes. [See the font view
for more information](../fontview/#metrics)
-->
フォントビューでは、このコマンドは横書きのメトリックを表す線をグリフ表示の上に重ねて表示するかどうかを切替えます。
アウトライングリフビューではこれと同じ機能がパレットの 1 つから使用できます。
より詳しい情報は
[フォントビュー](../fontview/#metrics)
を参照してください。


<!--
#### View V. Metrics...
-->
#### 縦書きメトリックの表示法(V)... (View V. Metrics...)

<!--
In the font view this will control which of the vertical metrics lines
are draw across the displayed glyphs. In the outline glyph view the same
functionality is available from one of the palettes. (This will be
greyed out if your font does not have vertical metrics in it). [See the
font view for more information](../fontview/#metrics)
-->
このコマンドはフォントビューでは、表示されているグリフ上に縦書きメトリックを表す 2 つの線のどちらを表示するかを制御します。
アウトライングリフビューではこれと同じ機能が利用できるボタンがパレットにあります
(縦書きメトリックが存在しないときはこれは灰色表示になっていて選択できません)。
より詳しい情報は
[フォントビュー](../fontview/#metrics)
を参照してください。


<!--
#### 32x8 cell window
-->
#### 32x8 マス表示 (32x8 cell window)

<!--
In the font view you may explicitly set the window size so that there
are 32 glyph cells horizontally and 8 vertically.
-->
フォントビューのグリフ表示枠が横 32 マス・縦 8 マスになるようにウィンドウサイズを直接指定できます。


<!--
#### 16x4 cell window
-->
#### 16x4 マス表示 (16x4 cell window)

<!--
In the font view you may explicitly set the window size so that there
are 16 glyph cells horizontally and 4 vertically.
-->
フォントビューのグリフ表示枠が横 16 マス・縦 4 マスになるようにウィンドウサイズを直接指定できます。


<!--
#### 8x2 cell window
-->
#### 8x2 マス表示 (8x2 cell window)

<!--
In the font view you may explicitly set the window size so that there
are 8 glyph cells horizontally and 2 vertically.
-->
フォントビューのグリフ表示枠が横 8 マス・縦 2 マスになるようにウィンドウサイズを直接指定できます。


<!--
#### 24 pixel outline
-->
#### 24 ピクセルアウトライン (24 pixel outline)

<!--
In the font view you may choose how large you want the rasterized
representation of the outline view to be. The default is to rasterize it
on a 24 pixel block. If this item is checked then a 24 pixel version of
the outline font is displayed, selecting it will display a 24 pixel
version of the font.
-->
フォントビューでは、アウトラインビューをラスタライズしたものをどの大きさで表示したいかを選択することができます。
デフォルトではグリフを 24 ピクセルのブロック上にラスタライズします。
この項目にチェックが入っているときには、アウトラインフォントの 24 ピクセル版が表示されています。
これを選択するとフォントを 24 ピクセルで表示します。

<!--
(Exactly one em-square of the glyph will be displayed, if the glyph
extends above the ascent or below the descent those features will be
clipped)
-->
(グリフの正確な 1 em 正方形が表示されます。
グリフがアセントの上やディセントの下にかかる場合は、それらの部分ははみ出てしまいます)。


<!--
#### 36 pixel outline
-->
#### 36 ピクセルアウトライン (36 pixel outline)

<!--
Similar to the above but for a 36 pixel version.
-->
上と同じですが 36 ピクセルで表示します。

<!--
#### 48 pixel outline
-->
#### 48 ピクセルアウトライン (48 pixel outline)

<!--
Similar to the above but for a 48 pixel version.
-->
上と同じですが 48 ピクセルで表示します。

<!--
#### 72 pixel outline
-->
#### 72 ピクセルアウトライン (72 pixel outline)

<!--
Similar to the above but for a 72 pixel version.
-->
上と同じですが 72 ピクセルで表示します。

<!--
#### 96 pixel outline
-->
#### 96 ピクセルアウトライン (96 pixel outline)

<!--
Similar to the above but for a 96 pixel version.
-->
上と同じですが 96 ピクセルで表示します。

<!--
#### AntiAlias
-->
#### アンチエイリアス(A) (AntiAlias)

<!--
Only in the font and metrics view. Toggles between whether the font
displayed in the view is a bitmapped font or an anti-aliased font. An
Anti-aliased font shows levels of grey rather than just black and white.
It often looks better than a bitmap, but it is slower to generate and
draw.
-->
フォントビューとメトリックビューでのみ使用可能です。
ビュー内に表示されるフォントがビットマップ表示かアンチエイリアス表示かを切り替えます。
アンチエイリアスフォント表示では、黒と白だけでなく灰色の階調で表示します。
多くの場合ビットマップより美しく見えますが、演算および描画処理により時間がかかります。

<!--
#### Vertical
-->
#### 縦書き(V) (Vertical)

<!--
Only in the metrics view. Toggles between displaying horizontal and
vertical metrics. (Only available if Element-\>Font Info-\>General-\>Has
Vertical Metrics is set).
-->
メトリックビューでのみ使用可能です。
横書き用と縦書き用のメトリックのどちらを表示するかを切り替えます。
(<span class="command">エレメント(L)-\>フォント情報(F)-\>一般-\>[]縦書きメトリックが存在</span>
がセットされている場合に限ります)。

<!--
#### Fit To Em
-->
#### 表示を全角に固定(F) (Fit To Em)

<!--
Only in the font view. The fontview will either display glyphs scaled so
that the font's bounding box fits in the window, or so that the em fits
in the window. The advantage of the first method is that you see all of
each glyph, the advantage of the second is that you can see how the
letter sizes compare from font to font.
-->
フォントビューでのみ使用可能です。
フォントビューでは、フォントのバウンディングボックスがウィンドウ内に収まるように縮小するか、
em がウィンドウに揃うようにするかのどちらかを選択できます。
最初の方法の利点は、各グリフの全体像を見ることができる点で、
2 番目の方法の利点はグリフのサイズをフォントごとに比較できる点です。

<!--
(This is something of a simplification. In bounding box mode the
displayed font is scaled so that the vertical size (as found in the
bounding box) fits it the window. Very wide glyphs will still not fit
horizontally. Also the scaling is not updated when glyphs change, if you
have changed the maximum bounds of the font you might want to force a
rescale by toggling this mode)
-->
(この説明は少し単純化しています。
バウンディングボックスモードでは表示されるフォントは、
垂直方向のサイズ (バウンディングボックスと同じ) がウィンドウにちょうど収まるように縮小されます。
それでも幅が非常に広いグリフは収まりません。
また、縮小率はグリフが変更されるたびに変化するわけではないので、
フォント内のグリフの最大境界を変更したときには、
このモードを切り替え直すことによって縮小をやり直す必要があるでしょう)

<!--
#### Bitmap Magnification...
-->
#### ビットマップの拡大... (Bitmap Magnification...)

<!--
In the font view. When displaying a bitmap font it is sometimes
desirable to look at the font with a greater magnification than normal.
-->
フォントビューでのみ使用できます。
ビットマップフォントを表示するとき、
通常よりも大きな倍率でフォントを見ることが望ましい場合があります。

<!--
#### \<list of bitmap pixel sizes, if any\>
-->
#### \<ビットマップがあれば、そのサイズのリスト\> (\<list of bitmap pixel sizes, if any\>)

<!--
In the font view or metrics view there is a list of all generated bitmap
fonts. You may select to have one of them displayed in the view rather
than a rasterized version of the outline font. If one is checked then
that one is currently displayed, if you select one then it will be
displayed.
-->
フォントビューとメトリックビューでは、生成されたビットマップフォントをすべて含むリストを表示します。
それらのビットマップのどれか一つを、アウトラインフォントをラスタライズしたものの代りに表示するように選択することができます。
どれかにチェックが入っているとき、そのチェックの入ったものが現在表示されることになります。

<!--
In CID keyed fonts this list will not be present.
-->
CID フォントではこのリストは存在しません。

<!--
If your font database includes some greymap fonts then these will be
listed here too, as usual they will be displayed as
\<pixel-size\>@\<bits-per-pixel\>
-->
フォントデータベースにグレイマップフォントが含まれている場合、
それらも普通のビットマップと一緒に、\<ピクセルサイズ\>@\<ピクセル毎のビット数\> の形で表示されます。


<!--
#### Show/Hide Grid
-->
#### グリッドを表示/隠す(G) (Show/Hide Grid)

<!--
In the Metrics View this entry allows you to turn on or off the lines
marking the edges of the glyphs on display. There are 4 levels
-->
メトリックビューではレイヤーパレットはありません。
画面上のグリフの境界を示す線を表示したり隠したりするのには、この項目を使うことができます。

<!--
-   Show Grid -- Always show the full grid lines
-   Partial Grid -- Show short lines at the top and bottom of the window
    so the line will not be distracting when examining spacing
-   Hide when moving -- Show the full grid line normally, but it will
    vanish while the user adjusts spacing with the mouse
-   Hode Grid -- Always hide the grid.
-->
-   グリッドを表示 -- 常にフルグリッドラインを表示します
-   部分グリッド -- ウィンドウの上下に短い線を表示して、間隔を調べるときに線が邪魔にならないようにします
-   移動時に非表示 -- 通常は完全なグリッド線を表示しますが、ユーザーがマウスで間隔を調整すると消えます
-   グリッドを非表示 -- グリッドを常に非表示にします


<!--
#### Outline
-->
#### アウトライン(O) (Outline)

<!--
In the Metrics View this will be checked when the outline font is bring
displayed. Selecting it will display the outline font (rather than a
bitmap font).
-->
メトリックビューでは、アウトラインフォントが表示されているときにはここにチェックがつけられます。
これを選択すると (ビットマップフォントではなく) アウトラインフォントを表示します。

<!--
#### Number Points
-->
#### 点番号を表示(N) (Number Points)

<!--
In the Outline view, this small sub-menu allows you to control whether
point numbers are displayed next to points in the foreground view. This
is primarily for TrueType, where the instructions use these numbers to
refer to the points when they do grid-fitting. The numbering scheme is a
little different depending on what the expected output (input) will be,
so we have a sub-menu listing output types.
-->
アウトラインビューでは、この小さなサブメニューを使って、
前面ビューの点のそばに点番号を表示するかしないかを切り替えることができます。
これは主に、グリッド合わせを行うときに命令が点を参照するのにこの番号を使用する
TrueType のために用意されたものです。
番号づけの方式は、どの出力 (入力) を予定しているかによっていくぶん異なるため、
表示タイプをリストするサブメニューを用意しています。


<!--
#### Show Grid Fit
-->
#### グリッド合わせを表示(W) (Show Grid Fit)


<!--
##### Show Grid Fit
-->
##### グリッド合わせを表示(W) (Show Grid Fit)

<!--
In the Outline view and only if the freetype library is available.
Brings up a [dialog](../charview/#GridFit) which allows you to control
whether a grid fit version of the splines in the font is displayed.
-->
アウトラインビューで、FreeType ライブラリが利用可能なときのみ使用可能です。
スプラインのグリッド合わせを行ったバージョンを表示するかどうかを決定する
[ダイアログ](../charview/#GridFit)
を表示します。


<!--
##### Bigger Point Size
-->
##### ポイントサイズ拡大 (Bigger Point Size)

<!--
In the Outline view, if grid fitting is turned on, this will increase
the point size (note, this is slightly different from increasing the
pixel size).
-->
アウトラインビューでは、グリッド合わせが有効になっている場合、
ポイントサイズを増加させします
(ピクセルサイズの増加とは少し違うことに注意してください)。


<!--
##### Smaller Point Size
-->
##### ポイントサイズ縮小 (Smaller Point Size)

<!--
In the Outline view, if grid fitting is turned on, this will decrease
the point size.
-->
アウトラインビューでは、グリッド合わせが有効になっている場合、
ポイントサイズを減少させます


<!--
##### Anti-Alias
-->
##### アンチエイリアス (Anti-Alias)

<!--
In the Outline view, if grid fitting is turned on, this will toggle
whethe the display is in anti alias mode.
-->
アウトラインビューでは、グリッド合わせが有効になっている場合、
アンチエイリアスモードでの表示を切り替えます。


<!--
##### Off
-->
##### オフ (Off)

<!--
Turns off grid fitting.
-->
グリッド合わせを無効にします。


<!--
#### Show
-->
#### 表示 (Show)

<!--
This submenu is only in the outline glyph view.
-->
このサブメニューは、アウトライングリフビューでのみ使用できます。


<!--
##### Points
-->
##### ポイント (Points)

<!--
This hides or displays the points in the outline glyph view.
-->
このコマンドは、アウトライングリフビューでの表示、非表示を切り替えます。

<!--
##### Show Control Point Info
-->
##### 制御点の情報を表示(C) (Show Control Point Info)

<!--
In the Outline view, when you move a [control
point](../charview/#CpInfo)this mode pops up a little window showing
various bits of information about the control point you are editing.
-->
アウトラインビューでこのモードを使用しているとき、
[制御点](../charview/#CpInfo)
を移動すると編集中の制御点に関する各種の細かい情報を表示する小さなポップアップウィンドウが表示されます。


<!--
##### Extrema
-->
##### 極大点を表示(M) (Extrema)

<!--
In the Outline view, in postscript and truetype
fonts (in almost all cases) should have their horizontal and vertical
extrema at the endpoints of splines. This setting will mark extremal
endpoints by coloring them a dull purple to remind you that you should
not delete them. If an extremum occurs somewhere other than an end point
a crosshair will be drawn around it. You might consider doing
[Element-\>Add Extrema](../elementmenu/#Add.Extrema) in this case (or
you might not, this can be ok in some cases).
-->
アウトラインビューでは、
PostScript フォントおよび TrueType フォントでは
(ほとんどの場合)
極大点にある水平または垂直になる点が端点でないようなスプラインが存在するべきではありません。
これを設定すると、
極大点にある端点を鈍い紫色で印づけ、
その点を削除してはならないことを思い出させます。
もし、極大値がどこか端点以外の場所に存在する場合、
その点を中心に十字線が描画されます。
この場合、
[<span class="command">エレメント(L)->端点を追加(A)</span>](../elementmenu/#Add.Extrema)
を実行することを検討すべきでしょう
(それは許される場合もあるので、検討は不要かもしれません)。

![](/assets/img/filemenu-extrema-poi.png)


<!--
##### Points of Inflection
-->
##### 変曲点を表示(M) (Points of Inflection)

<!--
In the Outline view, points of inflection occur where the change in the
slope of the curve (second derivative) changes sign. Quadratic splines
(truetype) cannot represent points of inflection. If you have a
postscript font which you intend to convert to truetype it can be
helpful to know where these difficult points lie. (the cubic-\>quadratic
approximation routines will often add intermediate points at these
points of inflection)
-->
アウトラインビューにおいて、変曲点は、曲線の傾きの変化率 (2 階微分) の符号が変わる箇所に発生します。
2 次スプライン (TrueType) は変曲点を表現することができません。
後で TrueType に変換するつもりで PostScript フォントを編集する場合には、
この難しい点がある場所を知ることが役に立つ可能性があります。
(3 次 -\> 2 次の近似ルーチンは、変曲点に中間点を加えることがよくあります)。


<!--
##### Almost Horizontal/Vertical Lines
-->
##### ほぼ水平/垂直な直線 (Almost Horizontal/Vertical Lines)

<!--
If a line is almost, but not quite horizontal or vertical then draw the
line in a different color to show visually that it should be fixed.
-->
直線がほぼ水平または垂直であるが、完全に水平、垂直でない場合、
線を異なる色で描いて、修正する必要があることを視覚的に示します。


<!--
##### Almost Horizontal/Vertical Curves
-->
##### ほぼ水平/垂直な曲線 (Almost Horizontal/Vertical Curves)

<!--
If a curve is almost, but not quite horizontal or vertical at one of its
endpoints then draw little tick marks at the end point to indicate this.
-->
曲線がほぼ水平または垂直であるが、その端点の1つで完全に水平、垂直でない場合、
これを示すために端点に小さな印を描画します。

<!--
##### (Define Almost)
-->
##### (「ほぼ」の定義) (Define Almost)

<!--
Define what "almost" means, as used in the above two commands.
-->
上記の 2 つのコマンドで使用されている "ほぼ" の意味を定義します。


<!--
##### Side Bearings
-->
##### サイドベアリング (Side Bearings)

<!--
Draws little lines to mark the left and right side bearings of a glyph.
-->
グリフの左右のサイドベアリングを示す小さな線を描きます。

<!--
##### Fill
-->
##### 塗りつぶし(L) (Fill)

<!--
In the Outline view this fills in the glyph outline as you edit it.
(this can be very slow. If the glyph is too big (too magnified) then
filling will not be done).
-->
アウトラインビューでは、これはグリフアウトラインを編集するたびに塗りつぶします。
(これは非常に遅くなることがあります。グリフが大きすぎる (拡大しすぎた) 場合、塗りつぶしは行われません)。

<!--
##### Preview
-->
##### プレビュー (Preview)

<!--
A preview mode hides points, hints, various other stuff and fills the outline
to give a better feel of the glyph's looks. Besides usual shortcut toggling it
on and off — **Ctrl+[*key above Tab*]** (eg, **Ctrl+\`** on a US keyboard)
— it can be also used by holding that **[*key above Tab*]** down (unless quick
navigation is enabled).
-->
プレビューモードは、ポイント、ヒント、その他のさまざまな要素を非表示にし、
アウトラインを塗りつぶして、グリフの外観をより良く感じられるようにします。
通常のショートカットのオン/オフ切り替えに加えて
-- **Ctrl+[*タブの上のキー*]** （たとえば、US キーボードの **Ctrl+\`**）
-- **[*タブの上のキー*]** を押したままにして使用することもできます
(クイックナビゲーションが有効でない場合)。


<!--
##### Palettes
-->
##### パレット(P) (Palettes)

<!--
###### Tools
-->
###### ツール(T) (Tools)

<!--
If this item is checked then the tools palette (in the outline and
bitmap views) is visible. Selecting it toggles whether the palette is
visible or not.
-->
この項目がチェックされていると、
(アウトラインビューとビットマップビューの) ツールパレットが表示された状態になります。
これを選択すると、パレットを見せるか消すかが切り替わります。

<!--
###### Layers
-->
###### レイヤー(L) (Layers)

<!--
If this item is checked then the layers palette (in the outline and
bitmap views) is visible. Selecting it toggles whether the palette is
visible or not.
-->
この項目がチェックされていると、(アウトラインビューとビットマップビューの) レイヤーパレットが表示された状態になります。
これを選択すると、パレットを見せるか消すかが切り替わります。

<!--
###### Shades
-->
###### 階調(S) (Shades)

<!--
Only in the bitmap view, and only if editing grey-scale (anti-aliased)
fonts. Controls whether the shades of grey palette is visible or not.
-->
ビットマップビューでのみ使用可能で、
グレイスケール (アンチエイリアス表示の) フォントを編集中のときのみ表示されます。
灰色の階調を表示するパレットを見せるようにするか否かを制御します。

<!--
###### Dock Palettes
-->
###### パレットを連結表示(D) (Dock Palettes)

<!--
Allows you to control whether you want the palettes free standing or
docked in the current view.
 The window manager under gnome does not handle this properly. If you
want docked palettes under gnome: Open a window with palettes, select
docked palettes (the palettes will not dock), close the window, reopen
the window. The palettes are now docked and should be from here on.
-->
パレットを独立のウィンドウとして表示するか、現在のビューに連結するかを選択することができます。<br>
 Gnome のウィンドウマネージャーこれを正しく扱うことができません。
Gnome で連結パレットを使用するには以下のようにしてください:
パレットつきのウィンドウを作成してから連結表示のパレットを選択し
(まだパレットは連結表示になりません)、
一度ウィンドウを閉じてから再びウィンドウを開いてください。
今度はパレットは連結表示になり、これ以降はみな連結表示になります。

<!--
##### Glyph Tabs
-->
##### グリフタブ (Glyph Tabs)

<!--
Controls whether the outline glyph view has a set of tabs of past glyphs
viewed in that window.
-->
アウトライングリフビューに、そのウィンドウで表示される過去のグリフのタブのセットがあるかどうかを制御します。

<!--
##### Rulers
-->
##### ルーラーを表示/隠す(R) (Rulers)

<!--
In the Glyph Outline View toggles whether rulers appear at the top and
to the left of the editing area.
-->
アウトライングリフビューでは、編集エリアの上辺と左辺にルーラーを表示するかどうかを切り替えます。


<!--
##### Horizontal Hints
-->
##### 水平ヒント (Horizontal Hints)

<!--
Controls whether horizontal hints are visible
-->
水平ヒントを表示するかどうかを制御します。


<!--
##### Vertical Hints
-->
##### 垂直ヒント (Vertical Hints)

<!--
Controls whether vertical hints are visible
-->
垂直ヒントを表示するかどうかを制御します。


<!--
##### Diagonal Hints
-->
##### 斜めヒント (Diagonal Hints)

<!--
Controls whether diagonal hints are visible
-->
斜めヒントを表示するかどうかを制御します。


##### BlueValues

<!--
Controls whether the glyph's PostScript BlueValues are visible
-->
グリフの PostSctript BlueValues を表示するかどうかを制御します。


##### FamilyBlues

<!--
Controls whether the glyph's PostScript FamilyBlues are visible.
-->
グリフの PostSctript FamilyBlues を表示するかどうかを制御します。


<!--
##### Anchors
-->
##### アンカー (Anchors)

<!--
Controls whether Anchor points are visible
-->
アンカーポイントを表示するかどうかを制御します。


<!--
##### Horizontal Metrics
-->
##### 水平メトリック (Horizontal Metrics)

<!--
Controls whether horizontal metrics lines (the width line) are visible.
-->
水平メトリックの線 (幅を表す線) を表示するかどうかを制御します。


<!--
##### Vertical Metrics
-->
##### 垂直メトリック (Vertical Metrics)

<!--
Controls whether vertical metrics lines (the vertical advance line) are
visible.
-->
垂直メトリックの線 (垂直方向の送り幅) を表示するかどうかを制御します。


<!--
##### Snap Outlines to Pixel Grid
-->
##### アウトラインをピクセルグリッドにスナップ (Snap Outlines to Pixel Grid)

<!--
Cairo can draw contours with sub-pixel resolution -- which means that if
a spline's end point falls somewhere between two pixels then cairo will
draw a bit of the contour on both pixels this leads to an often
undesirable level of fuzziness. In some sense it provides a more
accurate indication of where the spline goes. This menu item can be used
to turn that on and off.
-->
Cairo はサブピクセルの解像度で輪郭を描くことができます。
つまり、スプラインの終点が2つのピクセルの間にある場合、
Cairo は両方のピクセルに少し輪郭を描きます。
これにより、しばしば望ましくないレベルのぼやけが生じます。
ある意味では、スプラインの行き先をより正確に示します。
このメニュー項目を使用して、オンとオフを切り替えることができます。


<!--
#### Bigger Pixel Size
-->
#### ピクセルサイズを拡大 (Bigger Pixel Size)

<!--
In the bitmap view this displays the current glyph in next larger bitmap
font (if there is one)
-->
ビットマップビューでは、
次に大きいサイズのビットマップフォント (存在する場合) で現在のグリフを表示します。

<!--
#### Smaller Pixel Size
-->
#### ピクセルサイズを縮小 (Smaller Pixel Size)

<!--
In the bitmap view this displays the current glyph in next smaller
bitmap font (if there is one)
-->
ビットマップビューでは、
次に小さいサイズのビットマップフォント (存在する場合) で現在のグリフを表示します。
