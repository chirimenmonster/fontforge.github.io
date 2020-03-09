---
published: true
layout: default.ja
title: ヒントメニュー
---
<!--
published: true
layout: default
title: The Hints Menu
-->

<!--
This menu is only present in the outline glyph view and the font view.
 [A more detailed description of the hinting UI](../hinting/).
-->
このメニューはアウトライングリフビューとフォントビューにしか存在しません。<br>
 ヒントづけ UI のもっと詳しい解説は
[こちら](../hinting/)
にあります。

[table_of_contents]


<!--
#### AutoHint
-->
#### 自動ヒント(H) (AutoHint)

<!--
The Auto Hint command causes FontForge to throw away any existing hints
for the glyph and guess an new ones. In the outline view this operates
on the current glyph, in the font view it operates on all selected
glyphs.
-->
<span class="command">自動ヒント(H)</span>
コマンドを使うと、
FontForge はそのグリフに設定された既存のヒントを放棄して新しく推測したヒントを追加します。
アウトライングリフビューでは現在のグリフに対してこれを行い、
フォントビューでは選択中のすべてのグリフに対して行います。

<!--
FontForge will do a better job hinting a font if you have previously
set the BlueValues, StdVW and StdHW fields in [Element-\>Font Info-\>PS
Private](../fontinfo/#Private). These in turn depend on the hints so it
is best to autohint the entire font, then set the above values, and then
autohint the font again.
-->
FontForge は、
[<span class="command">エレメント(L)->フォント情報(F)->PS Private辞書</span>](../fontinfo/#private--font-wide-postscript-hinting)
の
`BlueValues`, `StdVW`, `STDHW`
フィールドをあらかじめ設定しておくと、
より高品質なヒントづけ処理を行います。
これらの値もヒントに依存するので、
まずフォント全体に自動ヒントづけを行い、
それから上記の値を設定し、
最後にフォントを再び自動ヒントづけすると、
最も良い結果が得られます。

<!--
If you wish to use AutoInstr below you should first AutoHint your font
with `File->Preferences->PS Hints->Detect Diagonal Stems` enabled.
-->
以下の
<span class="command">ヒント命令の自動生成(I)</span>
を使用する場合は、
まず、
<span class="command">ファイル-\>設定-\>PSヒント-\>対角ステムの検出</span>
を有効にして、
フォントに
<span command="class">自動ヒント(H)</span>
を実行する必要があります。


<!--
#### Hint Substitution Pts
-->
#### ヒントが置換する点(S) (Hint Substitution Pts)

<!--
In the font view this figures substitution points for all selected
glyphs. In the outline glyph view, this figures substitution points for
the current glyph using the current hint set.
-->
フォントビューでこのコマンドを実行すると、
選択中の全てのグリフに対して置換が行われる点を表示します。
アウトライングリフビューでは、
現在のヒントセットを使用して現在のグリフで置換が行われる点を表示します。


<!--
#### Auto Counter
-->
#### 自動カウンタヒント(C) (Auto Counter)

<!--
Attempt to figure out counter groups for the selected glyphs (font view)
or the current glyph (outline glyph view).
-->
選択中のグリフのカウンタグループを表示しようと試みます
(フォントビューの場合)。
または現在のグリフのカウンタグループを表示しようと試みます
アウトライングリフビューの場合)。


<!--
#### Don't AutoHint
-->
#### 自動ヒントを停止(D) (Don't AutoHint)

<!--
Tells FontForge not to do any implicit hinting on the selected glyphs.
(FontForge will normally perform an autohint on a glyph if the glyph's
contours have changed since it was last hinted and the user has not
explicitly changed the hints). The user may turn this flag off by
invoking AutoHint explicitly.
-->
選択中のグリフに対し、FontForge が暗黙のヒントづけをまったく行わないように指示します。
(通常の場合は FontForge は、
あるグリフに最後にヒントづけが行われて以来ユーザが明示的な変更をヒントに行わなかった場合、
そのグリフを変更したときには自動ヒントづけを行います)。
ユーザは、
<span class="command">自動ヒント(H>)</span>
を明示的に呼び出すことによりこのフラグをオフにすることができます。

In the outline glyph view, behavior is a bit more complicated. This
command will toggle the current setting of the "Don't AutoHint" flag. If
the flag is currently on the menu entry will be checked.
アウトライングリフビューでは、
そのふるまいはもう少し複雑です。
このコマンドは現在の
<span class="command">自動ヒントを停止(D)</span>
フラグの現在の設定を反転します。
このフラグがメニューメニュー項目にある場合、
そこにチェックマークが表示されます。


<!--
#### AutoInstr
-->
#### ヒント命令の自動生成(I) (AutoInstr)

<!--
The Auto Instr command is only available in quadratic fonts and is used
to generate truetype instructions. It is designed to produce
instructions based on PostScript information, so please insure that all
glyphs are correctly hinted and that the [PostScript private
dictionary](../fontinfo/#Private) has been filled in. (I know the
instructions aren't used by PostScript, but the information needed to
generate the instructions is clearly expressed in the PostScript data).
-->
<span class="command">ヒント命令の自動生成(I)</span>
コマンドは
2 次スプラインからなるフォントでのみ使用可能で、
TrueType 命令を生成するのに用いられます。
PostScript 情報に基づいて命令を生成するように設計されているため、
すべてのグリフに正しくヒントが付けられ、
[PostScript プライベート辞書](../fontinfo/#private--font-wide-postscript-hinting)
が入力されていることを確認してください
(命令は PostScript では使用されませんが、
命令を生成するのに必要な情報は PostScript データで明確に表現されています)。

<!--
If you are using AutoHint to generate hints, please insure that the
diagonal hint preference item is turned on
(`File->Preferences->PS Hints->Detect Diagonal Stems)`
-->
<span class="command">自動ヒント(H)</span>
を使用してヒントを生成する場合は、
斜めのヒント設定項目がオンになっていることを確認してください
(<span class="command">ファイル-\>設定-\>PSヒント-\>斜めのステムを検出</span>)


<!--
#### Edit Instructions...
-->
#### ヒント命令の編集(E)... (Edit Instructions...)

<!--
Only available in the outline and font views, and only in quadratic
fonts. [This dialog](../ttfinstrs/) shows any truetype instructions
associated with this glyph, and allows you to edit them.
 Note there are some glyphs for which you cannot write instructions if
they contain references that cannot be represented in TrueType. If a
glyph contains a reference that is scaled by a factor of 2 or more, or
if a glyph contains both a reference and a contour then you may not
generate instructions for it. You can either:
-->
これはアウトラインビューとフォントビューに限られ、
2 次スプラインからなるフォントでのみ使用可能です。
[このダイアログ](../ttfinstrs/)
は、
このグリフに付随する任意の TrueType 命令を表示し、
それらを編集することができます。<br>
 グリフに TrueType で表現不可能な参照が含まれでいるため、
そのグリフに命令を付け加えることができない場合があることに注意してください。
2 倍以上の比率で拡大された参照が含まれているか、
1 個のグリフに参照と輪郭の両方が含まれている場合、
そのグリフのための命令を出力することはできません。
その場合、以下のいずれかが可能です:

<!--
-   Unlink all references
-   (in the case of a glyph with references and contours) Place all the
    contours into a new glyph and make a reference to that glyph. (So
    the composite glyph will now contain only references).
-->
-   すべての参照を解除する
-   (参照と輪郭の両方を含むグリフの場合)
    すべての輪郭を新しいグリフに位置し、
    そのグリフへの参照を作成する
    (それにより、複合グリフだったのが参照だけを含むようになります)。


<!--
#### Debug...
-->
#### デバッグ(D)... (Debug...)

<!--
Only available in the outline view, and only if you have linked with a
version of freetype with the bytecode interpreter and only in quadratic
fonts. This allows you to [debug truetype
programs](../charview/#Debugging).
-->
これはアウトラインビューに限られ、
バイトコードインタプリタを有効にしてコンパイルされた FreeType にリンクされているときに、
2 次スプラインからなるフォントでのみ使用可能です。
これを使うと、
[TrueType のプログラムをデバッグする](../charview/#デバッグビュー)
ことができます。


<!--
#### Edit fpgm...
-->
#### 'fpgm' テーブルを編集... (Edit fpgm...)

<!--
Only available in the font view, and only in quadratic fonts. [This
dialog](../ttfinstrs/) shows any truetype instructions in the 'fpgm'
table, and allows you to edit them.
-->
これはフォントビューに限られ、
2 次スプラインからなるフォントに限られます。
[このダイアログ](../ttfinstrs/)
では 'fpgm' テーブルに含まれる任意の TrueType 命令を表示し、
それを編集することができます。


<!--
#### Edit prep...
-->
#### 'prep' テーブルを編集... (Edit prep...)

<!--
Only available in the font view, and only in quadratic fonts. [This
dialog](../ttfinstrs/) shows any truetype instructions in the 'prep'
table, and allows you to edit them.
-->
これはフォントビューに限られ、
2 次スプラインからなるフォントに限られます。
[このダイアログ]
では 'prep' テーブルに含まれる任意の TrueType 命令を表示し、
それを編集することができます。


<!--
#### Edit cvt...
-->
#### 'cvt' テーブルを編集... (Edit cvt...)

<!--
Only available in the font view, and only in quadratic fonts. [This
dialog](../ttfinstrs/#cvt) shows the initial values in the 'cvt '
table, and allows you to edit them. You can also add a brief comment to
describe what each entry is used for.
-->
これはフォントビューに限られ、
2 次スプラインからなるフォントに限られます。
[このダイアログ](../ttfinstrs/#cvt)
では 'cvt' テーブルの初期値を表示し、
それを編集することができます。
各エントリの用途を説明する短いコメントを追加することもできます。


<!--
#### Suggest Deltas...
-->
#### デルタを提案... (Suggest Deltas...)

<!--
Brings up a [dialog](../SuggestDeltas/) which will help you search for
places where truetype delta instructions might be useful.
-->
TrueType デルタ命令が役立つ可能性のある場所を検索するのに役立つ
[ダイアログ](../SuggestDeltas/)
が表示されます。


<!--
#### Remove Instr Tables
-->
#### 命令テーブルを削除 (Remove Instr Tables)

<!--
If the font contains a 'fpgm', 'prep', 'cvt ' or 'maxp' table, then this
command will remove them. This should be done in conjunction with
[Hints-\>Clear Instructions](../hintsmenu/#Clear.Instructions), 
otherwise any remaining instructed glyphs will fail to work.
-->
フォントに 'fpgm', 'prep', 'cvt', 'maxp' のテーブルが含まれている場合、
このコマンドはそれらを削除します。
これは、
[<span class="command">ヒント(H)->ヒント命令を削除</span>](../hintsmenu/#ヒント命令を削除-clear-instructions)
と組み合わせて実行する必要があります。
そうしないと、ヒント命令の対象となっている残りのグリフが機能しなくなります。


<!--
#### Clear Hints
-->
#### ヒントを削除(C) (Clear Hints)

<!--
Clears all hints in all selected glyphs.
-->
選択中のグリフの全てのヒントを消去します。


<!--
#### Clear Instructions
-->
#### ヒント命令を削除 (Clear Instructions)

<!--
Clears any truetype instructions associated with the selected glyphs.
-->
選択中のグリフに伴う任意の TrueType 命令を消去します。


<!--
#### Clear HStem
-->
#### 水平ステムヒントを削除(C) (Clear HStem)

<!--
Removes all Horizontal Stem hints from the current glyph.
-->
現在のグリフからすべての水平ステムヒントを削除します。


<!--
#### Clear VStem
-->
#### 垂直ステムヒントを削除(V) (Clear VStem)

<!--
Removes all Vertical Stem hints.
-->
すべての垂直ステムヒントを削除します。

<!--
#### Clear DStem
-->
#### 斜めステムヒントを削除 (Clear DStem)

<!--
Removes all Diagonal Stem hints.
-->
すべての斜めステムヒントを削除します。


<!--
#### Add HHint
-->
#### 水平ヒントを追加(A) (Add HHint)

<!--
If there are two points selected (exactly two) and if they have
different y positions, then this will create a Horizontal Stem Hint
starting at the lower one of the two going up to the upper one.
-->
2 個 (ちょうど 2 個に限る) の点が選択されていて、
それらの y 座標が異なる場合、
下の点から始まり上の点で終わる
「水平ステムヒント」
を作成します。


<!--
#### Add VHint
-->
#### 垂直ヒントを追加(V) (Add VHint)

<!--
If there are two points selected (exactly two) and if they have
different x positions, then this will create a Vertical Stem Hint
starting at the leftmost one of the two going right to the rightmost
one.
-->
2 個 (ちょうど 2 個に限る) の点が選択されていて、
それらの x 座標が異なる場合、
左の点から始まり右の点で終わる
「垂直ステムヒント」
を作成します。


<!--
#### Add DHint
-->
#### 斜めヒントを追加 (Add DHint)

<!--
If there are exactly 4 points selected and they can describe a diagonal
stem hint then this menu item will be active and will add it.
-->
ちょうど 4 個の点が選択されていて、
それらが斜めステムを表現可能な場合、
このメニュー項目が有効になり、斜めヒントを追加します。


<!--
#### Create HHint
-->
#### 水平ヒントを作成(T) (Create HHint)

<!--
Brings up a dialog allowing you to specify exactly where and how wide
you want a Horizontal Stem Hint.
-->
水平ステムヒントがどこから始まり、どれだけの幅をもつかを正確に指定できるダイアログを起動します。


<!--
#### Create VHint
-->
#### 垂直ヒントを作成(E) (Create VHint)

<!--
Brings up a dialog allowing you to specify exactly where and how wide
you want a Vertical Stem Hint.
-->
垂直ステムヒントがどこから始まり、どれだけの幅をもつかを正確に指定できるダイアログを起動します。


<!--
#### Review Hints
-->
#### ヒントを確認(R) (Review Hints)

![](/assets/img/filemenu-reviewhints.png)

<!--
Brings up a dialog allowing you to examine (and modify) all
horizontal/vertical stem hints (not diagonal). The currently active hint
is picked out in either dark blue or dark green.
-->
水平/垂直ステムヒントを吟味し (そして変更する) ことができるダイアログを起動します。
現在アクティブなヒントが抽出され、
藍色または暗緑色で表示されます。


<!--
### The Histograms SubMenu
-->
### 柱状グラフサブメニュー (The Histograms SubMenu)


<!--
#### HStem
-->
#### 水平ステム(H) (HStem)

<!--
Brings up a [dialog](../histogram/) displaying a histogram of the
horizontal stem widths of all selected glyphs.
-->
選択中のすべてのグリフに含まれる水平ステムの幅の柱状グラフを表示する
[ダイアログ](../histogram/)
を起動します。


<!--
#### VStem
-->
#### 垂直ステム(V) (VStem)

<!--
Brings up a [dialog](../histogram/) displaying a histogram of the
vertical stem widths of all selected glyphs.
-->
選択中のすべてのグリフに含まれる垂直ステムの幅の柱状グラフを表示する
[ダイアログ](../histogram/)
を起動します。


<!--
#### BlueValues
-->
#### BlueValues

<!--
Brings up a [dialog](../histogram/) displaying a histogram of the
vertical maxima and minima of all selected glyphs.
-->
選択中のすべてのグリフに含まれる垂直方向の最大値と最小値の柱状グラフを表示する
[ダイアログ](../histogram/)
を起動します。
