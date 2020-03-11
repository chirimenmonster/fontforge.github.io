---
published: true
layout: default.ja
title: CID メニューと CID キー指定フォント
---
<!--
published: true
layout: default
title: The CID Menu and CID keyed fonts
-->


<!--
The CID Menu provides a few commands for manipulating CID keyed fonts.
If the current font is a CID keyed font the menu also includes a list of
all subfonts that make up this one. This menu is only available in the
font view.
-->
CID メニューには、CID フォントを操作するための少数のコマンドがあります。
現在のフォントが CID フォントの場合、
このメニューにはその構成部品であるサブフォントすべてを含むリストもメニューに含まれます。
このメニューはフォントビューでのみ使用可能です。

[table_of_contents]


<!--
### Er... What is a CID keyed Font?
-->
### あのー CID キー指定フォントって何ですか? (Er... What is a CID keyed Font?)

<!--
A CID keyed font is a postscript (or opentype) font designed to hold
Chinese, Japanese and Korean characters efficiently. More accurately a
CID font is a collection of several sub-fonts each with certain common
features (one might hold all the latin letters, another all the kana, a
third all the kanji). This allows font-wide hinting to be crafted for
subsets of glyphs to which have something in common.
-->
CID キー指定フォントは、
中国語、日本語および韓国語の文字を効率的に格納できるように設計された
PostScript (または OpenType) フォントです。
より正確に言えば、
CID フォントはいくつかの共通の特徴をもつサブフォント
(そのうちの 1 つはラテン文字だけを含んでいるでしょうし、
別の 1 つは仮名ばかり、3 つ目は漢字ばかりという具合です)
の集まりです。
これにより、フォント単位のヒント指定を、
共通点をもつグリフのサブセットに合わせてあつらえることができます。

<!--
CID keyed fonts do not have an encoding built into the font, and the
glyphs do not have names. Instead the font is associated with a glyph
set and on each glyph set there are several character mappings defined.
These mappings are similar to encodings but allow for a wider range of
behaviors.
-->
CID キー指定フォントにはエンコーディングが組み込まれておらず、
グリフに名前がつけられてもいません。
その代り、フォントは特定のグリフセットに結びつけられており、
各グリフセットごとに複数の文字セットへの対応づけが存在します。
これらの対応づけはエンコーディングと似ていますが、
より広い範囲のふるまいが可能になっています。

<!--
A CID is a glyph index and is used to look up glyph descriptions instead
of glyph names in other types of fonts. Using a glyph set FontForge will
often be able to map a CID to a unicode character name (but not always),
so FontForge will give glyphs names when it can.
-->
CID はグリフのインデックスで、
このグリフ番号は、他のタイプのフォントで用いられているグリフ名の代りにグリフ記述を参照するのに用いられています。
FontForge は多くの場合文字セットを使用して
CID を Unicode の文字名に対応づけることができます
(が、いつもではありません)。
そのため、FontForge は可能なときだけグリフの名前を表示します。

<!--
For more information see the [section on CID keyed fonts on the font
view page](../fontview/#CID).
-->
より詳しい情報については、
フォントビューのページの
[CID キー指定フォントに関するセクション](../fontview/#CID)
を参照してください。


<!--
#### Convert to CID
-->
#### CIDに変換 (Convert to CID)

<!--
If the current font is not a CID font then this command will convert it
into one containing one subfont (with the glyphs in this font). You will
be prompted for a glyph set.
-->
現在のフォントが CID フォントでない場合、
このコマンドはそれを 1 個の (このフォントにあるグリフを含む) サブフォントからなる CID フォントに変換します。
文字セットを入力するように促されます。


<!--
#### Convert By CMap
-->
#### CMapを指定して変換 (Convert By CMap)

<!--
If the current font is not a CID font then this command will convert it
into one containing a single subfont. You will be prompted for an Adobe
CMap file.
-->
現在のフォントが CID フォントでない場合、
このコマンドはそれをサブフォントを 1 個だけ含む CID フォントに変換します。
Adobe CMap ファイルを選択するように促されます。


<!--
#### Flatten
-->
#### 単一化< (Flatten)

<!--
If the current font is a CID font then this command will convert it into
a normal (flat) font by taking all the glyphs from all the sub-fonts and
merging them into one normal font. The new font should be in the same
order as the CID font (ie. ordered by CID). After this operation you may
re-encode it into whatever encoding is appropriate.
-->
現在のフォントが CID フォントの場合、
このコマンドはそれに含まれるすべてのサブフォントからすべてのグリフを取り出し、
単一の通常フォントにまとめることにより、
通常の (階層構造のないフラットな) フォントに変換します。
新しいフォントはその CID フォントと同じ順序を保っているはずです
(つまり、CID 順に並んでいるはずです)。
この操作の後、符号化方式ををどれでも適当なものに変更することができます。


<!--
#### Flatten By CMap
-->
#### 指定したCMapで単一化 (Flatten By CMap)

<!--
If the current font is a CID font then this command will convert it into
a normal font. It prompts you for an Adobe CMap file and uses that to
define an encoding for the resultant font.
-->
現在のフォントが CID フォントの場合、
このコマンドはそれを通常のフォントに変換します。
Adobe CMap ファイルを指定するように促し、
それを作成結果のフォントのエンコーディングを定義するのに使います。


<!--
#### Insert Font
-->
#### フォントを挿入(O) (Insert Font)

<!--
Will allow you to browse for a normal font which will be added as
another sub font to the current CID font.
-->
現在の CID フォントに別のサブフォントとして追加される通常フォントを一覧から選択することができます。


<!--
#### Insert Blank
-->
#### 空のフォントを挿入(B) (Insert Blank)

<!--
Inserts a blank sub-font into the current CID font.
-->
現在の CID フォントに空のサブフォントを挿入します。


<!--
#### Remove Font
-->
#### フォントを削除(R) (Remove Font)

<!--
Removes the current font from the CID font. Anything in it will be lost.
(If you want to save it first then use Generate Font and save it as a
pfb file (or any other simple format).
-->
現在のフォントを CID フォントから削除します。
その中に含まれるデータはすべて失われます。
(それを保存したい場合はまず
<span class="command">フォントを出力(G)</span>
を使用して、pfb ファイル (か他の単純なフォーマット) で保存してください)。


<!--
#### Change Supplement...
-->
#### 補遺の変更 (Change Supplement...)

<!--
Displays the Registry/Ordering information of the font and allows you to
change the Supplement level.
-->
フォントの　Registry/Ordering の情報を表示し、
Supplement レベルを変更できます。


<!--
#### CID Font Info
-->
#### CID フォント情報(I) (CID Font Info)

<!--
This allows you to provide information on the entire collection of
subfonts rather than just the current subfont. It provides access to the
standard [font info dialog](../fontinfo/).
-->
これを使うと、現在のサブフォントではなく、サブフォントの集まりである CID フォント全体の情報を得ることができます。
このコマンドは標準の
[フォント情報ダイアログ](../fontinfo/)
と同じ方法で情報にアクセスできます。


<!--
#### (sub font name)
-->
#### (サブフォント名) (sub font name)

<!--
Clicking on a different sub font name in the menu will cause that
sub-font to be displayed instead of the current one.
-->
メニューにある別のサブフォント名をクリックすると、現在のフォントの代りにそのサブフォントが表示されます。
