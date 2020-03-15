---
published: true
layout: default.ja
title: ジャスティフィケーション情報
---
<!--
published: true
layout: default
title: The Justification Information
-->


![](/assets/img/dialogs1-JustifyDlg.png)

<!--
Text justification is handled differently in
different scripts and in different languages within those scripts.
-->
テキストのジャスティフィケーションは、
文字が異なれば、また、文字を使用する言語が異なれば、異なる処理が行われます。

<!--
In arabic special glyphs (called kashidas) are inserted into the text to
fill up space, in latin interword spacing and even the within word
letter spacing can be adjusted.
-->
アラビア文字では、特別なグリフ (カシダと呼ばれます) が空白をなくすようにテキストに挿入され、
ラテン文字では単語間の空きと、単語内の文字間の空きで調整できます。

<!--
But more sophisticated behaviors are possible. In some circumstances it
might be appropriate to turn off ligatures, something which (in latin at
least) will usually add a little more space to the line. In other cases
a special kerning lookup might be invoked.
-->
ですが、より洗練された動作を行うことができます。
場合によっては、合字をオフにすることが適切かもしれませんし、
大抵は (少なくともラテン文字では) 行にもう少し空白を追加することが適切でしょう。
また、特別なカーニング照合テーブルが呼び出される場合もあります。

<!--
OpenType allows a fairly general approach to this. Information is
organized by script, and then by language within the script.
-->
OpenType では、この問題に対し、かなり一般的なアプローチが可能になっています。
情報は文字ごとに編成され、次に文字を使用する言語ごとに編成されます。

![](/assets/img/dialogs1-JustifyExtenderDlg.png)

<!--
The extender list is specified at the script
level. You may either enter a series of glyph names into the space
provided in the dialog above, or click on the little box to the right
and a dialog will pop up giving a more convenient entry mechanism.
-->
エクステンダーリストは、文字レベルで指定されます。
上のダイアログで提供されるスペースに一連のグリフ名を入力するか、
右側の小さな四角をクリックしてより便利に入力できるダイアログをポップアップさせます。

<!--
Several different priority levels may be specified within a language.
The first priority level will be invoked to make small adjustments to
spacing. If this is not enough to fix the problem then the second level
will be invoked (in addition to the first, I believe). If the second
level is not enough then third, fourth, fifth... levels will be invoked
in turn until the line can be justified.
-->
言語内でいくつかの異なる優先度レベルを指定できます。
間隔を少し調整するために、
1 番目の優先度レベルが呼び出されます。
これで問題を修正するのに十分でない場合は、
(1 番目のレベルに加えて) 2 番目のレベルが呼び出されます。
2 番目のレベルが十分でない場合、
3 番目、4 番目、5 番目... のレベルが
行がジャスティフィケーションされるまで、順番に呼び出されます。

![](/assets/img/dialogs1-JustifyLangDlg.png)

<!--
Each priority level consists of two parts, a series of behaviors for
when the line is too long (and needs to be make smaller) and another
series for when the line is too short (and needs to be extended). Each
of these, in turn consists of a set of lookups (in either GPOS or GSUB)
to turn on, a set of lookups to turn off, and finally a special lookup
which specifies the maximum amount the advance width of a glyph can
change.
-->
各優先度レベルは、2 つの部分で構成されます。
ラインが長すぎる (そして短くする必要がある) 場合の一連の動作と、
ラインが短すぎる (そして長くする必要がある) 場合の別の一連の動作です。
これらはそれぞれ、
オンにする照合テーブル (GPOS か GSUB のいずれか) のセット、
オフにする照合テーブルのセット、
そして最後にグリフの可変送り幅の最大量を指定する特別な照合テーブルで構成されます。

![](/assets/img/dialogs1-JustifyLookupDlg.png)

<!--
So if you want to make a line shorter you might turn on ligatures and 
turn on kerning. Both of which (usually) make text shorter. On the other
hand if you want to make a line longer you might want to turn those same
lookups off.
-->
したがって、行を短くしたい場合は、合字をオンにし、カーニングをオンにします。
どちらも (通常は) テキストを短くします。 
一方、行を長くしたい場合は、同じ照合テーブルをオフにすることをお勧めします。

<!--
The maximum advance width lookups are a little different from normal
lookups. These may be either single positioning GPOS-style lookups or
kerning GPOS-style lookups. The lookup does not specify an exact
adjustment to a glyph's width, rather it specifies the maximum (in
absolute value) amount by which that glyph's width can change. So in
latin typesetting you might have a lookup with information solely for
the space glyph allowing it to (for instance) double in size when
expansion is needed, or half in size when contraction is needed -- or
any value between the normative amount and the adjusted maximum. At a
higher priority level there might be a set of lookups which adjust the
advance width of every glyph.
-->
最大送り幅の照合テーブルは、通常の照合テーブルとは少し異なります。
これらは、単独位置指定 GPOS スタイルの照合テーブル、
またはカーニング GPOS スタイルの照合テーブルのどちらかです。
照合テーブルは、グリフの幅の正確な調整値を指定するのではなく、
そのグリフの幅を変更できる最大量 (絶対値) を指定します。
したがって、ラテン植字では、空白グリフのみの情報で照合を行い、
拡張が必要な場合はサイズを 2 倍、
縮小が必要な場合はサイズを半分
-- または、標準値と調整可能な最大範囲の間のどこかの値にすることができます。
より高い優先度レベルでは、
すべてのグリフの送り幅を調整する照合テーブルのセットがあるかもしれません。

<!--
In theory you could use a kerning lookup to specify the maximum width
adjustment allowed between any two glyphs. (The OpenType spec actually
says that *any* GPOS lookup could be used, except for contextual ones
(which makes one wonder if contextual chaining lookups are permitted),
no semantics are provided for these other lookup types and it is hard to
imagine what they might do, so I'm ignoring them).
-->
理論的には、カーニング照合を使用して、任意の 2 つのグリフ間で許可される最大調整幅を指定できます。
(OpenType 仕様では、実際には *任意の* GPOS 照合を使用できると述べていますが、
コンテキスト照合
(コンテキストチェーン照合が許可されているかどうかは疑問に思われます)
を除き、
他の照合タイプにはセマンティクスが提供されておらず、何を行うか予想するのは困難ですので、
私はそれらを無視しています)。

<!--
These maximum lookups look like GPOS lookups, but are stored in the JSTF
table. FontForge will display them in the GPOS lookup list but will
output them the JSTF table when appropriate.
-->
これらの最大値用照合テーブルは GPOS 照合のように見えますが、
JSTF テーブルに保存されます。
FontForge はそれらを GPOS 照合リストに表示しますが、
必要に応じて JSTF テーブルを出力します。
