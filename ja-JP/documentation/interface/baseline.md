---
published: true
layout: default.ja
title: ベースラインダイアログと OpenType BASE テーブル
---
<!--
published: true
layout: default
title: The baseline dialog, and the OpenType BASE table.
-->


![](/assets/img/dialogs1-BASEdlg.png)

<!--
This dialog may be invoked by `Element->Other Info->Horizontal Baselines`
(or `Vertical Baselines`). It allows you to control the baseline
(in either horizontal or vertical orientation) on which the glyphs of
a particular script line up. You may also control the spacing between
baselines, and the interline (or intercolumn) spacing on a per-script,
or even per-language basis.
-->
このダイアログは、
<span class="command">要素-\>その他の情報-\>水平ベースライン</span>
(または <span class="command">垂直ベースライン</span>)
から呼び出すことができます。
特定の文字のグリフが並ぶベースラインを (水平または垂直方向に) 制御できます。
また、ベースライン間の間隔、および行間隔 (または列間隔) を、
文字ごと、さらには言語ごとに制御できます。

<!--
See the [Baseline section](/en-US/tutorials/overview/#Baseline) in 
the overview for a description of why this is important.
-->
これが重要である理由については、
概要の
[ベースライン](../../../tutorials/overview/#baselines)
セクションを参照してください。

<!--
There are currently seven standard baselines. The distinctions between
them are described in the OpenType standard. (See the [baseline tags
section](http://partners.adobe.com/public/developer/opentype/index_tag4.html))
-->
現在、7 つの標準ベースラインがあります。
それらの違いは、OpenType 標準で説明されています。
([ベースラインタグ](http://partners.adobe.com/public/developer/opentype/index_tag4.html)
のセクションを参照)

<!--
Basically most alphabetic scripts will use the 'romn' baseline, most CJK
scripts will use the 'ideo'graphic baseline. Tibetan and other Indic
scripts will use the 'hang'ing baseline, and math fonts might use the
'math' baseline.
-->
基本的に、ほとんどのアルファベット文字は 'romn' ベースラインを使用し、
ほとんどの CJK 文字は 'ideo'graphic (表意文字) ベースラインを使用します。
チベット語やその他のインド系諸語で用いられる文字は 'hang'ing ベースライン (吊り下げベースライン) を使用し、
数学フォントは 'math' ベースラインを使用することになるでしょう。

<!--
Roughly the ideographic baseline will line up with the descenders of a
Latin (Greek, Cyrillic) script, and the hanging baseline will line up
with the ascenders.
-->
おおまかにいうと、
表意文字ベースラインは、
ラテン文字　(ギリシャ文字、キリル文字) の深さと一致し、
吊り下げベースラインは高さと一致します。

<!--
You need to select which baselines your font will support. You may want
to specify baselines that apply to scripts which aren't in your font --
this will mean your font is positioned reasonable when used with glyphs
from other fonts. In the example above, the font has no Indic
characters, but it still specifies a hanging baseline.
-->
フォントがサポートするベースラインを選択する必要があります。
フォントに含まれていないスクリプトに適用するベースラインを指定したいことがあるかもしれません
-- これは、他のフォントのグリフを使用するときにフォントが適切に配置されることを意味します。
上記の例では、フォントにはインド文字がありませんが、吊り下げベースラインを指定しています。

<!--
You select which baselines you will support by turning on the
appropriate checkboxes. All scripts will have the same set of baselines.
In every script one baseline will be the default baseline. Generally
glyphs in that script will be drawn with their vertical origin (If you
are working on horizontal baselines, that is) on that baseline. You then
should specify how other baselines are offset from this one.
-->
適切なチェックボックスをオンにして、サポートするベースラインを選択します。
すべての文字には同じベースラインのセットがあります。
各文字で、1 つのベースラインがデフォルトのベースラインになります。
通常、その文字内のグリフは、そのベースライン上に置かれた垂直方向の原点
(水平ベースラインで作業している場合)
を用いて描画されます。
次に、他のベースラインがこのベースラインからどのくらいオフセットするかを指定する必要があります。

![](/assets/img/dialogs1-BASElang.png)

<!--
You may also set the minimum and maximum extent of the
font for each script (by pressing the `[Set Extents]` button). This
corresponds roughly to a per-script line spacing (or column spacing).
-->
各文字のフォントの最小および最大範囲を設定することもできます
(<span class="command">範囲の設定</span>
ボタンを押します）。
これは、文字ごとの行間隔 (または列間隔) にほぼ対応しています。

<!--
You may specify a default spacing for the script in general, and then
more specific spacings for a given language.
-->
一般的な文字のデフォルトの間隔を指定してから、特定の言語のより具体的な間隔を指定することができます。

<!--
In the example at left the default spacing for the Latin script allows
room for one accent above capital letters. Now English doesn't have any
accents (usually), so it might make sense that English could use a
tighter line spacing (and, traditionally this has been done). On the
other hand Vietnamese stacks multiple accents above one another, so it
needs more room than the default.
-->
左の例では、ラテン文字のデフォルトの間隔により、大文字の上に1つのアクセントを入れることができます。
現在、英語にはアクセントがありません (通常)。
したがって、英語ではより狭い行間を使用できることは理にかなっています （従来はそうなっていました)。
一方、ベトナム語は複数のアクセントを積み重ねているため、デフォルトよりも多くのスペースが必要です。

<!--
But suppose you are typesetting French. Now French sometimes is printed
with capital accented letters, but sometimes a "À" will be drawn just as
"A" with no accent. So you might create at feature that maps capital
accented letters to their unaccented forms:
-->
しかし、あなたがフランス語を組版しているとします。
現在、フランス語ではアクセント記号付きの大文字を印刷することがありますが、
"À" をアクセント記号のない "A" と同じように描画することもあります。
そのため、大文字のアクセント付き文字をアクセントなしの形式にマッピングする機能を作成できます:

    feature NoAc {
      sub Agrave by A;
      sub Aacute by A;
      ...
      sub Egrave by E;
      ...
    } NoAc;

<!--
Then it would be convenient to be change the baseline spacing if these
feature were active. And, indeed you can. Simply select the line for
French (in this case the default language works for French) and press
the [Set Feature Extents] button.
-->
これらの機能が有効な場合、ベースライン間隔を変更できると便利です。
そして、それは実際にできます。
フランス語でベースラインを選択し
(この場合、デフォルトの言語はフランス語で機能します)、
<span class="command">機能範囲の設定</span>
ボタンを押します。

![](/assets/img/dialogs1-BASEfeat.png)

<!--
It is possible to set Extent information even if you do not provide
baseline
-->
ベースラインを提供しなくても、エクステント情報を設定することは可能です。
