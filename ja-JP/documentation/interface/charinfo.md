---
published: true
layout: default.ja
title: グリフ情報
---
<!--
published: true
layout: default
title: Glyph Information
-->

[table_of_contents]


<!--
### Encoding and Unicode data
-->
### エンコーディングと Unicode 情報 (Encoding and Unicode data)

![](/assets/img/dialogs1-charinfo.png)

<!--
This dialog allows you to set the name and unicode encoding of a given
glyph. If you know the name of the glyph then FontForge can tell you the
encoding (if you press Set From Name), similarly if you know the
encoding then FontForge can tell you the name.
-->
このダイアログでは、
既存のグリフの名前と Unicode の符号位置を設定できます。
グリフ名が決まっている場合
(<span class="command">名前で指定(A)</span>
ボタンを押せば)、
FontForge に符号位置を決めさせることができます。
同様に、エンコーディングが分かっていれば、
FontForge に名前を決めさせることができます。

<!--
The name field contains a pull down list with (possibly) several
synonyms for the name of this unicode code point.
-->
<span class="command">Unicode名(N)</span>
フィールドは、
この Unicode コードポイントの名前に対する
(おそらく) いくつかの同義な名前を列挙したプルダウンリストからなります。

<!--
It is possible to have one glyph assigned to two unicode code points
(This is not recommended, but it is possible). If you wish to do this
you may enter additional unicode values in the "`Alternate Unicode`"
area (set the variation selector to 0).
-->
1 つのグリフを 2 つの Unicode コードポイントに割り当てることができます
(これは推奨されませんが、可能です)。
これを行うには、
<span class="command">Alternate Unicode</span>
領域に追加の Unicode 値を入力します
(異体字セレクタは 0 に設定します)。

<!--
Adobe has proposed an extension to OpenType to support unicode variation
selectors in the 'cmap' table (traditionally they have been done as
ligatures in the 'GSUB' table). If you wish to take advantage of this
mechanism you can also use the "`Alternate Unicode/Variation`" section
to add 'cmap' data. If you wish the current glyph to be the default
variation for this font (the one that appears in the unicode encoding
subtable), then set the `Unicode Value` field above to the desired code
point and add an entry with the same code point and the appropriate
variation selector (as in the example above).
-->
アドビは、'cmap' テーブルの Unicode 異体字セレクタ (variation selector) をサポートするために、
OpenType の拡張機能を提案しています (従来は、'GSUB' テーブルで合字として行われていました)。
このメカニズムを利用したい場合は、
"`Alternate Unicode/Variation`"
セクションを使用して 'cmap' データを追加することもできます。
現在のグリフをこのフォント
(Unicode エンコードサブテーブルに表示されるもの)
の異体字のデフォルトにしたい場合は、
上記の `Unicode Value` フィールドを目的のコードポイントに設定し、
同じコードポイントと適切な異体字セレクタ (上記の例のように)
を持つエントリを追加します。

<!--
However if this glyph is not going to be the default glyph for this code
point, then set the `Unicode Value` field to -1, while entering the
appropriate code point and variation selector below.
-->
ただし、このグリフをコードポイントの既定のグリフとしない場合は、
`Unicode Value` フィールドを -1 に設定し、
コードポイントと異体字セレクタを下記のように入力します。

<!--
The Glyph class field is for the opentype 'GDEF' table. You can usually
leave it set to automatic. FontForge will then figure out the class, and
whether it should be output into GDEF. You can see what FontForge does
in [View-\>Show ATT](../showatt/).
-->
<span class="command">Glyph Class</span>
フィールドは、OpenType の 'GDEF' テーブル用です。
通常は、自動に設定したままにしておくことができます。
FontForge は、クラスを把握し、GDEF に出力する必要があるかどうかを判断します。
FontForgeの機能は、
[View-> Show ATT](../showatt/)
で確認できます。

<!--
The `[] Mark for Unlink, Remove Overlap Before Save` checkbox sounds
absurdly complicated. Consider the glyphs Aring, Ccedilla, and Oogonek.
In traditional design the accent of each of these glyphs will overlap
the base letter. Unfortunately neither TrueType nor PostScript allows
contours to intersect. You can solve this problem by unlinking the
references that make up the glyph and then running Element-\>Remove
Overlap. But that has problems of its own... now when you change the
base letter (or the accent) the change will no longer be reflected in
the composite glyph. This little checkbox neatly solves that problem. If
the glyph is composed of references which overlap, and you wish to
retain the references, but you wish it to be output without an overlap,
simply check this box. Then when it comes time to save the font, ff will
perform the unlink and then run remove overlap, save the font, and then
restore the glyph to its original condition.
-->
<span class="command">\[] Mark for Unlink, Remove Overlap Before Save</span>
(保存する前に重なる部分のリンクを解除し除去するための印)
チェックボックスは、とてつもなく複雑に聞こえます。
Aring, Ccedilla, Oogonek のグリフを検討してください。
従来のデザインでは、これら各グリフのアクセントはベースの文字と重なってきます。
残念ながら、TrueType も PostScript も輪郭を交差させることはできません。
この問題を解決するには、グリフを構成する参照のリンクを解除し、
<span class="command">Element-\>Remove Overlap</span>
を実行します。
しかし、これにはそれ自体の問題があります。
ベース文字 (またはアクセント) を変更しても、その変更はもはや複合グリフには反映されません。
この小さなチェックボックスはその問題をきれいに解決します。
グリフが重なり合う参照で構成されていて、
参照は維持したいが、重なり合いはなくして出力したい場合には、
このチェックボックスをオンにするだけです。
そうすれば、フォントを保存するときが来ると、
FonrForge はリンク解除を実行してから、重なり合いの削除を実行し、
フォントを保存してから、グリフを元の状態に戻します。


<!--
### Glyph Comment
-->
### グリフコメント (Glyph Comment)

![](/assets/img/dialogs1-charinfo-comment.png)

<!--
You can assign an arbitrary (unicode) comment to the glyph. Simply type any text 
into this field. The comment is for your use, it will not go into any generated 
fonts. You may also assign a color to a glyph to make it stand out in the font view.
-->
グリフに対して、任意の (Unicode の) コメントをつけることができます。
単純にこのフィールドで任意のテキストをタイプしてください。
コメントはあなたのためのもので、出力されるフォントには含まれません。
また、フォントビューの中で目立って見えるようにグリフに色を割り当てることもできます。


<!--
### Simple Glyph Positioning (GPOS)
-->
### 単純なグリフ位置指定 (GPOS) (Simple Glyph Positioning (GPOS))

![](/assets/img/dialogs1-charinfo-pos.png)

<!--
There are 6 separate sub-dialogs to help you edit the [lookups](../lookups/) 
of the [GPOS and GSUB](../gposgsub/) tables (some of these data can be 
converted into various of Apple's AAT tables, particularly 'morx'). Lookups
and their subtables are described in some detail [here](/en-US/tutorials/overview/#Lookups), 
and may be manipulated and created with the [Element-\>Font Info](../fontinfo/#Lookups) 
commmand.
-->
[GPOS および GSUB](../gposgsub/)
テーブルの
[照合テーブル](../lookups/)
の編集を補助するための、
6 個に分かれたサブダイアログがあります
(これらのテーブルのデータの一部は、
各種の Apple の AAT テーブル
-- とくに 'morx' -- に変換することができます)。
照合テーブルとそのサブテーブルはここで詳細に説明されており、
[Element-> Font Info](../fontinfo/#照合テーブル-lookups)
コマンドで操作および作成できます。

<!--
The first of sub-dialogs is the alternate position pane which allows you
to associate certain modifications to a glyph's metrics with a feature
in the GPOS table.
-->
1 番目のサブダイアログは代替位置タブです。
これにより、グリフのメトリックに対する特定の変更を GPOS テーブルの機能に関連付けることができます。

<!--
In the example at right the first lookup subtable (which is associated
with the Scientific Inferiors feature) will move the y position of the
glyph down by 900 em-units, while the second subtable will move it down
by 560 em-units. Positioning subtables can also move glyphs horizontally
and can adjust the horizontal and vertical advances of the glyph.
You can also add device tables
for pixel level corrections to these adjustments. Most subtables will
use only a few of the possibilities open to them and FontForge generally
hides unused columns -- but if you want to see them just turn off [\*]
Hide Unused Columns.
-->
右側の例では、最初の照合サブテーブル
(Scientific Inferiors 機能に関連付けられています)
はグリフの y 位置を 900 em 単位下に移動し、
2 番目のサブテーブルはグリフの y 位置を 560 em 単位下に移動します。
サブテーブルを配置すると、
グリフを水平方向に移動したり、グリフの水平および垂直方向の送りを調整したりできます。
これらの調整にピクセルレベル補正用のデバイステーブルを追加することもできます。
ほとんどのサブテーブルは、開くことができるもののみが使用され
FontForge は通常、未使用の列を非表示にします。
-- 表示させたいときは
<span class="command">\[\*] Hide Unused Columns</span>
をオフにしてください。

<!--
A new entry in the list may be created by pressing the \<New\> button
and a popup menu will appear with all possible lookup subtables you
could add data to.
-->
リストの新しいエントリを作成するには、
<span class="command">新規</span>ボタンを押すと、
ポップアップメニューが表示され、データを追加できるすべての照合サブテーブルが表示されます。


<!--
### Pair-wise Glyph Positioning (kerning) (GPOS)
-->
### ペア単位の位置指定 (kerning) (GPOS) (Pair-wise Glyph Positioning (kerning) (GPOS))

<!--
The pairwise positioning sub-dialog allows you to change the positions
of two glyphs when they occur next to one another -- better know as
kerning. I think the [Metrics View](../metricsview/)provides a better
place to do kerning, but you can do it here if you wish.
-->
ペア単位の位置指定サブダイアログでは、
2 個のグリフが決まった順番で表れたときの位置を変更することができます。
最も一般的な例はカーニングです
(もっと変更しやすい方法が、例えばメトリックビューなどでありますが、それを本当にやりたい場合はここで行うこともできます。


<!--
### Glyph Simple Substitution (GSUB, morx)
-->
### 単純置換 (GSUB, morx) (Glyph Simple Substitution (GSUB, morx))

![](/assets/img/dialogs1-charinfo-subs.png)

<!--
A simple substitution replaces one glyph with another. Here the glyph "one" 
has a series of substitutions to various glyphs depending on what lookup
subtable is invoked.
-->
単純置換は 1 個のグリフを他のグリフと置き換えます。
この図は、
"one" のグリフに依存して呼び出される照合サブテーブルには、
さまざまなグリフへ置換する項目があることを示しています。


<!--
### Glyph Alternate Substitution (GSUB) / Glyph Multiple Substitution (GSUB)
-->
### 選択型置換 (GSUB) / 複数の置換先 (GSUB) (Glyph Alternate Substitution (GSUB) / Glyph Multiple Substitution (GSUB))

<!--
The multiple and alternate substitution sub-dialogs are very similar to
this one except that they can take multiple glyph names. In a multiple
substitution subtable each glyph is replaced by several other glyphs
(sort of the reverse of a ligature), while in the alternate substitution
sub-dialog each glyph is to be replaced by exactly one glyph from a list
and the user is to be given a choice as to which glyph is to be chosen.
-->
<span class="command">複数の置換先</span>
および
<span class="command">選択型置換</span>
サブダイアログもそれと似ていますが、
これらは複数のグリフ名をとることができる点が異なります。
<span class="command">複数の置換先</span>
サブテーブルでは各グリフはいくつかの他のグリフによって置き換えられ
(ある意味、合字の反対です)、
<span class="command">選択型の置換</span>
サブダイアログでは、
各グリフはリスト内に含まれるちょうど 1 個の文字によって置き換えられ、
どのグリフを使うかについてはユーザが選ぶことができます。

> "Hello Rabbit," he said, "is that you?"
> "Let's pretend it isn't," said Rabbit, "and see what happens."
> Winnie-The-Pooh
>  A. A. Milne, 1926


<!--
### Glyph Ligature Substitution (GSUB, morx)
-->
### 合字 (GSUB, morx) (Glyph Ligature Substitution (GSUB, morx))

![](/assets/img/dialogs1-charinfo-lig.png)

<!--
The ligature pane allows you to tell FontForge that the current glyph is 
a ligature composed of several other glyphs. FontForge will sometimes be 
able to fill this in with the right default value, but not always. The value 
should be a list of postscript glyph names separated by spaces. If a glyph 
may be viewed as two different ligatures then they may both be specified 
in different lines. For example "ffi" may be viewed as a ligature of "f" 
"f" and "i" or of "ff" and "i".
-->
<span class="command">合字</span>
タブでは、
FontForge が現在のグリフがいくつかの他のグリフから合成されたグリフであることを
FontForge に知らせることができます。
FontForge はこのとき右側のデフォルトグリフを補完することがしばしばうまくできますが、
時には変更してやる必要が生じます。
この値は、空白で区切られた PostScript グリフ名のリストでなければなりません。
あるグリフが 2 つの異なる合字であると見なされるときには、
それらを両方とも、別々の行に指定しなければなりません。
例えば　"ffi" は "f" "f" "i" の合字と見ることもできますし、
"ff" と "i" の合字とも見なせます。


<!--
### Counter Masks
-->
### カウンタマスク (Counter Masks)

![](/assets/img/dialogs1-charinfo-counters.png)

<!--
In complicated Asian glyphs, postscript has a mechanism for controlling 
the width of counters between stems. These are called counter mask 
hints.
-->
アジアの複雑なグリフでは、
PostScript はステムの間のカウンタを制御するメカニズムを提供しています。
それらはカウンタマスクヒントと呼ばれます。

![](/assets/img/dialogs1-newcountermask.png)

<!--
In Latin, Cyrillic, Greek fonts only glyphs like "m" are allowed to have 
counter masks, and only in very controlled conditions. See the description 
of [counter masks](../hinting/#Counter).
-->
ラテン文字・キリル文字・ギリシャ文字のフォントではカウンタマスクを使用することができる文字は "m" など、非常に限られており、
使用できる状況も非常に限られています。
[カウンタマスク](../hinting/#Counter)
に関する説明を参照してください。


<!--
### Components
-->
### 構成要素 (Components)

![](/assets/img/dialogs1-charinfo-counters.png)

<!--
Some glyphs (ligatures, accented glyphs, Hangul syllables, etc.) are built up 
out of other glyphs (at least according to unicode). This pane of the dlg shows
the components that Unicode says make up the current glyph, if those components
are in the font then you can use FontForge's `Element->Build->Build Accented` or
`Element->Build->Build Composite` commands to create the current glyph.
The information displayed here is informative only, you may not change this field
directly (it changes when you change the unicode value or glyph name associated
with this glyph).
-->
いくつかのグリフ (合字、アクセントつきグリフ、ハングル音節文字など) は他のグリフから構築されています
(少なくとも Unicode に関して言えば)。
ダイアログのこのタブでは、Unicode で現在のグリフを構成することとなる要素を表示します。
それらの構成要素がフォントに含まれていれば、
FontForge の
<span class="command">エレメント(L)-\>組み立て(U)-\>アクセントつきグリフを構築(B)</span>
コマンドか
<span class="command">エレメント(L)-\>組み立て(U)-\>複合グリフを構築(C)</span>
コマンドを使用して現在のグリフを作成することができます。
ここで表示される情報は通知目的のためだけであり、
このフィールドを直接変更することは許されていません
(これは、そのグリフに割り当てられている Unicode 値またはグリフ名を変更したときに自動的に変更されます)。

![](/assets/img/dialogs1-charinfo-tex.png)

<!--
The TeX pane allows you to specify glyph specific information used in TeX
tmf files. The height and depth fields are often the same as the glyph's 
bounding box (if you don't fill these in that's what fontforge will use 
by default), but they should be corrected for optical distortion, so in glyphs
like "o" these fields should be clipped to the x-height and baseline (ff 
will attempt to do this when you press `[Guess]`).
-->
TeX タブでは、TeX の tmf ファイルで使用されるグリフ固有の情報を指定できます。
高さと深さのフィールドは、多くの場合、グリフの境界ボックスと同じです
(これを FontForge がデフォルトで使用するもので埋めない場合) が、
視覚的な歪みを修正する必要があるため、
これらのフィールドの "o" のようなグリフ x-height とベースラインにクリップする必要があります
(<span class="command">Guess</span>
を押すと、FontForge はこれを試みます)。

<!--
The Italic correction is used by both TeX and the new OpenType
[MATH](../../reference/math/#Italic) table. In the MATH table you may also specify a
device table to correct rounding errors at small pixel sizes.
-->
イタリック補正は、TeX と新しい OpenType
[MATH](../../reference/math/#Italic)
テーブルの両方で使用されます。
MATH テーブルでは、小さなピクセルサイズでの丸め誤差を修正するデバイステーブルを指定することもできます。

<!--
The Top Accent Position is another concept from the [MATH
table](../../reference/math/#TopAccent) and provides a horizontal position over
which to position math accents (vertical positioning is done somewhere
else).
-->
Top Accent Position (上部アクセント位置) は、
[MATH テーブル](../../reference/math/#TopAccent)
の別の概念であり、
数学アクセントを配置する水平位置を提供します
(垂直位置は別の場所で提供されます)。

<!--
For extremely tall glyphs the normal mechanisms for positioning
superscripts are inappropriate and the `[] Is Extended Shape` checkbox
alerts the typesetter to this fact.
-->
非常に背の高いグリフの場合、上付き文字を配置するための通常のメカニズムは不適切であり、
<span class="command">\[] Is Extended Shape</span>
チェックボックスは植字工にこの事実を警告します。

<!--
The [Math Kerning] button brings up the [Math Kerning
dialog](../../reference/math/#MathKern) which gives you fine control over the
placement of subscripts and superscripts near the glyph.
-->
<span class="command">Math Kerning</span>
ボタンをクリックすると、
[Math Kerning ダイアログ](../../reference/math/#MathKern)
が表示され、グリフの近くにある下付き文字と上付き文字の配置を細かく制御できます。


<!--
### Variants
-->
### 異形 (Variants)

![](/assets/img/dialogs1-charinfo-variants.png)

<!--
![](/assets/img/dialogs1-charinfo-variants.png)There are two panes for variants, one for
glyphs that get longer horizontally and one for glyphs that get longer
vertically.
-->
異形には 2 つのタブがあります。
1 つは水平方向に長くなるグリフ用、
もう 1 つは垂直方向に長くなるグリフ用です。

<!--
In mathmatical typesetting the size of a parenthesis will depend on the
vertical size of the formula within that parenthesis. As formulae can be
arbetarily complex they may be arbetarily tall, so there needs to be a
way of making arbetarily big parentheses. This pane provides two
mechanisms.
-->
数学的な組版では、括弧のサイズはその括弧内の式の垂直方向のサイズに依存します。
数式は非常に複雑で、非常に長くなることがあるため、
必要に応じて大きな括弧を作成する方法が必要です。
このタブには2つのメカニズムがあります。

<!--
At the top you may specify a list of prebuilt glyphs each a little
bigger than the one before.
-->
上部では、事前に作成されたグリフのリストを指定できます。
それらのグリフは元のものより少し大きくなっています。

<!--
Underneath you may specify a way of building really big parentheses by
combining several component glyphs. See the description of this in the
[MATH Info dialog](../../reference/math/#GlyphConstruction)for more details.
-->
下部では、いくつかのコンポーネントグリフを組み合わせて、本当に大きな括弧を作成する方法を指定できます。
詳細については、
[数学情報ダイアログ](../../reference/math/#GlyphConstruction)
の説明を参照してください。


<!--
### Tile Size
-->
### タイルサイズ (Tile Size)

![](/assets/img/dialogs1-charinfo-tilesize.png)

<!--
This only applies when editing type3 fonts. Even then it is only
meaningful if the current glyph is used as a
[pattern](../multilayer/#Patterns) in some other glyph.
-->
これは、Type3 フォントを編集する場合にのみ適用されます。
さらに、現在のグリフが他のグリフの
[パターン](../multilayer/#パターン-patterns)
として使用されている場合にのみ意味があります。

<!--
When a glyph is used as a pattern, the size of the pattern tile defaults
to the bounding box of the glyph used. This means there will be no
whitespace around the tile. Sometimes that is desirable (if the tiles
are to looks as though they touch), sometimes it is not. This provides
control over the whitespace that surrounds the drawn region of the tile.
-->
グリフがパターンとして使用される場合、
パターンタイルのサイズは、使用するグリフの境界ボックスがデフォルトとして設定されます。
これは、タイルの周りに空白がないことを意味します。
それが望ましい場合 (タイルが互いに接触するような見た目の場合) もありますし、
そうでない場合もあります。
これにより、タイルの描画領域を囲む空白を制御できます。

<!--
You can specify that you want a constant margin of white space around
all edges of the tile, or you can specify explicitly the coordinates of
the tile.
-->
タイルのすべてのエッジの周囲に一定の余白を確保することを指定したり、
タイルの座標を明示的に指定したりできます。

<!--
The Next and Prev buttons allow you to move from one glyph to the next
(if, for example, you need to enter encodings for a range of glyphs).
-->
<span class="command">次へ</span>
ボタンと
<span class="command">前へ</span>
ボタンを使用すると、
1つのグリフから次のグリフに移動できます
(たとえば、グリフの範囲のエンコードを入力する必要がある場合)。

<!--
The Cancel button now cancels all changes made with this instance of the
dialog.
-->
<span class="command">キャンセル</span>
ボタンは、
ダイアログのこのインスタンスで行われたすべての変更をキャンセルします。
