---
published: true
layout: default.ja
title: フォントビュー
---

__Contents__

<!--
*    [Overview](#overview)
*    [Encodings and Character Sets](#encodings-and-character-sets)
*    [CID keyed fonts](#cid-keyed-fonts)
*    [Multiple Master Fonts](#multiple-master-fonts)
*    [Vertical Metrics](#vertical-metrics)
-->
*    [概要](#概要)
*    [エンコーディングと文字集合](#エンコーディングと文字集合)
*    [CID キー指定フォント](#cid-キー指定フォント)
*    [マルチプルマスターフォント](#マルチプルマスターフォント)
*    [縦書きメトリック](#縦書きメトリック)

<!--
### Overview
-->
### 概要
![Sample image of a font seen in Font View](/assets/img/windows-ambrosiafv.png "Font View sample")

<!--
The font view is a list of all the glyphs available in the given font.
-->
フォントビューは、あるフォントに含まれる全てのグリフをアクセスできるリストです。

<!--
You may chose to display it at various sizes, by default it will be
displayed with the outline font rasterized on a 24 pixel em square. You
may display it at 36, 48, 72 and 96 pixel sizes as well. You may also
choose to look at an anti-aliased greymap (the above image is
anti-aliased). These are slower to generate but look nicer
([Comparison](../AA-Comparison/)).
-->
文字表示をさまざまなサイズから選択できます。
デフォルトでは、em 正方形を24 ピクセルでラスタライズします。
36, 48, 72 および 96 ピクセルを選ぶこともできます。
文字をアンチエイリアスされたグレイマップで表示するかを選ぶこともできます (上の図は、アンチエイリアス表示されています)。
アンチエイリアスを行うと表示は遅くなりますが、見栄えは良くなります ([比較](../AA-Comparison/))。

<!--
If you have an encoding slot which has nothing in it (as opposed to an
encoding which maps to a space glyph) then that will be shown by a faint
red X drawn across the box.
-->
ある符号位置に何も割り当てられていない場合、(空白文字に割り当てられた文字符号と異なり)
鈍い赤色の×字形がマスの中央に表示されます。

<!--
Above each image of the glyphs in the font is a label indicating the
glyph in some conventional format. Usually this is just a small image of
the glyph in a standard font (as it is above), but you can change it to
show the glyph's name, unicode code point or encoding (in hex). In small
views (24 pixel view for instance) there may not be room for the entire
label, and it will appear truncated.
-->
フォント内の各グリフの画像の上には、グリフをある伝統的な書式で表示しているラベルがあります。
通常はこれは単に、標準フォントで表示した小さなグリフの画像です (上の図のように) が、
グリフ名や Unicode のコードポイントまたはエンコーディングを (16 進数で) 表示するように変更することができます。
小さなビューでは (例えば 24 ピクセル表示では)ラベル全体を表示する余地がないので、それらは切り詰められるでしょう。

![Close-up of glyphs with red and blue bars](/assets/img/windows-fvOutOfDateHinting.png "The instructions for glyph A are out of date. Glyph B has changed.")

<!--
If a glyph has been changed since it was last hinted (PostScript), or if
a glyph contains contours but has no instructions (TrueType), then its label
will be edged with blue bars. If the glyph has out of date instructions
(TrueType), then its label will be edged with red.
-->
あるグリフに最後の (PostScript) ヒントを付け加えた後にグリフを変更しているか、
グリフに輪郭が含まれているのに (TrueType) 命令が含まれていないならば、
そのラベルは青い枠線で縁取り表示されます。
グリフの (TrueType) ヒントが今のアウトラインよりも古いものであれば、
ラベルは赤い枠線で縁取り表示されます

<!--
If one of your glyphs has something in its background layer then this
will be indicated visually (currently by darkening the background of the
glyph label).
-->
グリフが何らかの背景レイヤを持っている場合、それは視覚的に表されます
(現在はグリフラベルの背景を暗くすることによって表しています)

<!--
Normally the view will display the foreground layer of the font, but you
may change it to display any layer (other than the background layer)
with `View->Layers->?`
-->
通常、ビューはフォントの前景レイヤーを表示しますが、
<span class="command">表示(V)-\>レイヤ-\>?</span>
で（背景レイヤー以外の）任意のレイヤーを表示するように変更できます。

<!--
You may also display any of the bitmap fonts you have generated from the
outline glyphs. Simply go to the View menu and select the one you want.
-->
また、グリフアウトラインから生成した全てのビットマップフォントを表示することができます。
<span class="command">表示(V)</span>
メニューから見たいサイズのビットマップを選んでください。

<!--
If you look at a bitmap version of the font, and it does not contain a
glyph for which there is an outline glyph (ie. the font needs its
bitmaps regenerated) then the missing glyph will be outlined in red to
bring it to your attention more easily.
-->
フォントのビットマップ版を見るとき、グリフアウトラインがあるのにビットマップが含まれていない
(つまり、ビットマップを再生成する必要がある) とき、
存在しないビットマップグリフは、注意をひきやすくするために赤い枠で囲んで表示されます。

<!--
Small bitmap fonts will be magnified. If the pixelsize of the font is
less than 10 it will be shown 3 times normal size, if less than 20 twice
normal size.
-->
小さなビットマップフォントは拡大表示されます。
フォントのピクセルサイズが 10 未満のときは通常サイズの 3 倍で、20 未満のときは通常サイズの 2 倍で表示されます。

<!--
Underneath the menu bar is some information on the last glyph selected.
First is the encoding of the glyph in the current font expressed in
decimal. Next is the unicode code point for the glyph (or ???? if it is
not a unicode character). Next the postscript name for the glyph, and
finally the unicode name. Not all unicode characters will have unicode
names (the CJK characters do not for example)
-->
メニューバーの直下には、最後に選択したグリフに関連する情報が表示されます。
まず現在のフォントにおけるグリフのエンコーディングが 10 進数で表示されます。
次はそのグリフの Unicode のコードポイントです (Unicode 文字でない場合、???? と表示されます)。
その次はそのグリフの PostScript 名で、最後が Unicode 名です。
全ての Unicode 文字が Unicode 名を持つわけではありません (例えば、CJK 文字は持っていません)。

<!--
If you move the cursor to a glyph and let it rest there a small popup
window will appear containing information about that glyph. If you
depress the control key then this window is locked in place until you
move the mouse.
-->
カーソルをあるグリフの上に持って行ってしばらく待つと、そのグリフに関する情報を含む小さなポップアップウィンドウが表示されます。
Control キーを押しておくと、マウスを移動するまでそのウィンドウはその場に固定されます。

<!--
You may display metrics lines (baseline, origin and advance width) in
the font view. (View -\> Show H Metrics). If you do so, I suggest
viewing the font at a large pixel size, otherwise the window looks too
confusing.
-->
フォントビューで、メトリックの補助線 (ベースライン, 原点と送り幅) を表示することができます
(<span class="command">View(V)-\>横書きメトリックの表示方法(H)...</span>)。
これを行うときには、フォントを大きなピクセルサイズで表示することをお勧めします。
さもないとウィンドウはごてごてして見にくくなります。

<table class="table" border>
    <tr>
        <td>
            <img src="/assets/img/windows-FVHMetrics.png" alt="Sample of a glyph with horizontal metrics shown">
        </td>
        <td>
            <img src="/assets/img/windows-FVVMetrics.png" alt="Sample of a glyph with vertical metrics shown">
        </td>
    </tr>
    <tr>
        <td>
<!--
A 96 pixel display showing the various horizontal metric lines.<br />
 The blue line is the baseline<br />
 The small red tick on the left marks the glyph origin.<br />
 The green line on the right shows where the advance width is while the
bottom green line shows how long it is. (normally you will not display
both at once)<br />
 The glyph is centered horizontally, and the font ascent is the top of
the box displaying it, while the descent is the bottom.
-->
横書きメトリックの各種の補助線を 96 ピクセルで表示しているところ。<br />
 青い線はベースライン。<br />
 左にある赤い小さな縦棒はグリフの原点を表す。<br />
 右側にある緑色の線は字送りの位置を表し、画面下の緑色の線は送り幅を表す。
 (ふつうは両方同時に表示する必要はないはず)<br />
 グリフは幅の中央に配置されており、このフォントの高さは表示枠の上端に、
 深さは表示枠の下端に相当する。
        </td>
        <td>
<!--
A 96 pixel display showing the various vertical metric lines.<br />
 The blue line down the center is the vertical baseline.<br />
 The red bar at the top (over writing the ascent line) is the vertical
origin.<br />
 The green line at the bottom shows where the vertical advance is while
the green line on the right shows how long it is. (normally you will
not display both at once)
-->
縦書きメトリックの各種の補助線を 96 ピクセルで表示しているところ。<br />
 中央に引かれた青い垂直線は縦書きのベースライン。<br />
 上の小さな赤い横棒 (高さを表す線に重なる) はグリフの原点を表す。<br />
 下にある緑色の線は字送りの位置を、右にある緑色の線は送り幅を表す。
 (ふつうは両方同時に表示する必要はないはず)
        </td>
    </tr>
</table>

<!--
You may select any number of glyphs in the font by dragging through
them. You may use shift-click to select (or deselect) additional glyphs.
You may also use the arrow keys to move around (and shift-arrow to
select). To some extent the order you select glyphs in will be
remembered and a few commands will make use of that.
-->
フォントビューの上でドラッグすることにより、フォント内のグリフをいくらでも同時に選択することができます。
Shift キーを押しながらクリックすることによりグリフを追加選択 (または選択解除) することができます。
矢印キーを選択グリフの移動に使うことも可能です (範囲指定には Shift＋矢印キーが使えます)。
グリフを選択した順番はある程度記録され、いくつかのコマンドは操作の時にそれを使用します。

<!--
You may drag and drop selected glyphs into
-->
選択したグリフは、以下の場所にドラッグ&amp;ドロップすることができます。

<!--
* The metrics view

    Where they will be inserted into the display before the selected glyph
    (selected in the metrics view) in the order in which you selected them
    in the font view.
-->
* メトリックビュー

    この場合、グリフはフォントビューで選択された順番を保って、
    画面上の選択されたグリフ (メトリックビューでの選択グリフ) の前の位置に挿入されます。

<!--
* The outline view

    Where they will appear as references
-->
* アウトラインビュー

    この場合、それらの文字は参照として表示されます。

<!--
* The glyph info substitutions/ligature dlg

    Where they will appear as a substitution or ligature.
-->
* グリフ情報ウィンドウの <span class="command">置換/合字</span> ダイアログ

    この場合、それらの文字は置換または合字として表示されます。

<!--
The [Tab] key will move to the next glyph with something in it, and
Shift-[Tab] will move to the previous glyph with something interesting.
-->
[Tab] キーを押すと、何らかのデータが含まれている次のグリフに移動し、
Shift + [Tab] キーで、有効なデータのある前のグリフに移動します。

<!--
You can perform various operations on the selected glyphs:
-->
選択されたグリフに対し、以下のような様々な操作を行うことができます。

<!--
-   Apply a general transformation (ie. move 20 units right and then
    rotate 180&deg;)
-   Expand all paths to be stroked paths
-   Clean up areas where several paths intersect
-   Simplify paths
-   Build Accented Characters
-   Regenerate bitmaps
-   Autohint
-   Control various metrics settings
-->
-   一般的な変換操作を適用する (例: 20 ユニット右に移動してから180°回転する)
-   全てのパスをペンで描いた線に変換する
-   いくつかのパスが交差する領域を整理する
-   パスを単純化する
-   アクセントつき文字を構築する
-   ビットマップを再生成する
-   自動ヒントづけを行う
-   各種のメトリック設定を制御する

<!--
And, of course, you can cut and paste. Normally copying a glyph will
copy that glyph and any bitmaps associated with it, but you can use the
Edit-\>Copy From menu item to change this so that only entries from the
currently displayed font are copied. So if a 12 pixel font is being
displayed then only the bitmaps from the 12 pixel bitmap font will be
copied in this mode. Cut and Clear will clear those things which would
be copied.
-->
もちろん、それに加えて、カット&amp;ペーストを行うことができます。
通常、あるグリフをコピーするとそのグリフおよび付随するビットマップを全てコピーしますが、
<span class="command">編集(E)-\>コピー元の指定(F)</span>
の項目選択で、
現在表示されているフォントだけをコピーするように変更することができます。
それにより、例えば 12 ピクセルフォントが表示されているときは、
そのモードでは 12 ピクセルのビットマップフォントだけがコピーされます。
<span class="command">切り取り(T)</span>
と
<span class="command">クリア(L)</span>
は、コピーの対象となるデータを取り除きます。

<!--
Paste is a little more complicated. In general it will paste whatever is
in the clipboard, regardless of the copy mode. So if the clipboard
contains a 12pixel bitmap and the font view is displaying outlines, then
pasting it will paste it into the 12pixel font none the less. There is
one exception to this. If the clipboard contains a 12 pixel bitmap and
the font view is currently display a 17pixel bitmap then the paste will
go into the displayed bitmap.
-->
<span class="command">貼り付け(P)</span>
はやや複雑です。
一般的に、クリップボードにある物はコピーモードに関係なくすべて貼り付けられます。
そのため、クリップボードに 12 ピクセルのビットマップが含まれている場合、
フォントビューがアウトラインを表示していたとしても、
貼り付けを行うと 12 ピクセルフォントのデータが書き換えられます。
この動作には一つ例外があります。
クリップボードに 12 ピクセルのビットマップフォントが含まれていて、
フォントビューが現在 17 ピクセルのビットマップを表示しているような場合、
貼り付けられたデータは現在表示中のビットマップに置かれます。

<!--
A Paste from the font view will delete whatever splines were in the
glyph beforehand (while a paste in the outline glyph view will merge the
new set of splines with the old). Paste from the font view will also set
the width of the glyph.
-->
フォントビューへの貼り付けを行うと、
そのグリフに以前含まれていたスプラインは完全に削除されます
(アウトライングリフビューへの貼り付けでは以前あったスプラインデータへの追加を行う点が異なります)。
フォントビューへの貼り付けでは、グリフの幅もコピーの対象になります。

<!--
You can scroll the display to any particular character by typing that
character. There is also a dialog which allows a slightly more general
way of jumping around. You may type in the glyph's name (all glyphs in a
font will be named), its encoding value, its unicode encoding value, or
(for 2 byte fonts) its ku ten specification.
-->
任意の文字をキー入力することにより、その文字へスクロールして移動することができます。
ダイアログを使って、それよりわずかに汎用的な方法でビュー内を飛び回ることもできます。
グリフの名前 (フォント内に含まれる全てのグリフには名前がついています)、
エンコーディングの値、Unicode エンコーディングでの値、または (2 バイトフォントでは)
区点番号を入力することができます。

<!--
Pressing the right mouse button invokes a popup menu.
-->
マウスの右ボタンを押すとポップアップメニューが出て来ます。

<!--
### Encodings and Character Sets
-->
### エンコーディングと文字集合

<!--
A Character Set is a set of characters (for example all the letters of
the alphabet would be one character set). An encoding is a function that
takes a number (often between 0 and 255) and maps it to a character.
Often these two are used synonymously as an encoding generally implies a
given character set. (strictly speaking a character set is an unordered
collection with no implied encoding, and some encodings work with
multiple character sets).
-->
文字集合 (character set) は、一定の文字の集まりのことです
(例えば、アルファベットに含まれる全ての文字は 1 個の文字集合となるでしょう)。
エンコーディング (符号化方式) は、与えられた数値 (しばしば 0 から 255) を文字に対応づける関数です。
しばしばこれら 2 つは同義的に用いられ、
一般的には、あるエンコーディングにはある特定の文字集合が結びついているものと暗黙に前提されます。
(厳密に言えば、文字集合は順序づけられていない集合であり、何らエンコーディングを暗示するものではありませんし、
一部のエンコーディングは複数の文字集合に適用されて使用されます)。

<!--
All fonts in fontforge have both a character set and an encoding. The
character set is just the set of characters in the font. The encoding is
the way those characters are ordered (or sometimes, the way the first
256 are ordered). The font info dialog allows you to chose the encoding
(and character set) you wish for a font. Often a font will have a few
extra glyphs that don't fit into the character set specified by the
encoding, these glyphs will be placed at the end of the font and when
the font is output (ie. postscript is generated, or a bitmap font
created) the glyphs will be included in the font but they will not be
encoded (this can be useful, especially in postscript where it is
possible to reencode a font at run time. Thus a font might have all the
glyphs needed both for a cyrillic character set and for a latin one, but
only one character set at a time would be encoded).
-->
FontForge 内の全てのフォントは、文字集合とエンコーディングの両方を備えています。
ここで文字集合は、単純にフォントの含む文字の集合のことです。
エンコーディングは、それらの文字が並んでいる順番です
(時には、最初の 256 文字が並んでいる順番のことを指すこともあります)。
<span class="command">フォント情報</span>
ダイアログにより、フォントのエンコーディング (および文字集合) を選択することができます。
1 個のフォントの中には、
エンコーディングによって指定された文字集合に当てはまらない若干の追加グリフが含まれることがしばしばあります。
それらのグリフはフォントの最後に配置され、フォントが出力される時 (例えば PostScript が生成される時やビットマップフォントが作成される時)、
それらのグリフはフォント内に含まれますが符号化されません。(これは役に立つことがあります。
特に、PostScript では実行時にフォントのエンコーディングを切り替えることができるので、
1 個のフォントにキリル文字集合とラテン文字集合の両方がそれぞれ必要とするグリフを全て収録することができます。
ただし、一度には 1 個の文字集合しか符号化することができません)。

<!--
It is possible for an encoding not to be one-to-one. That is there may
be several characters that might lead to the same underlying glyph (the
classic example is the non-breaking space which often uses the same
glyph as the breaking space). When FontForge encounters such an encoding
it will create a character structure for each entry, one of those
structures will contain the data for drawing the glyph, the other(s)
will contain a reference to the one real character. All characters will
have the same name. When FontForge generates a font it looks for this
case and turns it into a font whose encoding vector contains multiple
references to a glyph.
-->
エンコーディングによって、1 対 1 でない対応づけを行うことも可能です。
というのも、文字に伴うグリフを二、三の文字が共有することも可能だからです
(古典的な例としては、改行不能の空白がしばしば改行可能の空白と同じグリフを共有していることがあります)。
FontForge がこのようなエンコーディングに出会ったときは、それぞれの項目に対して文字の構造体を作成し、
それらの構造体の一つにグリフを描画するためのデータを格納し、その他の文字には文字の実体に対する参照を格納します。
それら全ての文字は同じ名前を持つことになります。
FontForge がフォントを生成する時はこのような場合を探し出し、
1 個のグリフに対して複数の参照を含むエンコーディングベクタをもつフォントに変換します。

<!--
It is also possible to have an encoding where a single character can
lead to several different glyphs depending on the context. In arabic,
for example, most characters have at least four different glyphs
depending on whether the character is found initially, medially or
finally in a word, or if it appears by itself (isolated).
-->
1 個の文字が複数の異なるグリフに対応するような符号位置が存在することも可能です。
例えば、アラビア文字ではほとんどの文字が単語の最初・中間または最後のどこに位置するか、
または単体で (孤立して) 表れるかによって最低 4 種類の異なるグリフを使用します。

<!--
You may also create a custom encoding. (Generally, only the first 256
entries of a Custom encodings will actually be part of a font's encoding
vector). You may change the name of any glyph in the font with the
Element-\>Char Info command. This will force the font to have a custom
encoding.
-->
カスタムエンコーディングを作成することもできます。
一般的に、フォントのエンコーディングベクタの一部分として含まれるのは、
カスタムエンコーディングのうちの先頭 256 項目だけです)。
<span class="command">エレメント(L)-\>グリフ情報(I)...</span>
コマンドを使用して、フォント内の任意のグリフの名前を変更することができます。
これを行うと、フォントは強制的にカスタムエンコーディングに変換されます。

<!--
There are many standard encodings built in to the program. There are 14
ISO 8859 encodings, the encoding used by the Macintosh for the US and
Western Europe, the encoding used by MS Windows for the US and Europe
(which is a slight extension of ISO 8859-1). There are also several
2-byte encodings built in. Several of these are subsets of unicode
(whose goal is to specify every character currently used by humans).
There are many large CJK (Chinese, Japanese, Korean) two byte encodings.
You can also add your own encodings with the
[Encoding](../encodingmenu/) menu. A brief description of what's in the
encodings also appears [on that page](../encodingmenu/).
-->
たくさんの標準エンコーディングがプログラムに組み込まれています。
ISO 8859 で定義されたエンコーディングが 14 種類、米国と西ヨーロッパの Macintosh で使用されるエンコーディング、
米国と西ヨーロッパの MS Windows で使用されているエンコーディング (ISO 8859-1 を少しだけ拡張したものです) があります。
組み込みの 2 バイトエンコーディングもいくつかあります。
それらのいくつかは、現在人間が用いている世界の全ての文字を指定することを目標にしている Unicode のサブセットです。
多数の CJK (中国・日本・韓国) の 2 バイト文字集合が存在します。
[Encoding](../encodingmenu/) メニューで、独自のエンコーディングを追加することができます。
何がエンコーディングに含まれているかも [このページ](../encodingmenu/) で簡単に説明しています。

<!--
There may be some slight differences between one vendor's definition of
an encoding and another. I try to follow those encodings specified by
the Unicode consortium. I notice that the Symbol encoding used by
Microsoft differs from the Unicode one (usually just be substituting
synonyms, Omega for Ohm sign for instance).
-->
あるベンダによる特定のエンコーディングの定義が他のベンダによるものと微妙に異なることがあり得ます。
それらのエンコーディングについては、Unicode コンソーシアムが指定する定義に従ったつもりです。
Microsoft が使用する Symbol エンコーディングは Unicode の定義と異なることが判明しています
(通常は、例えばオメガがオーム記号になっているような単に同義の文字に置き換わっているだけです)。

<!--
Adobe did not choose their naming conventions very well for Greek
letters. They assigned the name "mu" to Micro Sign, "Delta" to Increment
and "Omega" to Ohm Sign. So the Greek alphabet has ugly nameless holes
in it.
-->
Adobe は、ギリシャ文字の名前づけに関してまずい方針を採用してしまいました。
マイクロ記号に "mu", 増分記号に "Delta", オーム記号に "Omega" という名前を割り振っています。
そのためギリシャアルファベットには醜い名無しの穴が空いています。

<!--
CID fonts (see [below](#cid-keyed-fonts)) have no encodings. Instead they are
designed to be associated with one or several cmap files which provide
encodings in a general way. cmap files are beyond the scope of
FontForge. Adobe has defined many which are freely
[available](http://www.adobe.com/products/acrobat/acrrasianfontpack.html).
-->
CIDフォント ([下記](#cid-keyed-fonts) 参照) にはエンコーディングがありません。
その代わり、エンコーディングを一般的なやり方で供給する、
1 種類ないし数種類の CMap ファイルと一緒に使用するように設計されています。
CMap ファイルは FontForge のスコープ外です。
Adobe は、無料で
[入手可能](http://www.adobe.com/products/acrobat/acrrasianfontpack.html)
なファイルを数多く提供しています。

<!--
There is one final encoding called "Glyph Order". This encoding is just
the glyphs in the order in which they were read from the original font.
-->
最後にもう一つ、 "Glyph Order" と呼ばれるエンコーディングがあります。
このエンコーディングは元のフォントから読み出せる順序でのグリフのリストです。

### Unicode (ISO 10646)

<!--
PostScript&reg; assigns a name to every unicode character. Some of these
names are fairly obvious like "A" for the first letter of the latin
alphabet, others are more obscure like "afii57664" for hebrew alef,
while others are just "uni8765" for the unicode character at 0x8765.
-->
PostScript&reg; は全ての Unicode 文字に名前を割り当てています。
それらの文字の一部は非常に明瞭で、例えばラテンアルファベットの文字は "A" という名前です。
一部はもっと分かりにくく、ヘブライ文字のアレフは "afii57664" という名前で、
その他の物は Unicode の 0x8765 に位置する文字を単に "uni8765" のようにしています。

<!--
PostScript Unicode encoding does not quite mesh with the unicode
standard. This is probably because PostScript deals in glyphs and
Unicode deals with characters so PostScript sees no distinction between
space and nobreak space (and so does not encode the latter) while
Unicode does.
-->
PostScript の Unicode エンコーディングは Unicode 標準とうまく咬み合っていません。
おそらく、これは PostScript がグリフを扱うのに対して Unicode は文字を扱っているため、
PostScript では Unicode が区別しているスペースとノーブレークスペースの区別がない
(そして後者に符号を割り当てていない) のが原因でしょう。

<!--
According to the [unicode website](http://www.unicode.org/) the first
256 character positions of unicode and ISO 8859-1 (ISO Latin1) are the
same. However the PostScript encoding of ISOLatin1 is slightly different
from that specified for unicode. I cannot explain the reasoning behind
this. FontForge does not use PostScript's ISOLatin1 Encoding vector,
instead it uses the first 256 code positions of the unicode encoding
vector (slightly modified by me to conform to Unicode conventions rather
than PostScript. So I include nobreak space and the soft-hyphen).
-->
[Unicode の Web サイト](http://www.unicode.org/)
によると、Unicode の最初 256 文字は ISO 8859-1 (ISO Latin1) と同じです。
しかしながら、PostScript の ISOLatin1 エンコーディングは、Unicode で指定されている物とわずかな差があります。
私はこの背景にある理由を説明できません。
FontForge は PostScript の ISOLatin1 エンコーディングベクターを使わず、
その代わりに Unicode エンコーディングベクターの最初の 256 個のコード位置を使用します
(PostScript ではなく Unicode の習慣に適合するようにわずかに変更してあります。
そういうわけで、私はノーブレークスペースとソフトハイフンを含めています)。

<!--
FontForge supports two slightly different unicode encodings. The first
contains only the first 65536 characters of unicode (those in the [Basic
Multilingual Plane](http://unicode.org/roadmaps/bmp/), or BMP),
while the second can contain as many characters as you have memory for.
Character definitions are still sparse outside of the BMP so at the
moment you probably want to use just the BMP. Currently there are only
definitions for plane 0 (BMP, U+0000-U+ffff), Plane 1 ([SMP, Secondary
Multilingual Plane](http://www.unicode.org/roadmaps/smp/),
U+10000-U+1ffff), Plane 2 ([SIP, Supplementary Ideographic
Plane](http://www.unicode.org/roadmaps/sip/), U+20000-U+2ffff), and
Plane 14 ([SSP Supplementary Special-purpose
Plane](http://www.unicode.org/roadmaps/ssp/), U+e0000-U+effff).
-->
FontForge は 2 つの微妙に異なる Unicode のエンコーディングをサポートしています。
第 1 は、Unicode の最初の 65536 文字 ([基本多言語面](http://unicode.org/roadmaps/bmp/), BMP) のみを含み、
2 番目はメモリの許す限り多くの文字を含むことができます。
BMP の外側では文字定義は非常に疎らなので、さしあたり BMP だけしか使いたいと思わないでしょう。
今のところ、文字が定義されているのは、
第 0 面 (BMP, U+0000〜U+ffff),
第 1 面 ([SMP, 第二多言語面](http://www.unicode.org/roadmaps/smp/), U+1000〜U+1fff)、
第 2 面 ([SIP, 補助漢字面](http://www.unicode.org/roadmaps/sip/)、U+20000〜U+2fff)、
および第 14 面 ([SSP, 補助特殊用途面](http://www.unicode.org/roadmaps/ssp/), U+e0000〜U+efff) だけです。


<!--
### CID keyed fonts
-->
### CID キー指定フォント

<!--
The standard mechanisms that postscript provides work reasonably well
for alphabets and syllabaries, but the massive number of characters
needed for CJK (Chinese, Japanese or Korean) fonts require more complex
machinations. Adobe's current solution is the [CID-keyed
font](../cidmenu/#er-what-is-a-cid-keyed-font), a font consisting of several subfonts each a
collection of glyph descriptions with no encoding imposed on them and no
names given to them.
-->
PostScript の標準のメカニズムはアルファベットと音節文字に対しては割合うまく働きますが、
CJK (中国語・日本語・韓国語) フォントは、厖大な文字数を必要とするため、より複雑なたくらみを必要とします。
Adobe の現在の解決法は [CID キー指定フォント](../cidmenu/#er-what-is-a-cid-keyed-font) と呼ばれ、
それぞれがグリフ記述の集合体であるいくつかのサブフォントからなる 1 個のフォントで、
それらのグリフにはエンコーディングも定められておらず名前もついていません。

<!--
If FontForge loads in a CID keyed font it will enable a special menu
called [CID](../cidmenu/) which (among other things) displays the list
of all the sub-fonts in the font. When it starts up FontForge will pick
(practically at random) a sub-font to display in the font view. You may
change which font is displayed by the CID menu.
-->
FontForge が CID フォントを読み込むと、 [CID](../cidmenu/) という名の特殊メニューを表示し、
そこには (他の項目に加えて) フォント内に含まれる全てのサブフォントのリストを表示します。
起動時には、FontForge は (事実上ランダムな) 1 個のサブフォントを選んでフォントビューに表示します。
CID メニューによってどのフォントが表示されているかを変更することができます。

<!--
The CID menu also allows you to turn a normal font into a CID keyed
font. It creates a collection containing just the original font (you may
add other fonts, or blank fonts, later). But before it can create a
collection FontForge needs to know what glyph set you will be using. A
glyph set is just a collection of glyphs, and you may define your own if
you wish (but if you do you have to define your own cmap files, etc and
it's probably not worth it). Adobe has defined glyph sets for Japanese
(actually there are two, one corresponding to JIS208 and one to JIS212),
Korean (Wansung & Johab), Traditional Chinese (Big5) and Simplified
Chinese (GB2312). Although these glyph sets are based on the standards
mentioned, they each have many additional glyphs. Adobe also defines a
glyph set that works for Unicode, but it is called "Identity" instead.
FontForge does not have these glyph sets built in to it, each must be
loaded the first time it is used. I provide one file for each of the
above glyph sets, they have an extension of ".cidmap", and you may
download them all [from here](/assets/old/cidmaps.tgz).
-->
CID メニューでは、通常のフォントを CID キー指定フォントに変換することもできます。
それはオリジナルフォント 1 個のみを含むコレクションを作成します (後で他のフォントを追加したり、空のフォントを挿入したりできます)。
しかし、コレクションを作成する前に、FontForge はどのグリフセットを使うのか知っていなければなりません。
グリフセットは単なるグリフの集まりで、もし新しいセットを定義したいならそうすることもできます
(ただし、その場合は自分自身の CMap ファイル等を定義する必要があり、恐らくそうするだけの価値はないでしょう)。
Adobe は日本語用のグリフセット
(実際には 2 種類あります。一つは JIS X 0208 に対応し、もう一つは JIS X 0212 です)、
韓国語用 (Wansung と Johab)、繁体字中国語 (Big5) と簡体字中国語 (GB2312) を既に定義しています。
これらのグリフセットは上に挙げた規格に基づいていますが、それぞれのセットには追加のグリフがたくさんあります。
Adobe は Unicode 用に動作するグリフセットも定義していますが、ただしそれは "Identity" と呼ばれています。
FontForge はこれらのグリフセットを組み込んでいないので、それを最初に使用するときに読み込まなければなりません。
以上のグリフセットのそれぞれに 1 個ずつの定義ファイルが用意されていて、".cidmap" という拡張子が付けられています。
[ここから](/assets/old/cidmaps.tgz)
ダウンロードすることができます。

<!--
(There are also many other character sets floating around feel free to
install them yourself).
-->
(その他たくさんの文字セットがそこら中にありますが、それはパブリックドメインではなく、それを自分の手元に入手することはできませんでした。)

<!--
Adobe identifies each glyph set by a three values: a registry, an
ordering and a supplement. The registry is the name of the organization
that is defining the glyph set (Adobe calls itself Adobe), an ordering
identifies the glyph set (Japan1, Korea1, etc.) and the supplement
indicates how many times the ordering has been revised. Glyphs may only
be added to an ordering, never removed, so an old font will be perfectly
described by a newer glyph set, while a new font described by an old
glyph set will have some unavailable glyphs. So a full cidmap name will
look like:
-->
Adobe は各グリフセットを 3 個の値で識別しています:
登録者 (registry)、順序づけ (ordering) および補遺番号 (supplement) です。
登録者はグリフセットを定義する組織の名前で (Adobe は自分自身を Adobe と呼んでいます)、
順序づけはグリフセット (Japan1, Korea1 等) を識別し、
補遺番号は、順序づけが何度更新されたかを示します。
グリフは順序づけに追加することだけが許され、決して削除されません。
それにより、古いフォントを完全に新しいグリフセットで記述することができますが、
古いグリフセットで新しいフォントを表現した物は、いくつかアクセスできない文字が出る結果となります。
そういうわけで、完全な cidmap 名は以下のようになります:

* Adobe-Japan1-4.cidmap
* Adobe-Korea1-2.cidmap

<!--
<strong class=".text-warning .label-warning">Warning:</strong> CID keyed fonts (actually any CJK font) use massive amounts
of memory in FontForge. I am able to work on many of them on my 256M
machine with 384M of swap space.
-->
<strong class=".text-warning .label-warning">警告:</strong>
CID フォント (実際には全ての CJK フォント) を FontForge で編集するには厖大な量のメモリを必要とします。
多くの物が 256MB のメモリと 384MB のスワップ容量をもつマシンで編集できるのを確認しています。

<!--
The [Remove Undoes](../editmenu/#remove-undoes) command will allow you
to free up memory if you think you may be running short. FontForge is
not always able to protect itself against running out of memory,
sometimes the OS just sends it a SIGKILL signal.
-->
メモリが不足しそうなときには、
[<span class="command">アンドゥ履歴のクリア(V)</span>](../editmenu/#remove-undoes)
コマンドを使えばメモリを開放することができます。
FontForge はメモリを使い果たしてしまう危険から常に守られているわけではなく、
場合によっては OS からいきなり SIGKILL シグナルを送られてしまうことがあります。

<!--
### Multiple Master Fonts
-->
### マルチプルマスターフォント

<!--
If the font is a [Multiple Master](../multiplemaster/#what-is-a-multiple-master-font) Font there
will again be several subfonts only this time all the subfonts contain
the same glyph set. Each subfont provides glyphs for one style of the
font family. The [MM](../mmmenu/) menu allows you to control which
style of the family is visible in the font view, and provides a few
other commands for manipulating multiple masters.
-->
フォントが [マルチプルマスター](../multiplemaster/#what-is-a-multiple-master-font) フォントである場合も、
いくつかのサブフォントが存在しますが、この場合は全てのサブフォントが同じグリフセットを持っています。
各サブフォントは、あるフォントファミリーの 1 スタイルにあたるグリフを提供します。
[MM](../mmmenu/) メニューでは、フォントビューでどのスタイルのファミリーが見えるかを制御できるほかに、
その他いくつかのマルチプルマスターフォントを扱うフォントが存在します。

<!--
### Vertical Metrics
-->
### 縦書きメトリック

<!--
CJK fonts generally should have vertical metrics. Latin (Cyrillic,
Greek) fonts generally should not. If FontForge reads in a font with
vertical metrics it will retain those metrics, but when FontForge
creates a new font then that font will not have vertical metrics
enabled.
-->
CJK フォントは通常縦書き用のメトリックを備えている必要があります。
ラテン文字 (やキリル文字、ギリシャ文字) のフォントは一般的にそれを含んでいてはなりません。
FontForge が縦書きメトリックを含むフォントを読み込むと、それらのメトリックを保持しますが、
FontForge が新しいフォントを作成した時には、そのフォントでは縦書きのメトリックが使用可能にはなっていません。

<!--
To enable vertical metrics for a font go to `Element->Font Info` and
select the `General` tab and check the
`[*] Has Vertical   Metrics `checkbox. This will allow you to set the
vertical origin for the font and it will give every glyph a default
vertical advance of the emsize of the font (ascent+descent).
-->
あるフォントで縦書きのメトリックを使用可能にするためには、
<span class="command">エレメント(U)-\>フォント情報(F)...</span>
から
<span class="command">一般情報</span>
タブを選択し、
<span class="command">[*] 縦書きメトリックが存在</span>
チェックボックスにチェックを入れます。
これを使うと、そのフォントの縦書きの原点を設定し、
各グリフに縦書きの字送りのデフォルト値 (高さ+深さ) を EM サイズ単位でセットします。

<!--
The vertical origin is the y height (in the design coordinate system) of
the origin for vertical metrics.
-->
縦書きの原点は、縦書きメトリックの Y 軸方向の高さ (デザイン座標系で) と一致します。

<!--
In the outline glyph view you will be able to adjust the vertical
metrics just as you adjust the horizontal metrics.
-->
アウトライングリフビューでは、横書きメトリックを調整するのと同様の方法で縦書きメトリックを調整することができます。

<!--
You can view the vertical metrics in the font view just as you can the
horizontal metrics with View-\>Show V Metrics.
-->
フォントビューで縦書きのメトリックを表示させるには、横書きメトリックと同様に、
<span class="command">表示(V)-\>縦書きメトリックの表示法(V)...</span>
を使用します。