---
published: true
layout: default.ja
title: エンコーディングメニュー
---
<!--
published: true
layout: default
title: Encoding Menu
-->


[table_of_contents]


<!--
#### Reencode
-->
#### エンコーディング変換(R) (Reencode)

<!--
Has an attached sub-menu of standard and user defined encodings. The
font's current encoding will be indicated with a check mark. You may
change the encoding by selecting a different entry.
-->
このメニューには標準およびユーザ定義のサブメニューが付属しています。
フォントの現在のエンコーディングにはチェックマークがついています。
別の項目を選択することによってエンコーディングを変換できます。

<!--
There are two slightly different formats an encoding can take. It can be
defined by unicode code points, or it can be defined by glyph names.
When reencoding to an encoding defined by code points, the glyph with
the matching unicode value is placed in the encoding slot. When
reencoding to an encoding defined by glyph name, we first search for a
glyph with the matching name and use it, if not found we search for the
glyph name's corresponding unicode code point (if any) and if found we
change its name to that specified by the encoding.
-->
エンコーディングは、2 つの僅かに異なる形式が可能です。
それは Unicode の符号位置かグリフ名によって定義することができます。
符号位置によって定義されたエンコーディングに変換したときは、
それに一致する Unicode 値がエンコーディングスロットに割り当てられます。
グリフ名によって定義されたエンコーディングに変換したときは、
一致する名前をもつグリフを最初に検索し、
見つかった場合はそれを使用します。
見つからなかった場合は、
グリフ名に対応する Unicode 符号位置 (があれば) を検索し、
グリフがあればその名前をエンコーディングによって指定されている名前に変更します。

<!--
Example: Suppose we have a font containing a glyph named "uni0041", and
an encoding which maps U+0041-\>slot 65, then the glyph will be moved
into slot 65. If we have another encoding which maps "A" -\> slot 65,
then (since "A" has unicode value U+0041) our glyph will still be mapped
to slot 65, but in addition its name will be changed to "A".
-->
例: "uni0041" という名前のグリフを含むフォントがあったとして、
そのエンコーディングでは U+0041-\>スロット 65 に対応づけられていたとすると、
グリフはスロット 65 に移動します。
もし、"A"-\>スロット 65 への対応づけを行っている別のエンコーディングがあったとすると、
("A" の Unicode 値は U+0041 なので)
エンコーディング変換後のグリフはスロット 65 に置かれたままですが、
その名前は "A" に変更されます。


<!--
#### Compact
-->
#### コンパクト化(C) (Compact)

<!--
Remove any holes from the encoding so all the glyphs get smushed
together. If the font is already compact, then selecting this again will
restore the original.
-->
エンコーディングからすべての隙間を取り除き、
全グリフは一繋がりに押し潰されます。
フォントがすでにコンパクト化されている場合、
もう一度これを選択するとオリジナルに復元します。


<!--
#### Force Encoding
-->
#### エンコーディングを強制(F) (Force Encoding)

<!--
Has the same sub-menu as above. Here we assume that the glyphs of the
font are currently encoded in the right order, but they have the wrong
names (This may seem odd, but it happens a lot). This command will
change the names of all the glyphs to match what they should be if the
indicated encoding were in force.
-->
上記の
<span class="command">エンコーディング変換(R)</span>
と同じサブメニューを含みます。
このメニューでは、フォント内のグリフが正しい順番に並んでいて、
名前の方が間違っていると見なします (これは奇妙に感じますが、よくあることです)。
このコマンドは、全てのグリフの名前を、
エンコーディングで指定された名前に強制的に変更します。


<!--
#### Add Encoding Slots...
-->
#### エンコーディングスロットを追加(A)... (Add Encoding Slots...)

<!--
Add some extra slots at the end of the font into which you can put
unencoded glyphs (variant glyphs, etc.)
-->
幾つかの追加スロットをフォントの末尾に追加します。
それらはエンコーディングに含まれないグリフ (異体字グリフなど) を定義するのに使用できます。


<!--
#### Remove Unused Slots
-->
#### 未使用のスロットを削除(U) (Remove Unused Slots)

<!--
Removes any unused slots from the end of the font. It does not remove
unused slots inside the font, that would screw up the encoding.
-->
フォントの末尾にある任意の未使用スロットを削除します。
フォントの途中にあるスロットは削除できません。
それを行うとエンコーディングが壊れてしまいます。


<!--
#### Detach Glyphs
-->
#### グリフの切り離し(D) (Detach Glyphs)

<!--
Detaches any selected encoding slots from their currently associated
glyphs. These slots will now be marked as unused. The glyphs will remain
in the font, just not encoded (If you reencode the font those glyphs
will become visible again).
-->
選択した全てのエンコーディングスロットを、
現在割り当てられているグリフからきりは生します。
それらのスロットは未使用のものとマークされます。
グリフはフォント内に残ります。
文字符号が割り当てられていないだけです
(エンコーディング変換を行うと、それらのグリフはまた見えるようになります)。


<!--
#### Detach & Remove Glyphs...
-->
#### グリフの切り離し・削除(V)... (Detach & Remove Glyphs...)

<!--
Similar to the above except that any glyphs detached (which are not used
elsewhere in the encoding) will be removed from the font.
-->
上と同様ですが、切り離されたグリフ
(のうち、エンコーディングの他の箇所で使用されていない物)
のすべてをフォントから削除します。


<!--
#### Add Encoding Name...
-->
#### エンコーディングの名前を追加(N)... (Add Encoding Name...)

<!--
Requests an encoding name from the user and searches for it in the
iconv() database. It then adds that encoding to the menu.
-->
ユーザにエンコーディング名を問い合わせ、
それを iconv() データベースから検索します。
それがあれば、そのエンコーディングをメニューに追加します。


<!--
#### Load Encoding...
-->
#### エンコーディングを読み込み(L)... (Load Encoding...)

<!--
Asks the user for a filename and attempts to load a user defined
encoding from that file. (You can only load small encodings -- one byte
encodings)
-->
ユーザにファイル名を問い合わせ、
ユーザ定義のエンコーディングをそのファイルから読み込もうと試みます。
(読み込むことができるのは、小さなエンコーディング
-- 1 バイトエンコーディングだけです)


<!--
#### Make from Font...
-->
#### フォントから作成(K)... (Make from Font...)

<!--
Allows you to name the font's current encoding (if it isn't already
named), and add it to the encoding menu.
-->
フォントの現在のエンコーディングに (既存の物と重ならない) 名前をつけ、
エンコーディングメニューに追加することができます。


<!--
#### Remove Encoding...
-->
#### エンコーディングを削除(C)... (Remove Encoding...)

<!--
Removes one of the user defined encodings from the menu.
-->
ユーザ定義のエンコーディングを一つ削除します。


<!--
#### Display by Group...
->
#### グループ毎の表示(G)... (Display by Group...)

<!--
Allows you restrict the glyphs displayed in the font view to those in a
user defined [group](../groups/) (specified in the next command).
-->
フォントビューに表示されたフォントを、
ユーザが定義した
[グループ](../groups/)
(次のコマンドで定義できます) に制限します。


<!--
#### Define Groups...
-->
#### グループを定義(E)... (Define Groups...)

<!--
Allows you to define [groups](../groups/) of glyphs which (presumably)
have some meaningful connection to each other.
-->
相互に何らかの繋がりをもつ (と見ることができる) グリフの
[グループ](../groups/)
を定義することができます。


<!--
#### Save NameList of Font...
-->
#### フォントの名前リストを保存(S)... (Save NameList of Font...)

<!--
Creates a [namelist](#NameLists) file mapping unicode to the glyph names
of the current font.
-->
現在のフォント内のグリフ名を Unicode に対応づける
[名前リスト](#名前リスト)
ファイルを作成します。


<!--
#### Load NameList...
-->
#### 名前リストを読み込み(O)... (Load NameList...)

<!--
Loads a [namelist](#NameLists) file into fontforge and copies it so that
fontforge will load it on start up in the future.
-->
[名前リスト](#名前リスト)
ファイルを FontForge に読み込み、
将来 FontForge を起動した時に読み込めるようにコピーします。


<!--
#### Rename Glyphs...
-->
#### グリフ名を変更(Y)... (Rename Glyphs...)

<!--
Allows you to specify a [namelist](#NameLists). All glyphs in the current
font will be renamed to match the scheme in the namelist.
-->
このコマンドでは
[名前リスト](#名前リスト)
を指定できます。
現在のフォント内のすべてのグリフは名前リストの様式に合うように改名されます。


<!--
#### Create Named Glyphs...
-->
#### 名前を指定してグリフを作成(A)... (Create Named Glyphs...)

<!--
Allows you to specify a file containing a list of glyph names. FontForge
will create a sequence of unencoded glyphs with these names. This might
be useful if all your fonts contain small caps and you always want to
have the names "A.small", "B.small", "C.small" etc. or perhaps you
always want the ligatures "longs\_longs\_t", "f\_longs", "f\_j", etc.
-->
このコマンドでは、グリフ名のリストを含むファイルを指定することができます。
FontForge は文字コードが割り当てられていないグリフの列を指定した名前で作成します。
これは例えば、あなたが作るフォントが必ずスモールキャップスを含んでいて、
それらを常に "A.small", "B.small", "C.small" のように命名したい時に役立つはずですし、
常に "longs_longs_t", "f_longs", "f_j" 等の名前を使いたい場合にもたぶん役立つでしょう。


<!--
## General notes on encodings
-->
## エンコーディングに関する一般的な注意

<!--
Not all font formats support all encodings. SVG fonts will always be
output in a unicode encoding, truetype fonts in either unicode or one of
the CJK encodings, type1 fonts only support single byte encodings, etc.
-->
すべてのフォントフォーマットが全てのエンコーディングをサポートするわけではないことにご注意ください。
SVG フォントは常に Unicode エンコーディングで出力され、
TrueType では Unicode か CJK エンコーディングのどれかを選ぶことができ、
Type1 フォントは 1 バイトエンコーディングしかサポートしていないなどです。

<!--
In a CID keyed font you are not allowed to change the encoding (in
essence because there is none), but there is an entry [CID-\>Change
Supplement](../cidmenu/#ChangeSup)which will display the
Registry/Ordering information and allow you to change the supplement.
-->
CID キー指定フォントではエンコーディングを変更することはできません
(本質的にエンコーディングが存在しないため)
が、
[<span class="command">CID->補遺番号を変更</span>](../cidmenu/#change-supplement)
コマンドでレジストリ/順序づけの情報を表示し、補遺番号を変更することができます。

<!--
### Built in Encodings
-->
### 組み込みのエンコーディング

<!--
FontForge knows about the following encodings by default:
-->
FontForge は、デフォルトで以下のエンコーディングについて知っています。

<!--
-   ISO-8859-1 (Latin1) -- traditional encoding for western european
    characters. Default encoding for http. Does not include the Euro
    sign.
-   ISO-8859-15 (Latin0) -- Replacement for Latin1. Does include the
    Euro.
-   ISO-8859-2 (Latin2) -- Central & Eastern European (Czech, Hungarian,
    Polish, Romanian, Croatian, Slovak, Slovnian.
-   ISO-8859-3 (Latin3) -- Southern European (Esperanto, Maltese)
-   ISO-8859-4 (Latin4) -- Northern European (Estonian, Latvian,
    Lithuanian, Greenlandic, Lappish)
-   ISO-8859-9 (Latin5) -- Turkish
-   ISO-8859-10 (Latin6) -- Nordic (reworking of Latin4&Latin1)
-   ISO-8859-13 (Latin7) -- Another Baltic character set
-   ISO-8859-14 (Latin8) -- Celtic (Gaelic & Welsh)
-   ISO-8859-5 (Cyrillic)
-   ISO-8859-6 (Arabic)
-   ISO-8859-7 (Greek)
-   ISO-8859-8 (Hebrew) -- (and Yiddish)
-   ISO-8859-11 (Thai) -- Also know as TIS 620 (there is no ISO-8859-12)
-->
-   ISO-8859-1 (Latin1) -- 西ヨーロッパの伝統的エンコーディングです。
    HTTP のデフォルトエンコーディングです。
    ユーロ記号は含まれません。
-   ISO-8859-15 (Latin0) -- Latin1に代るコードです。
    ユーロ記号を含んでいます。
-   ISO-8859-2 (Latin2) -- 中央ヨーロッパおよび東ヨーロッパ
    (チェコ語、ハンガリー語、ポーランド語、ルーマニア語、クロアチア語、スロバキア語、スロベニア語)。
-   ISO-8859-3 (Latin3) -- 南ヨーロッパ (エスペラント、マルタ語)
-   ISO-8859-4 (Latin4) -- 北ヨーロッパ (エストニア語、ラトビア語、リトアニア語、グリーンランド語、ラップ語)
-   ISO-8859-9 (Latin5) -- トルコ語
-   ISO-8859-10 (Latin6) -- 北欧諸語 (Latin4 と Latin1 の作り直し)
-   ISO-8859-13 (Latin7) -- その他のバルト諸言語用の文字セット
-   ISO-8859-14 (Latin8) -- ケルト諸語 (ゲール語とウェールズ語)
-   ISO-8859-5 (Cyrillic)
-   ISO-8859-6 (Arabic)
-   ISO-8859-7 (Greek)
-   ISO-8859-8 (Hebrew) -- (およびイディッシュ語)
-   ISO-8859-11 (Thai) -- 別名 TIS 620 (ISO-8859-12 はありません)

    * * * * *

<!--
-   KOI8-R -- Cyrillic
-   Macintosh Roman
-   Windows "ANSI" (CodePage1252)
-   Adobe Standard
-   Symbol
-   TeX Base
-->
-   KOI8-R -- キリル文字
-   Macintosh Roman
-   Windows "ANSI" (CodePage1252)
-   Adobe Standard
-   Symbol
-   TeX Base

    * * * * *

<!--
-   ISO-10646-1 (Unicode, BMP)
-   ISO-10646-1 (Unicode, Full)
-   ISO-10646-? (Unicode, by plane)  
    (You can select a specific plane of unicode as an encoding
    (ie BMP, SMP, SIP,...)
-->
-   ISO-10646-1 (Unicode, 基本多言語面 BMP)
-   ISO-10646-1 (Unicode, すべて)
-   ISO-10646-? (Unicode, 面を指定)<br>
    (Unicode の特定の面 (BMP, SMP, SIP など) を 1 つのエンコーディングとして選べます。

    * * * * *

<!--
-   SJIS
-   JIS 208 -- Japanese Kanji (first 8000 characters)
-   JIS 212 -- Japanese Kanji (next 8000 characters)
-   Wansung
-   KSC 5601 -- Korean (this is the 94x94 version of KSC 5601)
-   Johab
-   GB 2312 -- Simplified Chinese
-   Packed GB 2312 -- (I don't know what the proper name for this is,
    ASCII for bytes\<0x80, and GB 2312 EUC offset by 0x8080)
-   Big5 -- Traditional Chinese
-->
-   SJIS
-   JIS 208 -- 日本語の漢字 (最初の 8000 文字)
-   JIS 212 -- 日本語の漢字 (次の 8000 文字)
-   Wansung
-   KSC 5601 -- 韓国語 (これは KSC 5601 の 94×94 バージョンです)
-   Johab
-   GB 2312 -- 簡体字中国語
-   Packed GB 2312 -- (正確な名前は不明です。
    ASCII を 0x80 未満のバイトに割り当て、GB 2312 を 0x8080 だけオフセットした EUC)
-   Big5 -- 繁体字中国語

    * * * * *

<!--
-   Custom -- An unknown encoding
-   Glyph Order -- the glyph ordering used in the original font file.
-->
-   Custom -- 不明なエンコーディング
-   Glyph Order -- オリジナルのフォントファイルで使用されているグリフ順


<!--
Encoding sources:
-->
エンコーディングに関する情報源:

<!--
-   [ISO 8859 Alphabet Soup](http://czyborra.com/charsets/iso8859.html)
-   [Unicode Mapping Tables](http://www.unicode.org/Public/MAPPINGS/)
-->
-   [ISO 8859 符号表 (Alphabet Soup)](http://czyborra.com/charsets/iso8859.html)
-   [Unicode の対応表](http://www.unicode.org/Public/MAPPINGS/)

<!--
[An index to images of all the glyphs in
unicode](http://www.unicode.org/charts/).
-->
[Unicode のグリフすべての画像へのインデックス](http://www.unicode.org/charts/)。


<!--
### User Defined Encodings
-->
### ユーザ定義のエンコーディング (User Defined Encodings)

<!--
You can also add new encodings to the set that FontForge knows about.
There are three menu items that manipulate a set of user defined
encodings. As always these specify both a character set and an encoding.
The encoding has a maximum of 256 entries, but the character set may be
larger (up to 1024). This means that you can define a font with extra
characters. Since postscript fonts can be reencoded at runtime this can
be useful.
-->
FontForge が知っているエンコーディング一覧に新しいエンコーディングを追加することもできます。
ユーザ定義のエンコーディング群を操作するためのボタンは 3 つ用意されています。
標準のエンコーディングと同様に、これらは文字セットと符号化方式の両方を指定します。
エンコーディングは最大 256 項目を含むことができますが、文字セットはそれより大きくても構いません
(1024 文字まで)。
これは、追加の文字を含むフォントを定義できるということです。
PostScript フォントは実行時にエンコーディングを切り替えることができるので、これが役に立つ場合があります。

<!--
The Load Encoding command allows you to load an encoding(s) from a file.
Currently the file must either be in the format used by the unicode
consortium for [mapping ISO
8859](http://www.unicode.org/Public/MAPPINGS/ISO8859/) encodings to
unicode, or it must be a postscript encoding array. The first format
looks like this:
-->
<span class="command">エンコーディングを読み込む</span>
コマンドを実行すると、エンコーディングをファイルから読み込むことができます。
現在のところ、ファイルは
Unicode Consortium が
ISO 8859 の各エンコーディングを Unicode に対応づけるのに使っている
[フォーマット](http://www.unicode.org/Public/MAPPINGS/ISO8859/)
か、
PostScript のエンコーディング配列でなければなりません。
最初の形式は以下のような形です:

    0x20      0x0020  #   空白 (SPACE)
    0x21      0x0021  #   感嘆符 (EXCLAMATION MARK)
    ...

<!--
A postscript file looks like:
-->
PostScript ファイルは以下のような形です:

    /TeXBase1Encoding [
     % 00
     /.notdef /dotaccent /fi /fl
     /fraction /hungarianumlaut /Lslash /lslash
     ...
    ] def

<!--
There may be more than one encoding in a postscript file. The encoding
parser is not smart. It will only read arrays specified like this, don't
try any of the innumerable other ways of specifying an array in
postscript.
-->
PostScript ファイルには複数のエンコーディングを含めることができます。
エンコーディングの読み込み処理は賢くありません。
このような形で指定されたエンコーディングしか読み込めないので、
PostScript で配列を指定する他の無数の方法を試みないでください。

<!--
If the font has a custom encoding then the `Make From Font` menu item is
enabled. This allows you to name the encoding you have defined for the
current font.
-->
フォントにカスタムエンコーディングがある場合、
<span class="command">フォントから作成</span>
メニューが選択できるようになります。
これを使って、現在のフォントに対して定義したエンコーディングに名前をつけることができます。

<!--
The `Remove Encoding` menu item brings up a list showing all the custom
encodings and allows you to delete them.
-->
<span class="command">エンコーディングを削除</span>
メニューを選択すると、すべてのカスタムエンコーディングを列挙するリストが表示され、それらを削除することができます。

<!--
Here's an [example of a postscript encoding file](Encodings.ps.gz). It
contains:
-->
ここに
[PostScript エンコーディングファイルの例](/assets/old/Encodings.ps.gz)
があります。
それには以下のエンコーディングが含まれています:

-   TeXMathItalicEncoding
-   TeXMathSymbolEncoding
-   TeXMathExtensionEncoding

    * * * * *

<!--
-   IsoLatin -- (which specifies all the characters used in any of the
    ISO-Latin-\* fonts
-->
-   IsoLatin -- (これは、ISO-Latin-\* フォントのどれかに含まれる文字をすべて指定しています)

    * * * * *

<!--
-   AdobeExpert -- (Which contains things like lower case numbers, small
    caps, fractions, sub/superscript numbers, etc.)
-->
-   AdobeExpert -- (これはノンライニング数字、スモールキャップス、分数、下つき/上つき数字などを含みます。)

    * * * * *

<!--
-   CodePage1250 -- Microsoft's encoding for Central European characters
-   CodePage1251 -- Microsoft's Cyrillic encoding
-   CodePage1252 -- Microsoft's Western European encoding (a superset of
    Latin1. Sometimes called "ANSI" though I can find no ANSI standard
    that it follows)
-   CodePage1253 -- Microsoft's Greek encoding
-   CodePage1254 -- Microsoft's Turkish encoding
-   CodePage1255 -- Microsoft's Hebrew encoding (an extension of
    ISO-8859-8)
-   CodePage1256 -- Microsoft's Arabic encoding
-   CodePage1257 -- Microsoft's Baltic encoding
-   CodePage1258 -- Microsoft's Viet Namese encoding
-   CodePage874 -- Microsoft's Thai encoding
-->
-   CodePage1250 -- Microsoft の中央ヨーロッパの諸文字用エンコーディング
-   CodePage1251 -- Microsoft のキリル文字エンコーディング
-   CodePage1252 -- Microsoft の西ヨーロッパ用エンコーディング
    (Latin1 のスーパーセット。時に "ANSI" と呼ばれますが、これを定めた ANSI 規格の存在は見つかりません。)
-   CodePage1253 -- Microsoft のギリシャ語エンコーディング
-   CodePage1254 -- Microsoft のトルコ語エンコーディング
-   CodePage1255 -- Microsoft のヘブライ語エンコーディング (ISO-8859-8 の拡張)
-   CodePage1256 -- Microsoft のアラビア語エンコーディング
-   CodePage1257 -- Microsoft のバルト諸言語エンコーディング
-   CodePage1258 -- Microsoft のベトナム語エンコーディング
-   CodePage874 -- Microsoft のタイ語エンコーディング

    * * * * *

-   MacCentralEuropean
-   MacCyrillic
-   MacGreek
-   MacHebrew

    * * * * *

<!--
-   US-ASCII -- Not really useful by itself any more, but provides the
    first 128 characters of almost every other encoding.
-->
-   US-ASCII -- それ自身ではもはや本当に役立つわけではありませんが、
    その他ほとんどすべてのエンコーディングの最初の 128 文字を提供します。


<!--
## NameLists
-->
## 名前リスト

<!--
Adobe has established a standard glyph naming convention which provides
intelligible names for many glyphs of unicode characters. And some
unintelligible names too.
-->
Adobe は、多数の Unicode 文字に人が読んで理解可能なグリフ名をつけた命名規約を定めています。
その中には訳の分からない名前もいくつか含まれています。

<!--
A [namelist](/en-US/tutorials/overview/#Glyph-names) is just a mapping from unicode
to glyph names (a glyph name must be made up of alphanumeric characters
(or the special characters '.' or '\_'), it may not begin with a digit,
and it must be 31 or fewer characters in length.
-->
[名前リスト](/ja-JP/tutorials/overview/#glyph-names--namelists)
は Unicode からグリフ名への対応づけにすぎません。
グリフ名は英数字 (および特殊文字 '.' と '\_') からなり、
数字で始まらない長さ 31 文字以内の文字列でなければなりません。

<!--
FontForge provides a series of standard namelists:
-->
FontForge はいくつかの標準名前リストを提供しています:

<!--
-   Adobe Glyph List  
    This is the set of names that Adobe publishes on the web.

-   AGL For New Fonts
    This is the set of names that Adobe recommends for new fonts, without
    odd names like `"afiiXXXXX" or incorrect commaaccent names. 

-   AGL without afii  
    The cyrillic and hebrew glyphs have been assigned some very odd
    names (afiiXXXXX) and some people prefer not to use them. This 
    is now redundant; AGL for New Fonts should be used instead.

-   AGL with PUA  
    Adobe has assigned part of the unicode public use area to hold some
    standard glyph variants like small caps, subscripts, old-style
    numbers, etc.

-   Greek small caps  
    I've added some greek small cap assignments

-   TeX Names  
    The TeX typesetting system has its own set of names

-   AMS Names  
    The American Mathematical Society has its set of names (see the
    American Mathematical Society's
    [specification](http://www.ams.org/STIX/bnb/stix-tbl.asc-2003-10-10))
-->
-   Adobe グリフ名 (AGL)  
    これは、Adobe が Web 上で公開している名前セットです。

-   AGL (新規フォント用)  
    これは Adobe が新規フォント用に推奨する名前のセットで、
    "afiiXXXXX" のような奇妙な名前や間違ったカンマアクセント名を含みません。

-   AGL (afii を除く)  
    キリル文字とヘブライ文字には非常に奇妙な名前 (afiiXXXXX) がつけられており、
    それを使いたくない人が何人かいます。

-   AGL (私用領域 PUA を含む)  
    Adobe は、Unicode の私用領域の一部を、小型大文字・下つき文字・ノンライニング数字など、
    いくつかの標準的な異体字を保持するために割り当てています。

-   ギリシャ文字のスモールキャップス  
    私は、いくつかのギリシャ文字のスモールキャップスの割り当てを追加しました。

-   TeX 名  
    TeX 組版システムは独自の名前セットを定めています。

-   AMS 名  
    米国数学会 (AMS) は独自の名前セットを定めています。
    (AMS の
    [仕様書](http://www.ams.org/STIX/bnb/stix-tbl.asc-2003-10-10)
    を参照してください)。

<!--
You may define your own namelist file. It should have the extension
".nam". And it should contain a series of lines that look like:
-->
あなた自身の名前リストを定義することができます。
名前リストは拡張子 ".nam" をつける必要があります。
その中には以下のような行の並びが含まれます:

    0x0020 space
    0x0021 exclam
    0x0022 dblquote

<!--
In many cases you will just want to make a few modifications to an
already existing namelist. You can write:
-->
多くの場合、既存の名前リストに 2, 3 の追加を行いたいだけでしょう。
以下のように書くことができます:

    Based: Adobe Glyph List
    0x0021 exclamation

<!--
Which means the namelist is the same as the Adobe Glyph List except that
in your system U+0021 will be called "exclamation" rather than "exclam".
-->
この記述は、この名前リストが Adobe グリフリストと同じで、
U+0021 が "exclam" ではなく "exclamation" という名前になっているだけが違います。

<!--
Any glyphs you do not explicitly name will be named "uniXXXX" or
"uXXXXX" where XXXX is the unicode value in hex. The prefix "uni" will
be used for glyphs in the BMP, the prefix "u" for glyphs outside.
-->
リストに明記して名前をつけていないグリフはすべて "uniXXXX" または "uXXXXX" という名前になります
(ここで XXXX は 16 進表記の Unicode 値を表します)。
接頭辞 "uni" は BMP 内のグリフに、接頭辞 "u" は BMP に含まれないグリフにつけられます。

<!--
I said that glyph names should contain only alphanumeric characters (and
some others). But really this is only true of glyph names that get
output into a font. If you design your own namelist you may include
whatever glyph names you like, using (almost) the full range of unicode
-- provided you rename all your glyphs to Adobe's names before you
generate a font. If you use non-ASCII characters you should encode the
file in utf-8.
-->
いま、グリフ名は英数文字 (および他の少数の文字) のみを含むべきであると述べました。
しかし実際にはそれは、グリフ名がフォント内に出力される場合のみ当てはまる事実です。
独自の名前リストを作成した場合、
Unicode の (ほとんど) 全範囲を使用して、
どのようなグリフ名でも好きにつけることができます
-- ただし、フォントを出力する前に全てのグリフ名を Adobe の名前に変換することが前提です。
非 ASCII の文字名を使用した場合、ファイルを UTF-8 で符合化する必要があります。

<!--
FontForge normally will restrict glyph names to be within the ASCII
range, but if you go to File-\>Preferences-\>Generic-\>UnicodeGlyphNames
and set it on you can use unicode.
-->
通常は FontForge はグリフ名を ASCII の範囲に制限してしますが、
<span class="command">ファイル(F)-\>環境設定(E)...-\>一般-\>Unicodeグリフ名</span>
を選択し、この欄をセットすれば Unicode を使用することができます。

<!--
I've created a [french namelist](ListeDesGlyphs.nam) which uses accented
letters. This will work fine within fontforge, and most rasterizers will
parse fonts generated using such names -- but they are non-standard and
may cause problems. Best to do a rename just before generating your
font.
-->
私はアクセント付き文字を使用する
[フランス語の名前リスト](/assets/old/ListeDesGlyphes.nam)
を作成しました。
これは FontForge ではうまく動作していますし、
ほとんどのラスタライザはこのような名前を使用して出力されたフォントを解析することができるでしょう
-- しかしこれは非標準ですので問題を起こすことでしょう。
フォントを出力する前に改名するに如くはありません。

<!--
So if you find it easier to work with names other than those Adobe has
established you may create your own namelist file. Then use
[Encoding-\>Load NameList...](#Load.NameList...) to load that into
FontForge (you only need do this once, FontForge should remember it
thereafter). You may use
[File-\>Preferences-\>Font Info](../prefs/#NewFontNameList) to decree that
all your new fonts will use this namelist. You can change a font's
namelist with either:
-->
ですから、Adobe が決めた名前以外で作業した方が楽なのでしたら、
自前の名前ファイルを作成することができます。
ファイルを作成したら
[<span class="command">エンコーディング(N)->名前リストを読み込み(O)...</span>](#名前リストを読み込みo-load-namelist)
で、あなたが今後作成するすべてのフォントがこの名前リストを使用するように命令することができます。
[<span class="command">ファイル->環境->フォント情報</span>](../prefs/#NewFontNameList)
で、すべての新しいフォントがこの名前リストを使用することを宣言できます。
フォントの名前リストを変更するには、以下の 2 つの方法があります:

<!--
-   [Element-\>Font
    Info-\>General-\>NameList](../fontinfo/#PS-General)  
    Which will change the way new glyphs are assigned names

-   [Encoding-\>Rename Glyphs...](#Rename.Glyphs...)  
    Which will rename existing glyphs as well as changing the way new
    glyphs are named.
-->
-   [<span class="command">エレメント(L)->フォント情報(F)->一般情報->名前リスト</span>](../fontinfo/#PS-General)  
    新しいグリフに割り当てられる名前を変更します。
-   [<span class="command">エンコーディング(N)->グリフ名を変更(Y)...</span>](#グリフ名を変更y-rename-glyphs)  
    既存のグリフ名を、新規のグリフの命名既約に従って変更します。

<!--
You may also want to force a rename of all glyphs when you Open a font,
and the open dialog now lets you do this. Similarly when generating a
font you will probably want to force that font to be use the standard
names of the Adobe Glyph List.
-->
フォントを開いた時に全グリフを強制的に改名したい場合もあるでしょう。
現在のファイルオープンダイアログではそう指定することができます。
同様に、フォントの出力時にそのフォントを Adobe グリフリストの標準名を使用するように強制したほうがいいでしょう。
