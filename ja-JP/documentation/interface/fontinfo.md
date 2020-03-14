---
published: true
layout: default.ja
title: フォント情報
---
<!--
published: true
layout: default
title: Font Info
-->


[table_of_contents]


![](/assets/img/dialogs1-fontinfo.png)

<!--
The Font Info dialog is available from all views. It allows you to name
your font and various other useful bits of information. In a [CID keyed
font](../fontview/), things are more complex. Each CID keyed font is 
composed of man sub-fonts; this command works on the current sub-font 
while there is a [separate command](../cidmenu/#CID+Font+Info) to access 
the information for the font as a whole -- that dialog looks the same. 
The dialog is composed of many different sub dialogs.
-->
フォント情報ダイアログはすべてのビューから使用可能です。
このメニューを使ってフォントに名前をつけたり、その他さまざまな有用な情報の各ビットを設定することができます。
[CID キー指定フォント](../fontview/)
では、事情はより複雑です。
各々の CID キー指定フォントは多くのサブフォントから構成されています;
このコマンドは現在のサブフォントを操作するためのものであり、
フォント全体の集合体の情報にアクセスするためには
[独立したコマンド](../cidmenu/#cid-font-info)
があります
-- このダイアログと見た目は同じです。
このダイアログは多数の別種のサブダイアログから構成されています。


<!--
### Names
-->
### 名前 (Names)

<!--
PostScript fonts have several different names, but basically there are
two important ones: the family name (like Times) and the fontname (which
is the family name with a bunch of modifiers like Bold Italic Condensed
tacked on to the end. The FullName is designed to be read by humans,
while the others are for machines, this name can contain spaces (like
"New Century Schoolbook-Bold Condensed"). Finally there is the weight
name. All of these names should be in ASCII. If you wish to enter names
with characters outside this range look at the [TTF Names](#TTF+Names)
Section.
-->
PostScript フォントには何種類かの異なる名前がついていますが、
そのうちで重要なのは基本的に 2 つです:
ファミリー名 (Times など) とフォント名 (ファミリー名に多数の修飾子をつけたもの。
例えば Bold Italic Condensed などが後ろにつく) です。
フルネームは人間が読む目的でつけられていて、
その他の機械が読むための項目と異なります。
これは空白を含むことができます
(例えば "New Century Schoolbook-Bold Condensed")。
最後に、ウェイト名があります。
これらの名前はすべて ASCII で書かなければなりません。
この範囲に含まれない文字を含む名前をつけたい場合は、
[TTF 名](#TTF+Names)
のセクションを参照してください。

<!--
The copyright field can contain whatever you want to put there, but it's
a good place to put a copyright.
-->
<span class="command">著作権フィールド(R)</span>
は何でも入力したいものを入力できる場所ですが、
ここには著作権表示を記入するのがいいでしょう。

<!--
In most fonts the version field is a string (and so has minimal
constraints on it), but in CID keyed fonts it must be a floating point
number.
-->
ほとんどのフォントではバージョンフィールドは文字列です
(それには最低限の制限があります) が、
CID フォントでは浮動小数点数でなければなりません。

<!--
You may also specify a separate version number to be used in any sfnt
generated from this database; this should be a floating point number. Or
you may leave this field blank. If you leave it blank FontForge will
generate a default value based on other version information specified
elsewhere.
-->
このデータベースから生成された sfnt で使用する別のバージョン番号を指定することもできます;
これは浮動小数点数である必要があります。
または、このフィールドを空白のままにすることもできます。
空白のままにすると、FontForge は、
他の場所で指定された他のバージョン情報に基づいてデフォルト値を生成します。

<!--
Normally when [generating a font](../generate/), FontForge will use the
fontname as the base for the default filename of the font file (the base
to which the extension is added). But that is not always what you want.
You may wish to attach a version string to the fontname, or abbreviate
it, etc. The `Base Filename` field allows you to specify this to
fontforge.
-->
通常、
[フォントを生成](../generate/)
する場合、
FontForge はフォント名をフォントファイルのデフォルトのファイル名のベース
(拡張子が追加されるベース)
として使用します。
しかし、それはあなたが期待するものとは限りません。
フォント名にバージョン文字列を添付したり、短縮名にしたりすることもできます。
`BaseFilename`
フィールドで、これを FontForge に指定できます。

<!--
Many of these names are similar to the english names of the [TTF
Names](#TTF+Names) section. If nothing is specified in that
section then the names specified here will be used by default in ttf
files.
-->
これらの名前の多くは
[TTF 名](#ttf-names)
セクションの英語名に似ています。
そのセクションで何も選択しなかった場合には、
ここで指定した名前が TTF ファイルのデフォルトとして使用されます。


<!--
### General
-->
### 一般情報 (General)

![](/assets/img/dialogs1-fontinfo-general.png)

<!--
This sub dialog contains a rather random collection of settings.
-->
このサブダイアログには、各種設定のかなり雑多な集まりが含まれます。

<!--
The Ascent and Descent are (in this current definition) Macintosh
concepts rather than PostScript, their sum, however, provides the size
of the em-square and that is very much a postscript concept. For
postscript fonts this number is set by strong convention to be 1000,
while in most TrueType fonts it will be 2048 (also a convention, but
TrueType claims rasterization is faster if the sum is a power of 2).
Since both TrueType and Type1 (postscript) fonts represent numbers as
16-bit integers ascent and descent must be less than 32767. TrueType is
more restrictive and requires their sum to be less than 16384.
-->
高さ (Ascent) と深さ (Descent) は、
(現在の定義では) PostScript の概念よりも Macintosh の概念と言うべきです。
とはいえ、それらの合計が EM 正方形のサイズとなるという点では
PostScript の概念と似ています。
PostScript フォントでは、
この合計値を 1000 にするという強固な慣習があります。
一方、TrueType フォントのほとんどでは 2048 になります
(これも慣習ですが、TrueType の仕様書によると、
合計が 2 の冪であるとラスタライズが高速に行えると主張しています)。
TrueType と Type1 (PostScript) フォントはどちらも 16 ビット整数で表現されるので、
高さと深さは 32767 より小さくなければなりません。
TrueType では制限がさらにきつく、
それらの合計が 16384 より小さくなければなりません。

<!--
If you change the size of the Em you may choose to have all the outlines
(and kerning info) scaled to have the same proportion to the new value
that they had to the old. Warning: **If your font has truetype
instructions scaling may break the font as entries in the `'cvt   '`
table will not be scaled.**
-->
EM のサイズを変更したときには、
すべてのアウトライン (およびカーニング情報) を古い値から新しい値に変更したのと同じ比率で拡大・縮小します。
警告: **フォントに TrueType 命令が含まれている場合、
拡大・縮小を行うと、
`'cvt...'`
テーブルは拡大・縮小されないままなので、
フォントは壊れるでしょう。**

<!--
The Italic Angle indicates the slant of the font. FontForge can attempt
to guess a good value for you by looking at the stems of certain letters
("I" for instance).
-->
<span class="command">イタリックの傾き(I)</span>
は、フォントの傾きを表します。
FontForge はいくつかの文字 (例えば "I") のステムを見ることにより、
適切な値の推測を試みることができます。

<!--
The underline position and height provide a program using this font a
hint as to where it should place a line if it wants to underline text
printed in this font.
-->
<span class="command">下線の位置(P)</span>
と
<span class="command">太さ(H)</span> は、このフォントを使うプログラムが下線つきテキストをこのフォントで印字しようとするときに、
線をどこに引くかに関するヒントを提供します。

<!--
If you want your font to have vertical metrics (generally this means you
are working on a CJK font) then check the `[*] Has Vertical   Metrics`
checkbox. This will enable the Vertical Origin field, and will mean that
when you generate a truetype or opentype font a vertical metrics table
will be added. The Vertical Origin is the vertical offset from the
origin of the design coordinate system to the origin for the purposes of
vertical metrics.
-->
作成中のフォントに縦書きメトリックが存在する場合
(一般には、これは CJK フォントをつくっているということですが)
<span class="command">[*] 縦書きメトリックが存在(V)</span>
チェックボックスがチェックされます。
これをチェックすると
<span class="command">縦書きの基準点(O)</span>
フィールドが使用可能になり、
それによって TrueType または OpenType フォントを出力するときに、
縦書きメトリックテーブルが追加されることになります。
縦書きの基準点は、デザイン座標系の原点から、
縦書きメトリックで用いられる原点への垂直方向のオフセットです。

<!--
Sadly the encoding is not always sufficient for understanding the font's
behavior. For example a unicode font designed for a chinese system will
look very different from a unicode font for a japanese system (The same
unicode character may map to very different chinese or japanese glyphs).
To handle this FontForge has the concept of "Interpretation".
-->
残念ながらエンコーディングは、フォントのふるまいを理解するのに常に十分なわけではありません。
例えば、中国語の表記法に合わせて作られた Unicode フォントは、
日本語の表記法に合わせて作られた Unicode フォントとは大きく異なる見かけをもつでしょう
(中国語と日本語で大きく異なるグリフが同一の Unicode 文字に割り当てられています)。
これを扱うために (および他のいくつかの目的のために) FontForge は "解釈" という概念をもっています。

<!--
When you create a new glyph in a font, fontforge will assign it a name
based on the current [NameLists](../encodingmenu/#NameLists).
-->
フォント内に新しいグリフを作成すると、
FontForge は現在の
[名前リスト](../encodingmenu/#NameLists)
に基づいて名前を割り当てます。


<!--
### Layers
-->
### レイヤー (Layers)

![](/assets/img/dialogs1-fontinfo-layers.png)

<!--
You may control how many and what types of layers are available in your
font.
-->
フォントで使用できるレイヤーの数とタイプを制御できます。

<!--
Fonts may be either outlined or stroked, or type3. You may choose
which kind of font you want.
-->
フォントは、アウトラインまたはストローク、または Type3 のいずれかです。
必要なフォントの種類を選択できます。

<!--
You may also decide what kind of splines you want in the font in
general, often all the layers will use the same type of splines (so
there are radio buttons to make that easy), but it isn't required each
layer may be in its own format.
-->
また、一般的にフォントに必要なスプラインの種類を決定することもできます。
多くの場合、すべてのレイヤーは同じタイプのスプラインを使用します
(したがって、簡単に設定できるようにラジオボタンがあります)
が、
必須ではなく、各レイヤーに個別の形式を指定することができます。

<!--
If you mark a layer as quadratic (or check `[*] All layers Quadratic`)
then FontForge will use quadratic [Bézier](/en-US/tutorials/overview/#spline) 
splines for this layer rather than cubic Béziers, this means that 
FontForge will be using the native spline format of truetype rather than 
postscript (or opentype). When FontForge generates a font it will convert 
from whatever format is used internally to whatever format is required for 
the font, so there will be no problem if this is set incorrectly, but setting 
it correctly for your font means you get a clearer idea of what the outlines 
will look like. I find quadratic splines harder to edit with because each spline 
is less flexible, but the advantage of actually seeing what your truetype font
will look like may outweigh that.
-->
レイヤーを 2 次スプラインにしている場合
(または、
<span class="command">[*] すべてのレイヤーを 2 次スプラインに (All layers Quadratic)</span>
をチェックしている場合)、
FontForge は 3 次 Béziers スプラインでなく、
2 次
[Bézier](../..//tutorials/overview/#spline)
スプラインをこのフォントに使用します。
言い替えれば、
FontForge が PostScript (または OpenType) の曲線フォーマットではなく、
TrueType 元来のフォーマットで編集を行うということです。
FontForge がフォントを出力するとき、
内部フォーマットがどちらであっても、
そのフォントフォーマットが必要とする方式に変換を行いますので、
これが間違って設定されていても問題は起こりません。
しかし、これを正しく設定しておくことにより、
アウトラインがどのように見えるかについてより明白に把握することができます。
個人的経験では、2 次スプラインのほうが自由度が低く
(かつ、FontForge の多くのコマンドが動作しない) ため、
編集がいっそう困難ですが、
TrueType フォントがどう表示されるかを実際に見ることの利点はそれに勝ります。

<!--
You may also mark a layer as a foreground layer or a background layer.
Background layers can hold images. Pasting into an empty glyph in a
background layer will not set the width. Splines in background layers do
not make a glyph worth outputting.
-->
レイヤーを前景レイヤーまたは背景レイヤーとしてマークすることもできます。
背景レイヤーには画像を置くことができます。
背景レイヤーに空のグリフを貼り付けても、幅は設定されません。
背景レイヤーのスプラインは、出力対象となるグリフを作成しません。


<!--
### PostScript Unique ID
-->
### PostScript ユニーク ID (PostScript Unique ID)

![](/assets/img/dialogs1-fontinfo-psuid.png)

<!--
**NOTE:** [Adobe now says](http://permalink.gmane.org/gmane.comp.fonts.fontforge.user/173) that both XUID and UniqueID
are unnecessary.
-->
**注意:**
Adobe は現在では、
XUID や UniqueID はどちらも
[不要だと言っています](http://permalink.gmane.org/gmane.comp.fonts.fontforge.user/173)。

<!--
The XUID field is a collection of numbers separated by spaces and
enclosed in brackets. This allows you to specify the extended unique ID
of the font. If you have set the XUID preference entry then FontForge
will assign values to all new fonts (by appending a number unique to
this font to the end of your preference item). Adobe recommends that the
XUID be changed every time the font is changed, so each time you
generate a postscript font, that font's XUID (if present) will be
incremented by 1 (This incrementing does not happen in CID-keyed fonts,
where the XUID behavior is too complex for this simple trick). (The XUID
field is only meaningful in PostScript fonts).
-->
XUID フィールドは、空白で区切られた数値の集まりを括弧でくくったものです。
フォントの拡張ユニーク ID はこれを用いて指定することができます。
XUID プリファレンス項目が既に設定されているならば、
FontForge はすべての新しいフォントに対して
(指定した値の後に各フォントに一意な数値を付け加えて)
その値を設定します。
Adobe は、フォントが変更されるたびに
XUID を毎回変更することを推奨しているので、
PostScript フォントを生成するたびごとにフォントの XUID (存在する場合) は  1 ずつ加えられます
(この増加は CID フォントでは行いません。
CID フォントでは XUID の扱いがこの単純なトリックでは対処しきれないほど非常に複雑だからです)。
(XUID フィールドは、PostScript フォントでのみ意味があります)。

<!--
The UniqueID field is an older convention for the same purpose as XUID.
If you do not fill in this field then FontForge will pick a random
number for you in the allowable range. If you want your font to have no
unique id then give this the value of -1. If you have talked to Adobe
and been assigned a real UniqueID then you may use this field, otherwise
leave it blank. (The UniqueID field is only meaningful in PostScript
fonts)
-->
UniqueID フィールドは XUID と同じ目的をもつ、
より以前からの慣習です。
このフィールドに値が入っていない場合は、
FontForge は許される範囲からランダムな値を選びます。
フォントにユニーク ID を設定したくない場合は、
この値を -1 にしてください。
もしあなたが Adobe に連絡して正式なユニーク ID を割り当てられたならば、
このフィールドを使うことができます。
それ以外の場合は空白にしておいてください。
(XUID フィールドは、PostScript フォントでのみ意味があります)。


<!--
### Private -- font-wide postscript hinting
-->
### PostScript の Private 辞書 --フォント全体に適用される PostScript のヒント (Private -- font-wide postscript hinting)


![](/assets/img/dialogs1-fontinfo-private.png)

<!--
This sub-dialog shows most entries in the font's Private dictionary. 
The interesting things in this dictionary are mostly concerned with hints
appropriate for the entire font. I shall not go into detail about 
the meanings of the various entries, that is best understood by reading 
[Adobe's Type1 specification](http://partners.adobe.com/asn/developer/PDFS/TN/T1_SPEC.PDF).
-->
このサブダイアログは、
フォントの Private 辞書内のほとんどの項目を表示します。
この辞書内にある興味深い事柄のほとんどが、
フォント全体に適用されるヒントに関連するものです。
それら多数の項目の詳細にここで立ち入るつもりはありません。
それを理解するには
[Adobe の Type1 仕様書](http://partners.adobe.com/asn/developer/PDFS/TN/T1_SPEC.PDF)
を読むのが最善の方法です。

<!--
Don't try to change these until you understand what they mean.
-->
これらの項目が何を意味するか理解するまでは、これらを変更しようとしてはいけません。

<!--
The dialog is shown at right. It consists of a list of dictionary
key/value pairs. The keys are on the left, values on the right.
Generally you will want to use the standard PostScript keys (these are
available from a pulldown list that appears when you press one of the
little grey buttons).
-->
右に表示されているのがこのダイアログです。
それはキー/値ペア辞書のリストを含んでいます。
左がキー、右が値です。
一般に、標準 PostScript キー
(小さな灰色のボタンを押すと表示されるプルダウンリストから利用できます)
を使用します。

<!--
Note: The values must be things which PostScript can parse. This means
that `ForceBold` must have a value of "false" or "true", and "False" or
"faux" will not work. Similarly the decimal point in numbers must be "."
(not ","). If you enter a "," by mistake FontForge will convert it for
you.
-->
注： 値は、PostScript が解析できるものでなければなりません。
つまり、
`ForceBold` の値は "false" または "true" でなければならず、
"False" または "faux" は動作しません。
同様に、数字の小数点は "." （"," ではなく） でなければなりません。
誤って "," を入力した場合、
FontForge が変換してくれます。

<!--
For example the `BlueValues` entry specifies certain key regions of the
font in a vertical direction. For instance it might contain the baseline
serif, the x-height serif, the cap-height serif. It is expressed as an
array of numbers, grouped in pairs. The first number of a pair is the
low end of the region and the second is the high end. So in the example
at right, the value of `BlueValues` is
`[-20 0 437 457 583 603 623   643`.
-->
たとえば、
`BlueValues` エントリは、垂直方向のフォントの特定のキー領域を指定します。
たとえば、ベースラインセリフ、x-height セリフ、cap-height セリフが含まれる場合があります。
ペアにグループ化された数値の配列として表されます。
ペアの最初の数字は領域の下端であり、
2番目は上端です。
したがって、右の例では、BlueValuesの値は
`[-20 0 437 457 583 603 623 643`
です。

<!--
When the `[Guess]` button is enabled FontForge thinks it can make a
reasonable guess for the value of the currently selected entry.
-->
<span class="command">推測(G)</span>
ボタンが押せる状態のとき、
FontForge は現在選択されている項目の妥当な値を推定することが可能だと判断しています。

<!--
The `[Histogram]` button is similar, it will bring up a [dialog showing
a histogram](../histogram/) of the values of an attribute of the font.
The hope is that this will allow you to pick a good value for the entry.
-->
<span class="command">柱状図(H)</span>
ボタンも同様で、
フォントのある属性の値を
[柱状グラフとして表示するダイアログ](../histogram/)
を起動します。
その項目の適切な値をフォント作成者が選ぶことができるように用意された機能です。

<!--
You may also delete an entry from the dictionary with the
`[Delete]   `button. Some entries (such as `BlueValues`) must be present
in any type1 font, but you may still delete them. FontForge will simply
guess at a reasonable value when it needs to generate the font.
-->
また、
<span class="command">削除(R)</span>
ボタンを押せば辞書から項目を削除できます。
いくつかの項目
(<span class="command">BlueValues</span> など)
はすべての Type1 フォントで設定する必要がある項目ですが、
それらの項目も削除することができます。
FontForge はフォントを出力するために値が必要になったときに妥当な値を単純に推測します。

<!--
Certain keys affect things other than hints. The `lenIV` entry controls
how much random padding is placed around the type1 strings when the font
is generated. Normally this will be 4, but if you want to save space (4
bytes per glyph in pfb format, 8 bytes in pfa) you may choose another
value. The UniqueID key represents the font's Unique postscript ID. If
you provide a value here then FontForge will copy it into the UniqueID
field in the Font Dictionary. (this is different from True Type's
UniqueID. They perform the same function but are formatted differently).
-->
いくつかのキーはヒント以外のものに影響を与えます。
項目
`lenIV`
は、フォントが生成されるときの Type1 文字列の先頭に置かれるランダムなパディングが何バイトになるかを制御します。
通常はこれは 4 ですが、
スペースを節約したい場合
(PFB フォーマットではグリフ 1 個ごとに 4 バイト、PFA では 8 バイト)
他の値を選択できます。
UniqueID キーは、フォントのユニーク PostScript ID を表します。
ここで値を設定した場合は、FontForge はその値をフォント辞書の UniqueID syー琉度にコピーするだけです。
ここで UniqueID を設定しなかった場合、
FontForge は自分でランダムな値を生成します
(これは TrueType の UniqueID とは異なります。それらは同じ機能ですが、フォーマットが異なります)。

<!--
Some of these entries are only meaningful for PostScript fonts, others
will be used by the truetype autoinstructor.
-->
これらの項目は PostScript フォントでのみ意味をもちます。


### OS/2

![](/assets/img/dialogs1-fontinfo-ttfvals.png)

This sub dialog contains settings important for Windows platforms, most
of these settings live in the 'OS/2' table of a truetype or opentype
font. The pane also includes a few pieces of data that do not live in
the 'OS/2' table but are logically related.

The weight class provides a numeric value describing the boldness of the
font. A normal face will usually have a boldness of 400, and a bold face
will usually be 700. This must be a number between 100 and 900.

The width class allows you to provide a numeric value saying how
condensed or expanded this font is.

The PFM Family is used when generating PFM files and classifies the font
into some rather broad categories (Serif, Sans, Monospace, Script,
Decorative).

You can control whether you want to allow your font to be embedded into
other documents (most commonly pdf). You can restrict it so that it can
never be embedded, it can be embedded into documents that can be printed
(but not edited), it can be embedded into documents that can be edited,
or it can be embedded into an editable document and later extracted and
installed on a different system. You can also control whether the
document producer is allowed to extract the glyphs it needs and make a
new font from them (which saves space) or whether they must include the
entire font if they use any of it. Finally you can restrict the
embedding so that only bitmap versions of the font may be embedded.
(meaningful in CID keyed postscript fonts as well as TTF and OTF).

The "Vendor ID" is a four character ASCII field used to identify the
creator of the font.

The IBM Family is another classification scheme for fonts.

Finally you may order lookups in the GSUB (or morx) table.

These entries are only meaningful in TrueType and OpenType fonts (though
the Embeddable entry (generally called FSType) will be set on CID keyed
fonts even if they are not in an OpenType wrapper.


#### GSUB/morx Ordering

![](/assets/img/dialogs1-GSUB-Order.png)

This dialog allows you to control the order features in which are to be
executed by the word processing program. If you have loaded an opentype
or truetype font then the original order will be maintained. As you add
more features they will appear at the bottom of the list (which may not
be appropriate). You may select a feature name and use the buttons to
move it up and down in the list. Things at the top of the list are
executed first, things at the bottom last.

**Caveat:** Although the OpenType spec claims that the execution of
features (actually lookups) will be ordered by their appearence in the
lookup table, MicroSoft claims that they will apply features in the
order that they think best. So the order specified in the font may be
ignored.


#### OS/2 Metrics

![](/assets/img/dialogs1-fontinfo-ttfmetrics.png)

The Windows Ascent and Descent fields are badly defined in the OpenType
spec, which says that they should express the maximum range of the
Windows "ANSI" glyphs. If one uses this definition, non-"ANSI" glyphs
are cropped. These should be the maximum range of all glyphs to avoid
cropping. But even that will not always work. If you have a line with
marks which are repositioned with GPOS, then the marks may be cropped,
so Windows Ascent should include the maximum possible height of
repositioned marks (or any other GPOS vertical repositioning feature).

This is too complex (and too ill defined) for FontForge to figure out,
instead FontForge gives you a couple of options.

1.  You may set WinAscent and WinDescent directly. Turn off the "[ ] Is
    Offset" checkboxes and any value you provide will be used as is.
2.  Or you may specify an offset to be added to the maximum ascent and
    descent of the font (which FontForge will compute for you when it
    saves the font). If you don't have a mark to base feature, then I
    recommend that you set the offsets to 0, and check the "[\*] Is
    Offset" checkboxes.

Both WinAscent and WinDescent should be positive numbers.

The Typographic Ascent and Typographic Descent are *supposed* to
represent the line spacing of the font on the windows platform. Sadly
very few applications actually use them (most applications use the
Windows Ascent/Descent described above).

In traditional (Latin) typography, the unleaded line spacing should be
1em, and that is what Adobe recommends for these fields (they should sum
to the Em-Size specified in the [General](#General) pane). The Typographic
Ascent should be the same as the font's Ascent, and the Typographic 
Descent should be the (negative) of the font's descent.

The "[\*] Is Offset" checkboxes behave much as they do above, except
they specify offsets from the font's ascent and descent rather than its
bounding box.

The Typographic descent should be a negative number, the ascent a
positive number.

You can also specify the default line gap, or leading between lines.

The mac uses a different set of fields for the same concepts, and stores
them in the 'hhea' table rather than the 'OS/2'. The HHead Ascent and
Descent are used to specify clipping (in some applications) and line
spacing. They behave very much the way the Win Ascent & Descent behave
(they are based on bounding box values). And the 'hhea' table has its
own line gap field.

And if your font has vertical metrics enabled (See [General](#General)
above) you will be able to set the default spacing between vertical 
columns of text. (the equivalent to LineGap in vertical text).

The Capital Height describes the height of the capital X (or of any other
non-rounded capital letter that starts at the base line). The X Height
describes the height of the lowercase x. These values presently have no
bearing on how FontForge displays or processes the typeface, but they
do get exported to certain file formats. These values are accessible via
native and Python scripting.

[See the FAQ](/about/faq/#linespace) for a discussion on the complexities
involved in setting the line spacing. [The 'BASE' table](../baseline/)
provides a more precise method for setting line spacing.


#### OS/2 Sub/Superscripts

![](/assets/img/dialogs1-fontinfo-subsup.png)

The OS/2 table also contain information on scaling and positioning
subscripts and superscripts.

Most fonts don't really need this control. If you leave the [\*] Default
check box on, then FontForge will generate some reasonable values on
output (if nothing significant changes, it will use the values shown
here). If you want control of these values, turn off the checkbox and
the text fields will be enabled for you to change.


#### PANOSE

![](/assets/img/dialogs1-fontinfo-panose.png)

This sub-dialog allows you to describe your font in 10 different
dimensions. The exact meanings of many of these entries vary from script
to script, and even the Latin ones are not clear to me, I have merely
typed them in as specified in the [true type
docs](http://fonts.apple.com/TTRefMan/RM06/Chap6OS2.html). 
Better information is available from 
[HP](http://www.panose.com/),
[MS](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/gdi/fontext_48aa.asp),
[RS](https://www.w3.org/Printing/stevahn.html), 
[JJ](http://spectrum.library.concordia.ca/981753/) and
[this discussion](http://forum.high-logic.com/viewtopic.php?f=4&t=941).

If you leave the [\*] Default checkbox set then FontForge will generate
reasonable values when the font is output, otherwise you may set these
values manually.

These entries are only meaningful for TrueType, OpenType and SVG fonts.


### Charsets

![](/assets/img/dialogs1-fontinfo-charsets.png)

The OS/2 table contains two fields which give some information about the
characters in the font. Windows is very picky about using fonts if the
proper code page bits are not set. If you leave the [\*] Default
checkboxes set then FontForge will generate reasonable values when the
font is output. Sometimes you need to override that behavior if you wish
Windows to use a font with an incomplete code page.

These entries are only meaningful for TrueType, and OpenType fonts.


### TTF Names

![](/assets/img/dialogs1-fontinfo-ttfname.png)

TrueType (and OpenType) fonts are allowed to have different names in
different languages. So a French user might see CaslonItalic displayed
as CaslonItalique in a font menu, while a German user might see
CaslonKursive. There are about 20 different strings which may be
customized into various different languages. Customizing one string does
not mean that you must customize the others (indeed, often only the
Style string will be customized).

The image at right shows the dialog, displaying all the strings set for
the given font. You may order these strings based on type of string
(ordered as below), on language (ordered by unicode), or by a variation
of language which displays strings for the language of the current
locale first, then English strings (because, in general, these will be
the most important for the user) and then ordered by language
thereafter.

Certain strings in English (Copyright, Family, Styles, Fullname,
Version) will always be present. If you do not set them explicitly they
will be taken (possibly with modifications) from the equivalent
postscript strings on the [Names](#Names) pane. You may not
remove these strings, and if you wish to modify them you must first
detach them from the PostScript. In the example at right the strings
bound to PostScript are shown in red (Copyright, Family, Styles), while
Fullname and Version have been detached and modified.

You may change the language of a string by clicking the mouse on the
language field of that string -- a popup menu will appear giving you a
choice of all supported locale/languages. (You may not modify the
language of the special English strings mentioned above).

You may change the string type in a similar manner, again you may not
change the special English strings.

![](/assets/img/dialogs1-fontinfo-ttfname-bigedit.png)

If you click with the right button on a string you will bring up a
different popup menu which will allow you to:

-   Detach a string from its PostScript equivalent if any (so you can
    modify it)
-   Delete a string entirely (except for the special strings bound to
    PostScript)
-   Edit a string in a larger window.

If you click with the left button on a string value you may edit that
string in line, if it is small enough, otherwise in a larger window.

If you wish to add a new string, click on the \<New\> entry at the
bottom. You will be given the standard language popup and it will create
a new string for you.

The various strings and a brief description of their meanings are:

- **Copyright**  
    Allows you to specify the copyright message
- **Family**  
    The font's family name
- **Styles (SubFamily)**  
    This should (in English) have values like "BoldItalicCondensed". This is
    the most likely string to change in different languages.
- **Fullname**  
    The concatenation of the Family name and the Styles name
- **UniqueID**  
    This is a string that uniquely identifies the font in a human readable
    fashion. Its format is quite different from postscript's UniqueID and
    FontForge will create an appropriate string if you don't specify one
    (rather than copying from postscript).
- **Version**  
    A string containing the version number of the font.
- **PostScript Name**  
    (FontForge will not let you set this directly. It will be set
    automatically to the postscript fontname, only one instance of this tag
    is allowed in the font and it must be ASCII)
- **Trademark**  
    A string containing any trademark information for the font.
- **Manufacturer**  
    The name of the company that distributes the font.
- **Designer**  
    The name of the person who designed the font.
- **Descriptor**  
    A description of the font and its characteristics.
- **VendorURL**  
    An URL pointing to the font's vendor.
- **DesignerURL**  
    An URL (often an e-mail address) pointing to the font's designer
- **License**  
    A string describing the license terms under which the font is marketed.
    If you want to use the [SIL Open Font License](http://scripts.sil.org/OFL/),
    there is a button at the bottom of the dialog which will add that directly
    (so you don't need to type it in).
- **License URL**  
    An URL pointing to a page describing the terms of the license
- **Preferred Family**  
    This is to get around a quirk of windows where only four Style names are
    allowed per family, so font families with more than four styles would
    get different family names above, but the preferred family name would be
    the same. This should only be specified if it differs from the family
- **Preferred Style**  
    This is similar to the above, except it applies to the style.
- **Compatible Full**  
    This is to get around a quirk on the Mac.
- **Sample Text**  
    Whatever.

These are described in the [original true type docs](http://fonts.apple.com/TTRefMan/RM06/Chap6name.html), 
but they apply to [opentype](http://partners.adobe.com/asn/tech/type/opentype/recom.jsp)
as well.

These settings specify strings for the windows platform with unicode
encoding.

Generally fonts will have a fairly complete set of strings in the
American English entry, with the Style string (and nothing else)
translated into different languages.

When you create a Style entry for an language, FontForge will attempt to
translate the American English style into something appropriate for that
language. It understands languages in [the table on the font styles
page](../fontstyles/), but not others so it won't always work.

So if your style in American English is "BoldItalic" then after you
create the appropriate strings FontForge will default to "GrasItalique"
for French, "FettKursiv" for German, "NigritaCursiva" for Spanish, etc.

These names are only meaningful for TrueType and OpenType fonts.


### StyleSet Names

![](/assets/img/dialogs1-fontinfo-ssnames.png)

The OpenType features 'ss01'-'ss20' are magic, and you are allowed to
provide more interesting names for them than the default "Style Set
01"... This table allows you to assign names, in various languages to
the various features. It is very similar to, though less complicated
than, the previous pane.


### Grid Fit ('gasp' table)

![](/assets/img/dialogs1-fontinfo-gasp.png)

The TrueType 'gasp' table gives you control over whether the rasterizer
should do grid-fitting or anti-aliasing at any given pixel size. Note
that this table only applies to *TrueType* fonts, it does not apply to
Type2 PostScript (fonts with .otf extension).

The table consists of a set of pixel sizes with corresponding flags. For
each entry in the table the flags apply to all pixel sizes bigger than
the previous entry but less than or equal to the current entry. The
table must be terminated with a pixel size of 65535.

Pressing the [Default] button will provide you with a default 'gasp'
table. If your font contains no instructions this will be different than
the 'gasp' table for a font with instructions.

MS has recently expanded the table. Version 0 of the table had two bits
for each pixel value, version 1 has four bits, two of which control the
behavior of their ClearType rasterizer. They have also added a bit to
the 'head' table called optimized\_for\_cleartype; if this bit is not
set then some fonts will not be hinted.

In the table above:

-   All pixel sizes less than or equal to 8 will not be grid-fit but
    will have anti-alias applied
-   All pixel sizes between 9 and 16 (inclusive) will be grid-fit but
    not anti-aliased.
-   All pixel sizes above 16 will be both grid-fit and anti-aliased, and
    will have Cleartype Symetric Smoothing done.


### TeX

![](/assets/img/dialogs1-fontinfo-tex.png)

This allows you to set the TeX font parameters (which are described in
Appendix F, pp 98-100 of the MetaFont Book). There seem to be 3
different types of font parameters, those for text fonts, those for math
fonts and those for math extension fonts. The later two have additional
parameters which are accessible through the [More Params] button. The
default values for the Math parameters are probably reasonable. **The
default values for the Math Extension parameters are probably
unreasonable**.

These values are stored in tfm files (should you generate a tfm file
with your font).


### Size

![](/assets/img/dialogs1-fontinfo-size.png)

This allows you to set the design size of a font, the design range, and
provide a style name for this class of font.

In tradtional typography every point size of a given font would be
slightly different -- generally small point sizes would have
proportionally more white-space around the glyph and wider stems inside
the glyph. This made small point sizes more readable than they would
otherwise be. Conversely large pointsizes would tend to have less white
space around them, otherwise the letters would appear too far apart.

[Multi-master fonts](../multiplemaster/) provide one method to avoid
this problem. This dialog provides another. Suppose you have a series of
font-faces designed for different point-sizes.

    Ambrosia-Regular-Small     \<9pt
    Ambrosia-Regular-Text      9-13pt
    Ambrosia-Regular-Heading   14-23pt
    Ambrosia-Regular-Display   \>=24pt

Then you would fill in this dialog to allow the font system to figure
out which font was appropriate for which point size. The dialog displays
the font's optimal size -- its design size, and the point range within
which it can be used.

In the example above all the different fonts would have the same
"Style-ID" this is an arbetrary number that links all fonts with this ID
together (all fonts in the same family, that is). However,
Ambrosia-Italic-Text would have a different Style ID. All fonts with the
same Style ID should have the same Style Name. Note that font names are
now something like "Ambrosia-Regular-Heading" -- the user should not be
subjected to that complication, as far as s/he is concerned there is
just a font called "Ambrosia-Regular" and all four of the above fonts
are just instances of it. So the Style Name of all four fonts above
should be "Regular".

Adobe allows two forms of size information. In one, only the design size
field is specified, in the other all the fields must be specified. This
means that if you want to supply a design range you are also required to
provide a style id and name.


### Comment

![](/assets/img/dialogs1-fontinfo-comment.png)

This allows you to keep track of arbitrary comments inside your font
database. It does not correspond to any postscript or truetype entity.
It is intended to store a changelog for the font itself, but could be
used for other purposes...

Various font formats allow a random comment to be placed in the font,
but no format makes use of it. This is primarily to be used inside
FontForge. The comment should be in ASCII.


### FONTLOG

This has the same interface as the Comment above. The FONTLOG is an idea
stolen from the Open Font License. It is description of the font and a
log of changes made to it over time and includes some more information
about the font as well (see the [OFL FAQ)](http://scripts.sil.org/OFL-FAQ_web).
This pane allows you to store this information within the font itself
where it won't get lost.


### Mark Classes & Mark Sets

![Font Info Mark Classes](/assets/img/dialogs1-fontinfo-markclasses.png)

The various marks in your font may be divided into classes or sets. 
As I write (spring 2009) there is essentially no support for mark sets, 
but that will change (Both Adobe and MicroSoft say their next releases 
will support it).

The idea behind both is similar: In many lookups it is important to be
able to ignore some mark glyphs, but not others. For example when
forming an arabic ligature, the vowel marks are (usually) irrelevant to
the ligature and you would want to ignore all marks. In situations where
you are positioning marks on a base glyph you might in one case, want to
ignore all marks that position on top of the glyph while paying
attention to those underneath it. And then in another lookup, the
reverse might be true.

At any rate, in some cases it is important to be able to categorize
marks. Both classes and sets let you do this. In the example right,
latin marks have been divided into those above the glyph and those
below.

A glyph may appear in at most one class, while it may appear in many
sets. So when implemented, sets will be more versatile. On the other
hand classes can be stored more compactly in the font file (a slight
advantage).

Once you have created your classes (or sets, or both) you may use them
in the [Add Lookup](../lookups/#Add-Lookup) dialog from the
[Lookups](#Lookups) pane.

The Mark Set pane looks almost exactly like the Mark Class pane, and
functions similarly. From these panes you may add new classes, or edit
old ones.


### Lookups

![Font Info Anchors](/assets/img/dialogs1-fontinfo-lookups.png) 

This pane is so complex that it merits its [own section](../lookups/).

Briefly, lookups contain the data to do the work needed for complex
typography. There are two main classes of lookups, those which
substitute glyphs (ligatures for example) and live in the GSUB table,
and those which position glyphs (kerning for example) and live in the
GPOS table.

Each lookup is composed of one or many subtables.

There are buttons to the side to create (add) new lookups and subtables,
and to edit their attributes (metadata) and their commands (data).

The order in which the lookups appear in this dialog is the order in
which they will be applied. The order of the subtables within each
lookup is the order in which they will be applied. There are buttons to
the side which will reorder things.

It is possible to merge two lookups (if they are of the same type) or to
merge two subtables (if they are in the same lookup and are similar
enough).

It is possible to import lookups from other fonts (which must already be
loaded into fontforge.

It is possible to drag and drop lookups to reorder them, or to copy them
from one font to another (by dragging them into the other font's
`Font Info->Lookups` pane).

There is a popup menu, available by right clicking on an entry, which
provides these functions as well as:

- Save Lookup
    Saves the currently selected lookup to an [Adobe Feature
    File](../../reference/featurefile/) of its very own.

- Add 'aalt' features
    FontForge can automagically generate an 'aalt' feature consisting of
    every single and alternate substitution of each glyph.

- Add 'DFLT' script
    Add the DFLT script to all selected lookups

- Add language to script
    Add the specified language to the specified script in all selected
    lookups.

- Remove Language from script
    Removes the specified language from the specified script in all selected
    lookups.

- Save Feature File
    Saves all lookups (both GSUB and GPOS) to an [Adobe Feature
    File](../../reference/featurefile/).
 


### WOFF (Web Open Font Format)

![Font Info WOFF](/assets/img/dialogs1-fontinfo-woff.png)

This sub-dialog allows you to specify additional information which may
be stored in a woff file. A woff file is very similar to a standard sfnt
except that its tables are compressed, and it has a few additional data
fields. It has version number fields for the WOFF file, a major and a
minor version. If you leave these fields blank then fontforge will
generate defaults based on some of the other font version information
available to it.

It also has a metadata string. This is a small xml document (which ff
does not currently parse), stored in utf8. Its internal format is
specified in [a document from
Mozilla](http://people.mozilla.com/~jkew/woff/woff-2009-09-16.html). 


### Mac Style & FOND

![Font Info Mac Styles](/assets/img/dialogs1-fontinfo-macstyle.png)

This sub-dialog allows you to set the mac style of your font. Normally
FontForge will be able to guess the style from the fontname (and various
other clues), but sometimes the name will be non-standard (or perhaps
just in a language FontForge doesn't know about), and other times you
may wish to override this default setting.

If you are happy with the default, just leave the Automatic button
checked, if you wish to override check the button next to the list box.
You may select any combination of styles (remember to hold down the
control key to get multiple selections) except for one containing both
"Condense" and "Expand".

Note: If you want the style to be "Regular" then leave all styles
unselected.

The mac style is stored in the header of an sfnt (truetype or opentype
font file), but is most important in creating mac font families.

The FOND name is only used for generating mac families. It is a grouping
level underneath the family level. See the [FAQ](/about/faq/#How-family)
for a discussion on when to use this.


### Mac Features

![Font Info Mac Features](/assets/img/dialogs1-fontinfo-macfeat.png)

This sub-dialog allows you to create and remove Mac features from your
font. This will override the Mac features specified in the [preferences
dialog](../prefs/#Mac)for this particular font (for example to give a
more appropriate but local name to a certain feature setting).


### Dates

Displays what fontforge thinks is the create date and modification date
of the font data. FontForge started retaining those dates in August of
2006, any prior dates are conjectural and based on a best guess --
usually from the modification time of the sfd file. When loading a font
from somthing other than an sfd file, FontForge will again make the best
guess it can.


### Unicode Ranges
![](/assets/img/dialogs1-fontinfo-unicode.png)

Displays information about the various unicode character ranges included
in the font.

If you click on a range, the font view will select all characters in
that range and scroll to one of them.

If you double click on a range, the font view will select any characters
not defined in the font within that range, and scroll to one of them.
