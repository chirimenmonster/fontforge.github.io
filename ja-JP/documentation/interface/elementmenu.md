---
published: true
layout: default.ja
title: エレメントメニュー
---
<!--
published: true
layout: default
title: The Element Menu
-->


[table_of_contents]


<!--
There are two menu entries [Tile Path](##Tile.Path) and
[Non Linear Transform...](##Non-Linear.Transform...) which are not part of the default
build but which may be configured by modifying `configure-fontforge.h`
before compiling FontForge.
-->
[パスのタイル敷き(P)](#パスのタイル敷きp-tile-path)
と
[非線形の変形(<U>N</U>)...](#非線形の変形n-non-linear-transform)
という2つのメニューエントリがあります。
これらはデフォルトビルドの一部ではありませんが、
FontForge をコンパイルする前に `configure-fontforge.h` を変更することで設定できます。

<!--
#### Font Info
-->
#### フォント情報(F) (Font Info)

<!--
In all views this brings up the [Font Info dialog](../fontinfo/).
-->
どのビューから実行した場合でも、
[フォント情報ダイアログ](../fontinfo/)
を起動します。

<!--
CID keyed fonts can set information on the CID font as a whole (rather
than just the current sub-font, which is what this command does) from
[CID-\>CID Font Info](../cidmenu/#FontInfo).
-->
CID フォントでは、
(このコマンドで現在のサブフォントを対象とするのではなく)
[<span class="command">CID->CIDフォント情報(I)</span>](../cidmenu/#FontInfo)
で CID フォント全体の情報の設定ができます。


<!--
#### Glyph Info
-->
#### グリフ情報(I) (Glyph Info)

<!--
In the all views this brings up the [Glyph Info
dialog](../charinfo/#Character).
-->
どのビューから実行しても、
[グリフ情報](../charinfo/#Character)
ダイアログを起動します。


<!--
#### MATH Info...
-->
#### 数学情報... (MATH Info...)

<!--
Brings up the [MATH Info dialog](../../reference/math/).
-->
[数学情報](../../reference/math/)
ダイアログを起動します。

<!--
##### BDF Info
-->
##### BDF 情報 (BDF Info)

<!--
If you have bitmaps in your font, then in the font view or bitmap view
this command will bring up the [BDF Info dialog.](../bdfinfo/)
-->
ビットマップを含むフォントを編集している場合、
フォントビューまたはビットマップビューでこのコマンドを呼び出すと
[BDF 情報](../bdfinfo/)
ダイアログが起動します。

<!--
##### Horizontal Baselines...
-->
##### 水平方向のベースライン... (Horizontal Baselines...)

<!--
This [dialog](../baseline/) gives you control over the OpenType 'BASE'
table which allows you to specify different baselines for different
scripts, and how to align those baselines with each other. It also
provides fine control over the inter-baseline spacing (the line height).
-->
この
[ダイアログ](../baseline/)
では、
OpenType の 'BASE' テーブルを制御できます。
これにより、さまざまな文字にさまざまなベースラインを指定し、
それらのベースラインを相互に調整する方法を指定できます。
また、ベースライン間の間隔 (行の高さ) を細かく制御できます。


<!--
##### Vertical Baselines...
-->
##### 垂直方向のベースライン... (Vertical Baselines...)

<!--
This [dialog](../baseline/) gives you control over the OpenType 'BASE'
table which allows you to specify different baselines for different
scripts, and how to align those baselines with each other. It also
provides fine control over the inter-baseline spacing (the column
width).
-->
この
[ダイアログ](../baseline/)
では、
OpenType の 'BASE' テーブルを制御できます。
これにより、さまざまな文字にさまざまなベースラインを指定し、
それらのベースラインを相互に調整する方法を指定できます。 
また、ベースライン間の間隔 （列幅) を細かく制御できます。


<!--
##### Justification Information...
-->
##### 位置合わせ情報... (Justification Information...)

<!--
This [dialog](../justify/) allows you to examine and provide the
information needed for the OpenType JSTF table -- information which
helps layout engines do text justification.
-->
この
[ダイアログ](../justify/)
では、OpenType JSTF テーブルに必要な情報
-- レイアウトエンジンがテキストの位置合わせを行うのに役立つ情報 --
を調べて提供できます。

<!--
##### Show Dependencies
-->
##### 依存関係の表示 (Show Dependencies)

<!--
###### References...
-->
###### 参照一覧(R) (References...)

<!--
This dialog is not available in the bitmap view. It shows you what
glyphs contain a reference to the current glyph. You can open a window
looking at any of the dependent glyphs by selecting that glyph and
pressing the [Show] button.
-->
このダイアログはビットマップビューでは使用できません。
どのグリフが現在のグリフへの参照を含んでいるかを表示します。
これを実行すると、現在のグリフに依存するすべてのグリフを一覧表示するウィンドウが現れます。
そこでグリフを選択して
<span class="command">[表示]</span>
ボタンを押せば、そのグリフを開くことができます。


<!--
###### Substitutions...
-->
###### 置換一覧(S)... (Substitutions...)

<!--
Show any glyphs that have substitutions (ligatures, multiple subs, etc.)
which depend on the current glyph. So if you select "i", you might see
that "fi" depended on it as a ligature, and if you select "A.swash" you
might see that "A" depended on it as a 'swsh' alternate subs.
-->
現在のグリフに依存する置換 (合字、複数文字への置換など) をすべて表示します。
例えば "i" を選択した場合、"fi" が合字として依存しているのが表示されるでしょうし、
"A.swash" を選択している時は
"A" が 'swsh' 選択型置換として表示されているのが表示されるでしょう。


<!--
##### Mass Glyph Rename...
-->
##### グリフ集団の名前変更... (Mass Glyph Rename...)

![](/assets/img/filemenu-massrename.png)

<!--
This allows you to rename a bunch of selected glyphs. It can be used
in two ways, either:
-->
これにより、選択したグリフの名前を変更できます。
次の2つの方法で使用できます:

<!--
- You want to rename all the selected glyphs by adding a suffix to
  their names (this might be useful if you are working with a small
  caps Type1 font that you wanted to convert to an otf font, where the
  old convention was just to name the glyphs as "a", "b" and so forth
  rather than "a.sc", "b.sc", etc.).
- Or you can select a block of glyphs, and specify another glyph
  somewhere in the encoding, then the selected glyphs would get be
  named by appending the suffix to the sequence of glyphs starting
  with the one identified in the dialog. (This might be useful if you
  wanted to add a small caps collection to an existing font). In this
  case you may also specify a lookup subtable so that the base glyphs
  would get substituted by the appropriate renamed glyphs when that
  subtable was activated (this can't be done in the previous case,
  because there are no longer any base glyphs)
-->
- 名前に接尾辞を追加して、選択したすべてのグリフの名前を変更します
  (これは、
  スモールキャップの Type1 フォントを OTF フォントに変換する作業をしている場合に便利です。
  元の Type1 の規則では "a.sc", "b.sc" などではなく
  "a", "b" のような名前が付けられています)。
- または、グリフのブロックを選択し、
  エンコードのどこかに別のグリフを指定すると、
  選択されたグリフは、ダイアログで識別されたものから始まる一連のグリフに接尾辞を追加することで名前が付けられます。
  (これは、既存のフォントにスモールキャップスの集合を追加する場合に便利です)。
  この場合、ルックアップサブテーブルを指定して、
  そのサブテーブルがアクティブになったときに,
  ベースグリフが適切な名前変更されたグリフに置き換えられるようにすることもできます
  (ベースグリフがなくなったため、前のケースではできません)


<!--
#### Get Info
-->
#### 情報を得る(I) (Get Info)

<!--
In the outline view this brings up [one of four different
dialogs](../getinfo/) (Point Info, Image Info, Reference Info, Anchor
Point Info) depending on what is selected.
-->
アウトラインビューでは選択した物によって異なる
[4 種類の異なるダイアログ](../getinfo/)
(点の情報、画像情報、参照情報、アンカーポイント情報) のどれかを起動します。


<!--
#### Find Problems...
-->
#### 問題点を発見(O)... (Find Problems...)

<!--
This command is not present in the bitmap view. It will search for
several common problems. In the glyph view it will select anything that
needs to be fixed, in the font view it will check all selected glyphs
and if any have problems will open them and select the problems. It will
post a message telling you of each problem found. It brings up the [Find
Problem](../problems/) dialog to let you choose what problems to look
for.
-->
このコマンドはビットマップビューには存在しません。
このコマンドはいくつかのよくある問題点を探します。
グリフビューでは修正の必要のあるすべての問題点を表示します。
フォントビューでは選択中の文字をすべてチェックし、
どれかの文字に問題があればそれを開き、
問題点を表示します。
それとともに、発見された各問題点を通知するメッセージを送ります。
[問題点を発見](../problems/)
ダイアログが開かれます。


<!--
#### Validate...
-->
#### 検証... (Validate...)

<!--
Rather similar to Find Problems, but works with a much smaller set of
things which are definitely errors, and provides an overview of the
problems found in all glyphs of the font. See the [validation
page](../validation/) for more info.
-->
<span class="command">問題点を発見(O)</span>
に似ていますが、
明確なエラーに対してはより小さなものについても動作し、
フォントのグリフすべてでで見つかった問題の概要を提供します。
詳細については、
[検証](../validation/)
ページを参照してください。

<!--
#### Bitmap Strikes Available...
-->
#### 使用するビットマップ(A)... (Bitmap Strikes Available...)

<!--
This brings up a list of pixel sizes for bitmap fonts.
-->
このコマンドはビットマップフォントのピクセルサイズ一覧を表示します。

![](/assets/img/filemenu-bitmapsavail.png)

<!--
If you have bitmap fonts this will show their pixel sizes. If you remove
a size that is in the list then that font will be deleted from the sfd
file. If you add a size then that size font will be created and stored
in the sfd file.
-->
編集中のフォントにビットマップが含まれているときは、
それらのピクセルサイズを一覧表示します。
リストからサイズ表示を取り除くと、SFD ファイルからそのサイズのビットマップフォントが削除されます。
サイズを追加すると、そのサイズのフォントが追加され、
SFD ファイルに格納されます。

<!--
FontForge deals in pixel sizes, not point sizes. The conversion between
pixels and points differs on different systems and indeed on different
screens. A point is (approximately) 1/72 of an inch, a pixel is however
big a pixel happens to be on your screen. Usually pixels range from
about 1/72 of an inch to about 1/144 of an inch. Different systems
support different screen resolutions as "standard", and FontForge tries
to know about these standards.
-->
FontForge が取り扱うのはピクセルサイズであってポイントサイズではありません。
ピクセルとポイントの間の変換はシステムごとに異なり、
実際には表示画面ごとに異なります。
1 ポイントは (約) 1/72 インチですが、
1 ポイントが何ピクセルに相当するかは画面の設定によって異なります。
通常 1 ピクセルは 1/72 インチ 〜 1/144 インチです。
システムが異なると "標準" としてサポートされるデフォルトの画面解像度は異なります。
FontForge は、以下の標準について知ろうと努めています。

<!--
Some conversions between points and pixels
-->
ポイント数とピクセル数のいくつかの変換方法

<!--
    Screen Resolution   72dpi   75dpi   96dpi   100dpi  120dpi
    Point Size          Mac     X       Win     X       Win
    10pt                10      10      13      14      17
    12pt                12      12~13   16      17      20
    18pt                18      19      24      25      30
    24pt                24      25      32      33      40
-->
    画面解像度          72dpi   75dpi   96dpi   100dpi  120dpi
    ポイントサイズ      Mac     X       Win     X       Win
    10pt                10      10      13      14      17
    12pt                12      12~13   16      17      20
    18pt                18      19      24      25      30
    24pt                24      25      32      33      40

<!--
Sadly your screen will probably not match one of the standard screens
precisely. On X the standard resolutions are 75 and 100dpi, on MS
Windows 96 and 120dpi, and on the Mac 72dpi. This dialog provides the
conversion between pixel size and point sizes at these resolutions.
-->
残念ながら、あなたの画面解像度はおそらく標準解像度とは一致しないでしょう。
X では標準解像度は 75dpi と 100dpi で、
MS Windows では 96 dpi と 120dpi、
Mac では 72dpi です。
このダイアログは、ピクセルサイズと、これらの解像度におけるポイントサイズとの間で変換を行います。

<!--
Normally the new glyphs are created by rasterizing the outline font. If
your system has the freetype2 library installed (and you checked the
"Use FreeType" box) then FontForge will use the FreeType rasterizer to
generate bitmaps, otherwise it will use FontForge's built-in rasterizer
(which isn't as good, but involves a little less overhead).
-->
通常は、新しいグリフはアウトラインフォントをラスタライズすることによって作成されます。
システムに freetype2 ライブラリがインストールされている場合
(そして "FreeType を使う" チェックボックスにチェックが入っている場合)
FontForge はビットマップの生成に FreeType ラスタライザを使用します。
それ以外の場合、
FontForge は内蔵ラスタライザ
(能力では劣りますが、オーバヘッドは少し削減されます)
を使用します。

<!--
Finally, if you have no outline font then the new glyphs will be created
by scaling the (bitmap) font displayed in the font view.
-->
最後に、もしアウトラインフォントが存在しない場合、
新しいグリフはフォントビュー内に表示されている (ビットマップ) フォントを拡大・縮小して作成されます。

<!--
If you want to generate a blank strike (one containing no glyphs) then
turn off the `[] Create Rasterized Strikes` checkbox.
-->
空白のストライク (グリフを含まないストライク) を生成する場合は、
<span class="command">\[\] ラスタライズされたストライクを作成</span>
チェックボックスをオフにします。

<!--
In CID keyed fonts there will not be a set of bitmaps for each sub font,
instead the entire complex of sub-fonts share bitmaps.
-->
CID フォントでは、各サブセットにはビットマップは存在しません。その代りに、サブフォントの複合体全体がビットマップを共有します。

![](/assets/img/filemenu-greymapsavail.png)

<!--
FontForge also supports anti-aliased bitmap fonts,
and you can use this dialog to generate them. If you want to generate a
12 point anti-aliased font with 8 bits per pixel you would type 12@8
into the dialog above. FontForge supports 1, 2, 4 and 8 bit per pixel
fonts (a 1 bit per pixel font is a standard bitmap, the others are
greymaps).
 (New greymaps can not be created by scaling old greymaps, if you wish
to generate a greymap font, you must have an outline font).
-->
FontForge はアンチエイリアス表示のビットマップフォントもサポートしており、
このダイアログを使ってそれらを生成するように設定することもできます。
12 ポイントのアンチエイリアスフォントを各ピクセル 8 ビットの階調で作成したいなら、
上のダイアログに 12@8 と入力します。
FontForge は各ピクセル 1, 2, 4, 8 ビットのフォントをサポートしています (各ピクセル 1 ビットのフォントは標準ビットマップで、その他はグレイマップです)。<br>
 (新しいグレイマップは古いグレイマップを拡大・縮小して作成することはできません。
グレイマップフォントを作成したい場合、アウトラインフォントを持っている必要があります)。


<!--
#### Regenerate Bitmap Glyphs...
-->
#### ビットマップの再生成(B)... (Regenerate Bitmap Glyphs...)

<!--
If you have changed the outline that a bitmap is based one then you
should (at some point) look into changing the bitmap too. This command
allows you to regenerate a subset of the glyphs in a given bitmap font.
In the font view you can regenerate all selected glyphs, while in the
bitmap and outline views you can regenerate the current glyph. You can
pick what pixel sizes should be regenerated too (unlike the above
command, removing a bitmap size from the regenerate list will not delete
it). As before, if you wish to change a greymap you should refer to it by
`pixel-size@bits-per-pixel`.
-->
アウトラインフォントに基づいたビットマップが作られている場合、
そのアウトラインを変更したら (ある時点で) ビットマップもちょっと直したくなるでしょう。
このコマンドを使用すると、
既存のビットマップフォントに含まれるあるグリフのサブセットを再生成することができます。
どのピクセルサイズを再生成するかを選択することもできます
(上のコマンドと異なり、あるビットマップサイズを再生成のリストから削除しても、
フォントからそのサイズが削除されることはありません)。<br>
上と同じように、グレイマップを変更したい場合は
`pixel-size@bits-per-pixel`
で指定することができます。


<!--
#### Remove Bitmap Glyphs...
-->
#### ビットマップグリフの除去... (Remove Bitmap Glyphs...)

<!--
This command will remove one or several bitmap glyphs from a strike
(while leaving the strike otherwise intact). The dialog is similar to
the above two. Any indicated glyphs will be removed from the specified
strikes.
-->
このコマンドは、1つまたは複数のビットマップグリフをストライクから削除します (ストライクはそのままにします)。
ダイアログは上記の 2 つに似ています。
指定されたグリフは、指定されたストライクから削除されます。


<!--
#### Styles
-->
#### スタイル (Styles)

<!--
There are many [standard variations](../Styles/) on Latin (Greek,
Cyrillic) fonts. Some of them apply to other scripts -- making a font
darker (bolder) is common to many scripts, though the actual mechanics
differ from script to script) Others -- such as Italic -- are more
specialized.
-->
ラテン文字 (ギリシャ文字、キリル文字) フォントには多くの
[標準バリエーション](../Styles/)
があります。
それらのバリエーションの一部は、他の文字にも該当します
-- フォントを濃くする (ボールドにする) ことは多くの文字に共通です
(実際のメカニズムは文字ごとに異なります)
が、他のバリエーション
-- イタリックなど -- はより特殊なものになっています。


<!--
##### Change Weight...
-->
##### ウェイトの変更... (Change Weight...)


<!--
This is a simplistic command to make the stems of glyphs darker or
lighter. It sometimes works.
-->
これは、グリフのステムを暗くしたり明るくしたりする単純なコマンドです。
時々機能します。

<!--
For CJK glyphs it simply expands the strokes of the font outward.
-->
CJK グリフの場合、フォントのストロークを外側に広げるだけです。

<!--
For LCG (Latin, Cyrillic, Greek) glyphs it expands the stroke outward
and then moves everything below a certain point up, and everything above
another point down. This is based on heuristics and will fail if a glyph
is even the slightest bit unexpected.
 For other writing systems FontForge will do something, currently it
will fall into one of the two cases above.
 See the [Change Weight dialog](../Styles/#Embolden).
-->
LCG (ラテン、キリル、ギリシャ) グリフの場合、
ストロークを外側に拡張し、
特定のポイントより下のすべてを上に、
別のポイントより上のすべてを下に移動します。
これはヒューリスティックに基づいており、
グリフが少しでも予期しないものである場合は失敗します。<br>
 他の書記システムのために、FontForge は何かを行いますが、
現在は上記の 2 つのケースのいずれかに該当する場合は失敗します。<br>
 [ウェイト変更ダイアログ](../Styles/#the-change-weight-dialog)
を参照してください。


<!--
##### Italic
-->
##### イタリック体 (Italic)

<!--
An italic font is different from and more complex than an oblique font.
Traditionally fonts with serifs are made italic and fonts without serifs
are made oblique. This will change some letterforms, change the serifs,
condense the font and slant things. See the
[Italic dialog](../Styles/#Italic).
-->
イタリック体フォントは、斜体フォントとは異なり、より複雑です。
伝統的に、セリフ付きのフォントはイタリック体になり、
セリフなしのフォントは斜体になります。
この機能より、一部の文字形式が変更され、
セリフが変更され、
フォントが凝縮され、
文字が斜めになります。
[イタリック体ダイアログ](../Styles/#italic-dialog)
を参照してください。


<!--
##### Oblique
-->
##### 斜体 (Oblique)

<!--
An oblique font is different from and simpler than an italic font.
Traditionally fonts with serifs are made italic and fonts without serifs
are made oblique. This will slant the letters.
-->
斜体フォントは、イタリック体フォントとは異なり、シンプルです。
伝統的に、セリフ付きのフォントはイタリック体になり、
セリフなしのフォントは斜体になります。
この機能により、文字が斜めになります。


<!--
##### Condense/Extend
-->
##### 長体/平体 (Condense/Extend)

<!--
Allows you to change the width of the counters and side bearings of a
glyph. The algorithm only works on simple latin glyphs, and it has
problems with diagonal stems. See the
[Condense/Extend dialog](../Styles/#Condense).
-->
グリフの輪郭とサイドベアリングの幅を変更できます。
このアルゴリズムは、単純なラテングリフでのみ機能し、
斜めのステムでは問題があります。
[長体/拡張 ダイアログ](../Styles/#condenseextend-dialog)
を参照してください。

<!--
##### Change X-Height
-->
##### x ハイトの変更 (Change X-Height)

<!--
Allows you to change the x-height of a font
-->
フォントの x ハイトを変更できます。


<!--
##### Change Glyph...
-->
##### グリフの変更... (Change Glyph...)

<!--
Allows you to make very general changes to a glyph's shape.
-->
グリフの形状に非常に一般的な変更を加えることができます。


<!--
##### Add Small Caps
-->
##### スモールキャップスの追加 (Add Small Caps)

<!--
This is a little different from the previous menu items as it does not
change the selected characters themselves. Instead it creates a new
glyph (or reuses an old one) with the appropriate name. So if you
selected "A", "B", and "C" it would create glyphs "a.sc", "b.sc" and
"c.sc". It will create two lookups one bound to 'c2sc' which maps
capital letters to small caps, and the other bound to 'smcp' which maps
lower case letters to small caps. It will build the appropriate small
caps glyphs in the new glyph slots. This only applies to upper and lower
case letters in the latin, greek and cyrillic scripts.
[See the Small Caps dialog](../Styles/#Smallcaps).
-->
これは、選択した文字自体を変更しないため、これまでのメニュー項目とは少し異なります。
代わりに、適切な名前で新しいグリフを作成します
(または古いグリフを再利用します)。
したがって、
"A", "B", "C" を選択した場合、
グリフ "a.sc", "b.sc", "c.sc" が作成されます。
2 つのルックアップテーブルが作成され、
1つは大文字をスモールキャップスにマップする 'c2sc' にバインドされたもの、
もう1つは小文字をスモールキャップにマップする　'smcp' にバインドされたものです。
新しいグリフ位置に適切なスモールキャップグリフを作成します。
この機能は、ラテン文字、ギリシャ文字、キリル文字の大文字と小文字にのみ適用されます。
[スモールキャップスダイアログ](../Styles/#small-capitals-dialog)
を参照してください。


<!--
##### Add Subscripts/Superscripts
-->
##### 下付き文字/上付き文字の追加 (Add Subscripts/Superscripts)

<!--
Like the previous command this creates new glyphs based on the selected
ones. The outlines of the selected glyphs will be scaled (with stems
potentially being scaled differently from the glyph as a whole), and
moved vertically. Then a new lookup will be created mapping the original
glyph to the newly created one under control of the appropriate feature.
[See the Subscript/Superscript dialog](../Styles/#SubSuper).
-->
前のコマンドと同様に、これは選択されたものに基づいて新しいグリフを作成します。
選択されたグリフのアウトラインはスケーリングされ
(ステムはグリフ全体とは異なる方法でスケーリングされる可能性があります)、
垂直方向に移動されます。
次に、適切な機能の制御下で、
元のグリフを新しく作成されたグリフにマッピングする新しいルックアップテーブルが作成されます。
[下付き文字/上付き文字ダイアログ](../Styles/#subsciptsuperscript-dialog)
を参照してください。

<!--
##### Outline
-->
##### アウトライン(O) (Outline)

![](/assets/img/filemenu-outlineinline.png)

<!--
Changes the selected glyphs so that instead of being a solid block, only
the outline of the glyph is visible. The glyphs' bounding boxes will not
change.
-->
選択されたグリフを中身の詰まった塊ではなく、
グリフの輪郭だけが見えるように変形します。
グリフのバウンディングボックスは変更しません。


<!--
##### Inline
-->
##### インライン(I) (Inline)

<!--
Changes the selected glyphs so that the glyph is surrounded by an
outline. The glyphs' bounding boxes will not change.
-->
選択中のグリフを加工し、グリフがアウトラインで囲まれたようにします。
グリフのバウンディングボックスは変更しません。


<!--
##### Shadow
-->
##### 影つき(S) (Shadow)

<!--
Changes the selected glyphs to give them each a
shadow.
-->
選択中の各文字に影をつけます。

![](/assets/img/filemenu-shadowwireframe.png)

<!--
The user has control over the shadow size and angle.
-->
ユーザは影の長さと角度を調節することができます。


<!--
##### Wireframe
-->
##### 縁どり立体化(W) (Wireframe)

<!--
Changes the selected glyphs to give them a 3D wireframe look.
-->
選択されたグリフを縁取られた立体に見えるように加工します。


<!--
#### Transformations
-->
#### 変形 (Transformations)

<!--
This sub-menu has rather different choices in the bitmap view from the
other views. (Because bitmaps are discrete and the continuous
transformations of splines are not meaningful).
-->
このサブメニューは、ビットマップビューでは他のビューとかなり異なる選択肢が表示されます。
(なぜならビットマップは離散的で、スプラインのような連続変形は無意味だからです)。


<!--
##### Transform...
-->
##### 変形(T)... (Transform...)

<!--
[In the Font and Outline Views this brings up the transform
dialog](../transform/). This provides the standard linear
transformations you expect to have available (rotation, scaling,
translation, skewing).
-->
フォントビューとアウトラインビューではこのコマンドは
[変形ダイアログ](../transform/)
を表示します。
このコマンドは普通に考えて利用できそうな標準的な線形変換
(回転、拡大・縮小、平行移動、傾き)
を提供します。


<!--
##### Point of View Projection
-->
##### 透視変換(P) (Point of View Projection)

<!--
[This dialog](../transform/#PoV)allows you to perform a perspective
transformation on your glyphs. (This is a non-linear transformation)
-->
[このダイアログ](../transform/#point-of-view-projection)
を使うと、グリフに対して透視変換を施すことができます
(これは非線形変換の一種です)。


<!--
##### Non-Linear Transform...
-->
##### 非線形の変形(N)... (Non-Linear Transform...)

<!--
[This dialog](../transform/#Non-Linear) allows you to perform a general
transformation (which could be linear or which can be non-linear).
Essentially you provide two equations for how x and y should be mapped.
-->
[このダイアログ](../transform/#non-linear-transformations)
を使うと、一般的な変換を施すことができます
(線形変換も非線形変換も可能です)。
本質的には、x と y がどのように写像されるかを 2 個の等式で指定します。

<!--
This command is not available in the default build, you must modify the
file `configure-fontforge.h` and then rebuild FontForge. This command
allows the user to specify a non-linear transformation as a pair of
expressions (the first specifies the transformation for the x
coordinate, the second for the y coordinate). These expressions may be
fairly general functions of x and y. See the
[scripting page](../../scripting/native/scripting-alpha/#NonLinearTransform)
for a description of the syntax.
-->
このコマンドはデフォルトのビルドでは使用できません。
ファイル `configure-fontforge.h` を変更してから FontForge を再構築する必要があります。
このコマンドを使用すると、ユーザーは非線形変換を式のペアとして指定できます
(最初は x 座標の変換を指定し、2番目は y 座標の変換を指定します)。
これらの式は、 x および y のかなり一般的な関数です。
構文の説明については、
[スクリプトのページ](../../scripting/native/scripting-alpha/#NonLinearTransform)
を参照してください。

<!--
##### Flip Horizontally
-->
##### 水平方向に反転(H) (Flip Horizontally)

<!--
Flips the bitmap horizontally. (Only in bitmap view)
-->
ビットマップを水平方向に反転します (ビットマップビューのみ)。


<!--
##### Flip Vertically
-->
##### 垂直方向に反転(V) (Flip Vertically)

<!--
Flips the bitmap vertically. (Only in bitmap view)
-->
ビットマップを垂直方向に反転します (ビットマップビューのみ)。


<!--
##### Rotate 90° CW
-->
##### 時計回りに90°回転(R) (Rotate 90° CW)

<!--
Rotates the bitmap 90° clockwise. (Only in bitmap view)
-->
ビットマップを時計回りに90°回転します (ビットマップビューのみ)。


<!--
##### Rotate 90° CCW
-->
##### 反時計回りに90°回転 (Rotate 90° CCW)

<!--
Rotates the bitmap 90° counter-clockwise. (Only in bitmap view)
-->
ビットマップを反時計回りに90°回転します (ビットマップビューのみ)。


<!--
##### Rotate 180°
-->
##### 180°回転 (Rotate 180°)

<!--
Rotates the bitmap 180° (Only in bitmap view)
-->
ビットマップを 180°回転します (ビットマップビューのみ)。

<!--
##### Skew
-->
##### 傾き(S) (Skew)

<!--
Allows you to specify a ratio by which to skew the bitmap 1:3 means for
every 3 pixel rise in y, skew the bitmap one pixel horizontally. (Only
in bitmap view)
-->
ビットマップを傾ける割合を指定します。
1:3 の時は、y 方向に 3 ピクセル上にいくごとに 1 ピクセル横に傾くことを意味します
(ビットマップビューのみ)。


<!--
#### Expand Stroke...
-->
#### 輪郭を太らせる(E)... (Expand Stroke...)

<!--
Not in the bitmap view. In the font view it applies to all foreground
splines in all selected glyphs. In the outline view it applies to all
paths that have at least one point selected (or if no points are
selected then it applies to all paths).
-->
ビットマップビューからは呼び出せません。
フォントビューでは選択されたすべてのグリフの前面にあるすべてのスプラインに対して太め処理を適用します。
アウトラインビューでは、最低 1 個の点が選択されているすべてのパスに適用します
(点が選択されていないときには、すべてのパスに適用します)。

![](/assets/img/filemenu-twolines.png)
![](/assets/img/filemenu-expandedlines.png)

<!--
Above is a simple example of what expand stroke can do. It takes the
two open paths above left and turns them into the two closed paths
right.
-->
上図は、ストロークの太め処理が何を行うかの簡単な例です。
左上にある 2 本の開いたパスを元に、それらを右の 2 本の閉じたパスに変換します。

![](/assets/img/filemenu-expandstroke.png)

<!--
The Expand Stroke dialog gives you control over various aspects of the
expansion process. First you can specify three types of pen nibs:
-->
<span class="command">輪郭を太らせる(E)</span>
ダイアログは、パスを太くする処理のさまざまな様相を制御することができるダイアログを起動します。
最初に、3種類のペン先を指定できます:

<!--
- A round pen, which is circular by default but may be transformed
  into an ellipse
- A rectangular pen, which is square by default but may be transformed
  into more traditional caligraphic nib shapes
- A polygonal pen -- you can draw almost any convex polygon.
-->
- 丸ペン。デフォルトでは円形ですが、楕円に変換される場合があります
- 長方形のペン。デフォルトでは正方形ですが、より伝統的な口径のペン先の形に変換できます
- 多角形のペン -- ほとんどすべての凸多角形を描くことができます。

<!--
For circular and caligraphic pens you can chose a stroke width, how the
ends of an open path should be drawn, and how the path should look when
two splines (or lines) join which do not have the same slope (ie. at a
corner point).
-->
円形ペンとカリグラフィックペンの場合、
ストローク幅、開いたパスの端を描画する方法、
2つのスプライン (またはライン) が同じ角度を持たないで結合 (つまりコーナーの点) するときのパスの外観
を選択できます。

<!--
For closed contours you may also choose to remove either the generated
contour which is inside the original, or that which is outside
-->
閉じた輪郭の場合、
元の内側にある生成された輪郭、
または外側にある生成された輪郭のいずれかを削除することもできます。

<!--
*Note: Make sure your glyph is oriented correctly with
[Edit-\>Correct Direction](#Correct) before removing a contour (if
misoriented the wrong contour may be removed).*
-->
*注： 輪郭を削除する前に、
[<span class="command">編集->アウトラインの向きを修正（C)</span>](#アウトラインの向きを修正c-correct-direction)
でグリフの向きが正しいことを確認してください
(向きが間違っていると、間違った輪郭が削除される場合があります)。*

<!--
[How is this done?](pfaeditmath.html#Stroke)
-->
[どうやって処理しているのか?](../../developers/pfaeditmath/#calculating-the-outline-of-a-stroked-path)


<!--
#### Tile Path
-->
#### パスのタイル敷き(P) (Tile Path)

<!--
This command is not available in the default build, you must reconfigure
`$ configure --with-tilepath` and then rebuild FontForge. Not available
in quadratic (truetype) fonts. This command brings up a
[dialog](../tilepath/) which allows you to specify a tile to be applied
to any selected contours.
-->
このコマンドはデフォルトのビルドでは利用できません。
`$ configure --with-tilepath` で再構成してから
FontForge を再ビルドする必要があります。
2 次曲線 (TrueType) フォントでは使用できません。
このコマンドは、選択した輪郭に適用するタイルを指定するための
[ダイアログ](../tilepath/)
を表示します。

<!--
#### Tile Pattern...
-->
#### タイルパターン... (Tile Pattern...)

<!--
Also not available in the default build, also controled by
`$ configure --with-tilepath`. [This command](../tilepath/#Pattern)
allows you to design a pattern which will be layed down on the current
layer m\*n times (where m is the number of horizontal repeats and n the
number of vertical repeats.
-->
これも、デフォルトのビルドでは利用できません。
`$ configure --with-tilepath`
で制御されます。
[このコマンド](../tilepath/#tile-pattern)
を使用すると、
現在のレイヤーに m\*n 回配置されるパターンを設計できます
(m は水平方向の繰り返し数、
n は垂直方向の繰り返し数です)。


<!--
#### Overlap
-->
#### 重なり合う図形 (Overlap)

<!--
None of these is available in the bitmap view.
-->
これらのコマンドはビットマップビューでは使用できません。

<!--
##### Remove Overlap
-->
##### 重なり合う図形を結合(R) (Remove Overlap)

<!--
Not in the bitmap view, *not available when the font has quadratic
splines*^[1](#overlap-footnote)^. If two closed paths intersect then
there will be overlap. This will get rid of it, leaving one closed path
behind.
-->
ビットマップビューには存在しません。
*フォントが 2 次スプラインのときは使用できません*^[1](#overlap-footnote)^。
2 本の閉じたパスが交差するとき、
それらを重なり合っていると言います。
このコマンドは、重なり合いを取り除いて 1 本のパスに変換します。

<!--
Make sure paths have the correct orientation. Consider the letter "O"
with two contours. If both contours run in the same direction then the
inner path will be removed (because the outer path overlaps it
everywhere), but if the contours run in opposite orientations then the
inner path will be retained. Things get very strange if you have
intersecting paths with different orientations.
-->
パスの向きが正しいことを確かめておいてください。
2 本の輪郭をもつ文字 "O" を考えましょう。
2 本の輪郭が同じ方向を向いている場合、内側のものが削除されます
(外側のパスが全体に重なり合っているからです)
が、
輪郭同士が逆向きになっている場合、
内側のパスは保持されます。
交差するパスが逆向きになっているときは非常に奇妙なことが起こります。

![](/assets/img/filemenu-expandedlines.png)
![](/assets/img/filemenu-overlappedlines.png)

<!--
This command is probably the buggiest in FontForge. So before FontForge
invokes the command it will save the state to the error recovery file.
-->
このコマンドは FontForge の中でおそらく最もバグが多いはずです。
ですから、FontForge はコマンドを起動する前にエラー回復ファイルに現状を保存します。

<!--
**Warning: Splines which are tangent (or nearly so) cause problems.
Points which are close together can cause problems.**
-->
**警告: 平行な (またはほとんどそれに近い) スプラインは問題を起こします。
あまりに近い点も問題を起こす可能性があります。**


<!--
##### Intersect
-->
##### 重複部分を抽出(I) (Intersect)

![](/assets/img/filemenu-exclude-pre.png)
![](/assets/img/filemenu-intersect-post.png)

<!--
This will remove everything not in the intersection of two regions.
-->
これは 2 つの領域の交差部分以外のすべてを削除します。


<!--
##### Exclude
-->
##### 重複部分を除去(E) (Exclude)

![](/assets/img/filemenu-exclude-pre.png)
![](/assets/img/filemenu-exclude-post.png)

<!--
This will remove the selected contours from the unselected ones. Only
available in the outline glyph view.
-->
これは選択された輪郭内の領域を選択されていない輪郭から除去します。
アウトライングリフビューでのみ使用可能です。


<!--
##### Find Intersections
-->
##### 交点を見つける(F) (Find Intersections)

<!--
This finds the places where overlapping contours intersect and inserts
points at those locations.
-->
これは重なり合う輪郭同士の交点を見つけ、
そこを通るパスそれぞれに点を追加します。

<!--
##### Simplify
-->
##### 単純化(S) (Simplify)

<!--
Not in the bitmap view. If you have lots of points on a path, some of
which do not materially add to the path's shape, then this command will
remove the extraneous points. (It will not remove points where the slope
at the point is horizontal or vertical as postscript likes to have these
points present).
-->
ビットマップビューでは使用できません。
パス上にたくさんの点があって、
そのうちのいくつかは実質的にはパスの形を指定する役割を果たしていない場合、
このコマンドは無駄な点を取り除きます
(このコマンドは線の傾きが水平または垂直になっている箇所にある点は取り除きません。
PostScript インタプリタではそれがあると都合がいいからです)。

<!--
[How is this done?](pfaeditmath.html#Approximating)
-->
[どうやって処理しているのか?](../../developers/pfaeditmath/#approximating-a-spline)


<!--
##### Simplify More
-->
##### さらに単純化 (Simplify More)

<!--
This is a variant of the simplify command. It brings up a dialog which
gives you control over what sorts of errors this simplification is
allowed to induce. You can control:
-->
これは
<span class="command">単純化(S)</span>
コマンドの変種で、
Shift キーを押しながらメニューを呼び出すと使用できます。
単純化処理によってどういう種類の誤差が生じてもよいかを指定することができるメニューが起動します。
以下の項目が設定可能です:

<!--
- How far the simplified contour is allowed to stray from the original
- Whether to allow removal of extreme points
- Whether to allow the slope to change at points.
- Whether to make corner points into curve points (by adjusting the
  control points)
- Whether to flatten small bumps off of lines
- Whether to try to simplify straight lines at all
-->
- 単純化の結果の輪郭が、オリジナルからどれだけ離れてもいいか
- 極値にある点を取り除いてもいいか
- 端点の所で傾きが変化してもいいか
- (制御点を調節することにより) 角の点を曲線上の点に転換してもいいか 
- 線から飛び出た小さなコブを平滑化するか
- 直線を完全に単純化することを試みるか

<!--
Finally, you may specify whether this set of values should become the
default value for future Simplify commands
-->
最後に、今回使用する値の組を、それ以降に実行する
<span class="command">単純化(S)</span>
コマンド群のデフォルト値とするかどうかを指定することができます。


<!--
##### Cleanup Glyph
-->
##### 不要な曲線を除去(N) (Cleanup Glyph)

<!--
This is a special case of the simplify command. In this case if there is
a spline which actually traces out a line but none the less has control
points, then this command will remove the control points. It will also
cleanup zero length splines.
-->
これは
<span class="command">単純化(S)</span>
コマンドの特殊な場合です。
この場合、実際には直線を描いているのに不要な制御点がある場合、
このコマンドがそれらの制御点を取り除きます。
また、長さ 0 のスプラインを取り除きます。


<!--
##### Canonical Start Points
-->
##### 開始点を正規化(P) (Canonical Start Points

<!--
This will change the start point of the contour (or of all selected
contours) to be the leftmost point on the contour. If there are several
points with the same horizontal coordinate it will pick the one closest
to the baseline. There are two reasons for doing this:
-->
このコマンドは、輪郭の開始点 (または選択された輪郭) を輪郭上の左端の点をに置き換えます。
水平座標が同じ点がいくつかある場合、ベースラインに最も近い点を選択します。
これを行うのには 2 つの理由があります:

<!--
- In a PostScript Type1 or Type2 font it will (usually) reduce the
  size of the code expressing the glyph slightly. (I don't think it
  can increase the code, but there are certainly cases where the
  optimization will have no effect).
- It will enable FontForge to find more reusable bits of code which it
  can put in subroutines
-->
- PostScript Type1 および Type2 フォントでは
  (通常) グリフを表現するコードのサイズを僅かに縮減します。
  (この処理がコードサイズを増やすような場合は無いと思いますが、
  最適化が意味をもたない場合があるのは確かです)。
- FontForge が、再利用可能でサブルーチンに移動できるコード片をより多く発見することができます。

<!--
##### Canonical Contour Order
-->
##### 輪郭の順序を正規化(C) (Canonical Contour Order)

<!--
Order the contours so that the contour with the leftmost point comes
first, then the contour whose leftmost point is a little further right
and so forth. Again, this should decrease the code size slightly in a
Type1 font.
-->
輪郭の順序を並べ替え、最初に左端の点が最初にある輪郭が、
次に左端の点がその次に左側にある輪郭がという具合に並ぶようにします。
これも Type1 フォントのサイズを僅かに縮小するはずです。


<!--
#### Add Extrema
-->
#### 極大点の追加(X) (Add Extrema)

<!--
Not in the bitmap view. Both TrueType and Type1 say that there should be
points on the contour where it reaches its extreme horizontal and
vertical values. In the outline view, if any points are selected, this
will add points at all extrema on splines between selected points. In
the font view, metrics view (or if nothing is selected in the outline
view) it will add extrema to a spline if: 1) The spline is longer than
the em-size/32, or 2) the entire contour (rather than just the current
spline) attains its maximum/minimum value at this point. If the added
extrema is extremely close to an already existing point, fontforge may
remove that point to avoid creating tiny splines.
-->
ビットマップビューでは使用できません。
TrueType と Type1 のどちらでも、
水平および垂直方向の極値にあたる位置に点が存在することを推奨しています。
アウトラインビューでは、
何らかの点が選択されていれば、選択された点の間に存在するすべての極値に点を追加します。
フォントビューおよびメトリックビュー
(または、アウトラインビューで何も選択されていなければ)
以下の 2 条件のいずれかが満たされている極値に点を追加します。
1) スプラインの長さが em / 32 よりも大きい、
2) その点が文字の輪郭全体 (現在のスプラインだけでなく) の極大/極小値に該当する。
もし、追加した点のごく近くに既存の点が位置する場合、
FontForge は微小なスプラインが発生するのを避けるためにその点を削除します。


<!--
#### AutoTrace
-->
#### 自動トレース(R) (AutoTrace)

<!--
This command is only available if you have downloaded Martin Weber's
[autotrace program](http://sourceforge.net/projects/autotrace/), or
Peter Selinger's [potrace](http://potrace.sf.net/). If you have a
background image in a glyph then autotrace will automagically trace the
outlines of that image. See [the section on autotracing](../autotrace/)
for more information.
-->
このコマンドは、
Martin Weber の
[autotrace](http://sourceforge.net/projects/autotrace/) か
Peter Selinger の
[potrace](http://potrace.sf.net/)
のどちらかのプログラムをダウンロードしていないと使用できません。
グリフに背景画像が含まれていると、
自動トレースプログラムが勝手にその画像のアウトラインをトレースしてくれます。
より詳しい情報は、
[自動トレースのセクション](../autotrace/)
を参照してください。


<!--
#### Align menu
-->
#### 点を揃える(L) メニュー (Align menu)

<!--
This submenu is only present in the outline view, it allows you to align
points or to space them out along an axis.
-->
このサブメニューはアウトラインビューだけに存在し、
これを使うと点を座標軸にぴったり沿うように揃えることができます。


<!--
##### Average Points
-->
##### 座標の平均値(A) (Average Points)

<!--
This will look at all the selected points and find the coordinate with
the least change. Then it will average find the median point on that
axis and set all the selected points to have that value for the
appropriate coordinate.
-->
このコマンドは選択中のすべての点を調べ、
値のばらつきが少ない方の座標軸を選択します。
次に、その軸上での平均値を取って中間点を求め、
選択中のすべての点をその平均値に揃えます。

<!--
So if you have a line which is almost horizontal, and select its
endpoints and apply this command it will be horizontal.
-->
ですから、ほとんど水平に並んでいる線がある場合、
その端点を選択してこのコマンドを適用するとその線は水平になります。

![](/assets/img/filemenu-constrain2_1.png)
![](/assets/img/filemenu-constrain2_2.png)

<!--
(if you select exactly two points, and they lie close to a 45 diagonal,
then they will be forced to the diagonal rather than to horizontal/vertical)
-->
(選択した点がちょうど 2 個で、
それらが 45°に近い斜めの関係にある場合は、
水平・垂直ではなく斜め方向に揃えられます)。


<!--
##### Space Points
-->
##### 点の間隔を均等に(S) (Space Points)

<!--
If you have three or more points selected then FontForge will figure out
the coordinate that has the greatest change and will space the points
out regularly along that axis.
-->
3 個以上の点を選択している場合、
FontForge は差が大きいほうの座標軸を選び、
その軸に沿って等間隔に点を分散させます。

<!--
If you select one point (and that point is in the middle of a path)
then (internally) the point's location will be expressed in a coordinate
system which is rotated so that one axis is parallel to the line between
the two points that surround the selected point. The selected point will
be moved mid-way between the two on this axis, while its other
coordinate remains fixed.
-->
点を 1 個だけ選択している場合 (しかもその点がパスの中間にある場合)、
点の位置は (内部的に) 選択した点の両隣の点を結ぶ直線が座標軸に平行になるように回転した座標軸で表現されます。
選択中の点はその軸に沿って 2 点の中間となる位置に移動します。
この時、それに直行する軸方向の位置は固定しています。

<!--
That's an extremely complicated way of saying: If the selected point is
connected to two points which are on a horizontal line, then the
selected point's x coordinate will be midway between the two, while its
y coordinate remains unchanged.
-->
これは非常に複雑な説明方法です:
水平な線上に置かれた 2 個の点の両方に接続した 1 個の点を選択した場合、
選択した点の x 座標は 2 個の点の中間になり、それに対して y 座標は変更されません。

![](/assets/img/filemenu-constrain1_1.png)
![](/assets/img/filemenu-constrain1_2.png)


<!--
##### Space Regions
-->
##### グループ間を均等に(R) (Space Regions)

<!--
This is similar to the above command except that it allows you to make a
rather simple definition of a collection of points which should be moved
together. Each of these regions will be regularly spaced along the
chosen axis. A region is defined as a collection of points, each one of
which is within some maximum distance of at least one other point in the
region. The purpose of this is to allow you to space out the stems of
the letter "m" so that they regularly spaced horizontally. Sadly it
won't work in many cases because in a serifed font the serifs will often
be closer to each other than to their respective stems.
-->
これは上のコマンドと似ていますが、
相対位置を保ちつつ移動したい点のグループをとても簡単に定義することができる点が異なります。
このコマンドは、それらのグループごとの間隔を、選択した座標軸に沿って均等に配置します。
1 個のグループは、その中の点同士がすべてグループ内の他の 1 個以上の点と、
所定の最大距離以内にある点の集まりとして定義されます。
このコマンドの目的は、文字 "m" のステム同士を横方向に均等に配置するような操作を可能にすることです。
残念ながら、これが役に立たない場合は非常に多くあります
(セリフつき書体では、しばしばあるセリフと他のセリフとの間隔のほうがセリフの属するステムとの間よりも狭くなります)。

![](/assets/img/filemenu-spacem_1.png)
![](/assets/img/filemenu-spacem_2.png)


<!--
##### Make Parallel
-->
##### 平行に(<U>P</U>) (Make Parallel)

<!--
If four points are selected, and there are two lines between them, then
FontForge will make those lines parallel. If there are four lines
between them (ie. they form a quadrilateral, then FontForge will turn it
into a parallelogram. (note, this only works on lines, not on curved
splines)
-->
4 個の点を選択中で、それらの間に 2 本の直線が通っている場合、
FontForge はそれらの線が平行になるように点を移動します。
4 本の直線が通っている場合 (つまり、四角形を構成している場合)、
FontForge はそれらを平行四辺形に変形します
(これは直線だけに作用し、曲線のスプラインには作用しないことにご注意ください)。

<!--
The last point selected will be the one moved (sometimes FontForge
doesn't remember which point was selected last, then it will just pick
one randomly. If you don't want that to happen, select your points and
then single click on the one you want moved).
-->
移動するのは最後に選択した線です (FontForge は、どの点が最後に選択されたか覚えていないことがしばしばあります。その時は 1 個をランダムに選びます。これを避けたい場合は、点を選択した後で移動したい点をシングルクリックしてください)。


<!--
#### Round
-->
#### 座標を丸める(D) (Round)


<!--
##### Round to Int
-->
##### 整数値に(I) 丸める (Round to Int)

<!--
Not in the bitmap view. FontForge stores point locations as real numbers
(ie. it retains fractional values). TrueType only supports integral
values (And much of the time you want integral values in Type1 and Type2
fonts also -- using real numbers makes font files bigger), so when
generating the font points are rounded to integral values. This command
will round all selected locations to the closest integer.
-->
ビットマップビューでは使用できません。
FontForge は点の位置を実数として格納しています
(つまり、それらの値には端数が含まれます)。
TrueType は整数値のみをサポートしています
(また、Type1, Type2 の両形式のフォントでもほとんどの場合は整数値が望ましいでしょう
-- 実数値を使用するとフォントファイルが大きくなります)
ので、フォントを出力する時には座標は整数値に丸められます。
このコマンドは、選択した対象の座標値をすべて一番近い整数に丸めます。

<!--
##### Round to Hundredths
-->
##### 1/100単位(H) に丸める (Round to Hundredths)

<!--
Not in bitmap or metrics views. FontForge's Type1 output is limited to
hundredths of an em-unit, even when rounding is turned off in the
Generate [Options] dialog.
-->
ビットマップビューとメトリックビューでは使用できません。
FontForge の Type1 出力の精度は、
出力ダイアログの
<span class="command">オプション</span>
で、
整数への丸めを off にした場合でも、
em 単位の 1/100 に限られています。

<!--
##### Round to Cluster
-->
##### 近い値をまとめる(C) (Round to Cluster)

<!--
Occasionally you want to make sure that coordinates which are close
together have the same value. This command will do that.
-->
ときどき、非常に近い座標値を確実に同じ値にしたいことがあります。
このコマンドはそれを行います。

<!--
#### Order
-->
#### 順序 (Order)

<!--
This changes the order in which contours, references and images are
drawn. It is almost useless because this order of contours and
references does not affect the final appearance of the glyph. The only
relevance it has is when interpolating fonts and in multiple master
fonts. Here similar contours must appear in the same order.
-->
このコマンドはどの順番で輪郭・参照と画像を描画するかを変更します。
この輪郭と参照の順序はグリフの形に影響しないので、
ほとんどの場合は意味がありません。
関係がある唯一の場合は、
フォントを補間する場合とマルチプルマスターフォントの場合です。
そのときは、同等の輪郭が出現する順番は同じでなければなりません。

<!--
If you have a glyph which contains both contours and references,
FontForge does not specify whether references or contours are drawn
first (or whether the two are intermixed). If this matters to you,
unlink your references.
-->
輪郭と参照の両方を含むグリフがある場合、
FontForge が参照と輪郭のどちらを先に描くか
(それとも 2 つを混ぜこぜに描画するか)
を指定することはできません。
これが問題になる場合は、参照のリンクを解除してください。

<!--
#### Clockwise
-->
#### 時計回り(O) (Clockwise)

<!--
Only in the outline view. If all selected paths have a clockwise
direction then this will be checked. Selecting it will make all paths be
clockwise.
-->
アウトラインビューでのみ使用可能です。
選択中のパスが時計回りの方向をもつ場合、
ここにチェックがつきます。
このメニューを選ぶと、それらすべてのパスが時計回りに変更されます。

<!--
If not paths are selected, or if all selected paths are open this will
be greyed out. I a selected path intersects itself results are
indeterminate.
-->
選択中のパスがない場合、
または選択中のパスがすべて開いたパスである場合、
このメニューは灰色表示で選択できません。
選択中のパスに自己交差しているものがある場合、
結果がどうなるかは不定です。

<!--
#### Counter-Clockwise
-->
#### 反時計回り(N) (Counter-Clockwise)

<!--
Only in the outline view. If all selected paths have a counter-clockwise
direction then this will be checked. Selecting it will make all paths be
counter-clockwise.
-->
アウトラインビューでのみ使用可能です。
選択中のパスが反時計回りの方向をもつ場合、
ここにチェックがつきます。
このメニューを選ぶと、それらすべてのパスが反時計回りに変更されます。

<!--
If not paths are selected, or if all selected paths are open this will
be greyed out. I a selected path intersects itself results are
indeterminate.
-->
選択中のパスがない場合、
または選択中のパスがすべて開いたパスである場合、
このメニューは灰色表示で選択できません。
選択中のパスに自己交差しているものがある場合、
結果がどうなるかは不定です。

<!--
#### Correct Direction
-->
#### アウトラインの向きを修正(C) (Correct Direction)

<!--
Not in the bitmap view. Sets the direction of outermost paths to be
clockwise. The next path crossed will be made counter-clockwise, the
next clockwise, etc.
-->
ビットマップビューでは使用できません。
一番外側のパスの向きを時計回りに設定します。
次に交差するパスを反時計回りに、
次を時計回りに、のように設定します。

<!--
This command may produce unexpected results if two splines cross.
-->
このコマンドは、2 本のスプラインが交差している場合、
予想外の結果を生じることがあります。

<!--
If a glyph contains a flipped reference, this command will be unable to
correct the contours inside of the reference directly, instead it will
offer to unlink the reference after which it can treat its (former)
contours like any others.
-->
グリフに反転した参照が含まれている場合は、
このコマンドでは参照に含まれる輪郭を直接修正することはできません。
その代りに、参照のリンクを解除するかどうかを尋ねるので、
解除した後はその (以前の) 輪郭を他の輪郭と同様に扱うことができるようになります。


<!--
#### Insert Text Outlines...
-->
#### テキストの挿入 (Insert Text Outlines...)

<!--
Upon occasion it is useful to be able to insert text into a glyph. The
[Insert Text Dialog](../InsertTextDlg/) lets you do this.
-->
場合によっては、
グリフにテキストを挿入できると便利です。
[<span class="command">テキストの挿入</span> ダイアログ](../InsertTextDlg/)
でこれを行うことができます。


<!--
#### Build
-->
#### 構築 (Build)


<!--
##### Build Accented/Composite Glyph
-->
##### アクセントつきグリフ(B)/複合グリフを構築(C) (Build Accented/Composite Glyph)

<!--
Not in the bitmap view.
-->
ビットマップビューでは使用できません。

<!--
The first menu item will only build accented letters, the second will
build general composite glyphs (fractions, ligatures, digits inside
parens, roman numerals, etc.) as well.
-->
前者のメニュー項目はアクセントつき文字を組み立てるだけです。
後者では、一般的な複合グリフ
(分数、合字、括弧つき数字、ローマ数字など)
を組み立てることもできます。

<!--
If the current glyph is an accented glyph (and all the base glyphs and
accents have already been created) then this command will delete
anything that is currently in the foreground and put a reference to the
base glyph and another reference to the accent glyph into the
foreground. So if the current glyph were "À" then a reference to "A"
would be added to it, and a reference to "\`" would be centered above
the "A".
-->
現在のグリフがアクセントつきグリフであれば
(なおかつ基底グリフとアクセントが既に作成してあれば)、
このコマンドはグリフの前面に含まれている内容をすべて削除し、
基底グリフに対する参照と、
アクセントのグリフに対するもう一つの参照を前面に配置します。
例えば、現在のグリフが "À" であれば、
"A" への参照がそのグリフに追加され、
"\`" への参照が "A" と中心を合わせて配置されるでしょう。

<!--
If the current glyph is something like "agrave.sc" then it will be
built using the rules of "agrave" but with ".sc" variants. So
"agrave.sc" would contain "a.sc". For accents it will use "grave.sc" if
it exists and "grave" if it does not.
-->
現在のグリフが "agrave.sc" のようなものである場合、
"agrave" のルールを使用して構築されますが、".sc" バリアントが用いられます。
したがって、
"agrave.sc" には "a.sc" が含まれます。
アクセントについては、存在する場合は "grave.sc" を使用し、
存在しない場合は "grave" を使用します。

<!--
If [Copy From](../editmenu/#Copy.From) is set to All Fonts then any bitmaps
will have a similar process done -- that is bitmap references will be
created (even in the outline glyph view).
-->
もし
[<span class="command">コピー元の指定(F)</span>](../editmenu/#Copy.From)
が「すべてのフォント」に設定されていると、
すべてのサイズのビットマップに対して同じ処理を行います
(アウトラインビューで実行した場合も行います)。

<!--
A more complete description is given in the section on
[accented glyphs](../accented/).
-->
より完全な説明は、
[アクセントつきグリフ](../accented/)
に関するセクションにあります。

<!--
##### Build Duplicate
-->
##### 複製グリフを作成(D) (Build Duplicate)

<!--
Only in the font view.
-->
フォントビューでのみ使用可能です。

<!--
Consider the letters "Alpha" and "A". Often these may be represented by
the same glyph. This command which change the encoding slightly so that
the encoding for U+0391 will refer to the glyph named "A". Note that
this is subtly different from refering to a glyph named "Alpha" which
refers to another glyph named "A".
-->
文字 "Alpha" と "A" を考えてみましょう。
これらはしばしば同一のグリフで表現されます。
このコマンドはエンコーディングを微調整して、
U+0391 の文字コードが "A" という名前のグリフを指し示すようにします。
これは、"Alpha" というグリフが "A" という別のグリフを参照するのとは微妙に異なることに注意してください。

<!--
Adobe suggests that you use a reference rather than giving to unicode
code points to one glyph, but it is part of the font format.
-->
Adobe は、1 個のグリフに複数の符号位置を割り当てるのではなく、
参照を使用するべきであると示唆していますが、
この方法はフォントフォーマットに違反しているわけではありません。


<!--
#### Merge Fonts...
-->
#### フォントの統合(M)... (Merge Fonts...)

<!--
Only in the font view. If you are building a unicode font you will often
want to merge in other fonts. You can, of course, cut and paste from one
to the other, but that can be tedious, while this command will do it all
in one fell swoop.
-->
フォントビューでのみ使用可能です。
Unicode フォントを作成している時には、
他のフォントに併合したくなることがよくあるでしょう。
もちろん、他のフォントからカット&ペーストをすれば可能ですが、
たいへん手間がかかるでしょう。
それにひきかえ、このコマンドはすべてを一撃で片付けてしまいます。

<!--
FontForge does the following when merging CID-keyed fonts:
-->
FontForge は、CID フォントを統合する時には以下の処理を行います。

<!--
-   If the font in the window (the mergee) is a normal font and the
    other font (the merger) is a CID keyed font, then the merger font is
    effectively flattened and the result merged into the mergee.
-   If the mergee is a CID keyed font and the merger font is a normal
    font then the merger font will be merged into whichever of the
    mergee's subfonts is currently active.
-   If both are CID keyed fonts, then they should:
    -   Have the same registry and ordering
    -   The supplement number of the mergee should be at least as big as
        that of the merger
    -   The mergee should have at least as many subfonts as the merger.

    If these conditions be met then any CIDs from the merger which are
    not present in the mergee will be merged into the same subfont of
    the mergee as they came from in the merger.

    This strikes me as somewhat problematic, but I can't think of a
    better solution.
-->
-   ウィンドウ内のフォント (統合する先) が通常フォントで、
　　　　もう片方のフォント (統合対象) が CID フォントの場合、
    統合対象のフォントは事実上単一化され、
    その結果が統合先に送られて統合されます。
-   統合先が CID フォントで統合対象が通常フォントの場合、
    統合先フォントのサブフォントのうち、
    現在アクティブになっているものに統合対象フォントが送られます。
-   両方が CID フォントの場合、
    以下の条件を満たしていなければなりません:
    -   CID レジストリとグリフ集合が同じである
    -   統合先の補遺番号が最低でも統合対象の番号と等しい
    -   統合先のサブフォントの個数が最低でも統合対象のサブフォントの個数と等しい

<!--
FontForge will also copy advanced typographic features, kerning,
ligatures, etc.
-->
FontForge は高度タイポグラフィ機能、カーニング、合字などもコピーします。

<!--
If one of the two glyphs of a kerning pair is in the mergee and the
other in the merger then you will be given the option of either ignoring
this kerning pair or adding it to the resultant font. This happens if
both the mergee and the merger contain a glyph, and the kerning pair is
in the merger font -- if that glyph is the same in both fonts then you
would want to include the kerning pair, but if it differs then you
probably don't.
-->
カーニングペアの 2 つのグリフの一方が統合先にあり、
他方が統合元にある場合、
このカーニングペアを無視するか、
結果のフォントに追加するかの選択肢が与えられます。
これは、統合先と統合元の両方にグリフが含まれ、
カーニングペアが統合元フォントにある場合に発生します
-- そのグリフが両方のフォントで同じである場合、
カーニングペアを含めますが、異なる場合はおそらく含めません。


<!--
#### Interpolate Fonts...
-->
#### フォントの補間(L)... (Interpolate Fonts...)

<!--
Only in the font view. If you have a bold font and a light font and
would like to create a medium font, then you can interpolate a font
between the two (or you can extrapolate a font that's even bolder or
lighter). Your two fonts must have the same sets of glyphs, and each
glyph must have the same number of paths (ordered similarly) and each
path must have the same number of points on it, and must have the same
references.
-->
フォントビューでのみ使用可能です。
ボールドとライトの 2 つのウェイトのフォントがあってそれらを元にミディアムフォントを作成したい場合、
2 個の間の中間フォントを補間によって作成することができます
(または、さらに太いフォントや細いフォントを補外して作ることもできます)。
その 2 つのフォントは同じグリフのセットを含み、
各フォントに同じ個数のパスを含み
(同じ順序で並んでいて)
各パスには同じ個数の点を含んでいなければならず、
含んでいる参照も同じでなければなりません。

<!--
Examples: If you are interpolating from a light font to a bold one, then
a medium font might be 50% between the two, an extra-bold font might be
200% and a thin one -100%.
-->
例: ウェイトが light のフォントから bold のフォントへの補間を行った場合、
medium のフォントは 2 つの中間の 50% にあたり、
extra-bold のフォントは 200% に、
thin は -100% になるでしょう。


<!--
#### Compare Fonts...
-->
#### フォントを比較... (Compare Fonts...)

![](/assets/img/filemenu-fontcompdlg.png)

<!--
Sometimes it is useful to compare two versions of a
font and see what has changed. This command will allow you to check:
-->
時には、あるフォントの 2 つのバージョンを比較して、
どこが変更されたかを確認できると便利なことがあります。
このコマンドでは以下の変更をチェックすることができます:

<!--
- The addition or removal of glyphs
- Changes to outline glyphs
- Changes to bitmap glyphs
- Changes to the font's names (truetype 'name' table and some
  postscript names)
- Changes to the font's glyph substitutions (ligatures and whatnot)
- Changes to the font's glyph positioning (kerning and whatnot)
-->
- グリフの追加または削除
- アウトライングリフの変更
- ビットマップグリフの変更
- フォント名の変更 (TrueType の 'name' テーブルといくつかの PostScript 名)
- フォントの含むグリフ置換 (合字だの何だの) の変更
- フォントの含むグリフ位置指定 (カーニングだの何だの) の変更

<!--
You can also use it to compare truetype and postscript versions of the
same font. Normally fontforge checks to make sure all the splines match
exactly, but you can also have it test whether a contour in one font is
always close to the similar contour in another font, or whether a
contour in one font is inside a reference in another (these are common
when comparing PostScript fonts where the format loses references).
-->
同じフォントの TrueType 版と PostScript 版の比較をすることもできます。
通常は FontForge はすべてのスプラインが完全に一致するかどうかを確かめるための検査を行いますが、
これを使って、片方のフォントが常にもう片方のフォントの同等な輪郭とどこでもほぼ一致するかどうか、
または片方のフォントに含まれる輪郭がもう片方のフォント内の参照に含まれているか
(これは、フォーマットが参照を含まない PostScript フォントを比較する時によく起こります)
を検査することもできます。

<!--
Comparing PostScript hintmasks is another somewhat iffy topic. There are
often many equivalent (I think) hint mask possibilities, but I don't
have a good algorithm for saying that they are equivalent -- especially
since Adobe uses hints in ways which I find unexpected.
-->
PostScript のヒントマスクの比較もまた、どこと無くあやふやな所のある問題です。
(私の考えでは) 等価なヒントマスクを表現する多くの方法が可能であることがしばしばありますが、
それらが等価であると示すいいアルゴリズムがありません
-- 思いもよらないようなヒントの使い方を Adobe がしていることに気づいてからはなおのことです。

<!--
Finally you can have it place the outlines of each differing glyph from
the second font into the background of the corresponding glyph in the
first font. This can be helpful in correcting discrepancies.
-->
そして最後に、比較先のフォントと比較元のフォントで異なるグリフのそれぞれに対し、
比較先のフォントの欠落したグリフを比較元のフォントの対応するグリフの背景に配置することができます。
これは、矛盾点を修正するのに役立つでしょう。

![](/assets/img/filemenu-fontcompresults.png)


<!--
#### Compare Layer To Layer...
-->
#### レイヤとレイヤの比較 (Compare Layer To Layer...)

<!--
Only available in the Outline and Font Views. This command allows you to
specify two layers within the current font and then checks that they are
similar. In the outline view a message box pops up to say if the layers
are the same or different. In the Font View, the view will scroll to the
first glyph whch differs, all differing glyphs will be selected and a
message box pops up.
-->
アウトラインビューとフォントビューでのみ使用できます。
このコマンドを使用すると、現在のフォント内の 2 つのレイヤーを指定して、それらが類似していることを確認できます。
アウトラインビューで、レイヤーが同じか異なるかを示すメッセージボックスが表示されます。
フォントビューでは、ビューは最初の異なるグリフまでスクロールし、
異なるグリフがすべて選択され、メッセージボックスがポップアップ表示されます。
