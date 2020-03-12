---
published: true
layout: default.ja
title: マルチプルマスターメニュー
---
<!--
published: true
layout: default
title: Multiple Master menu
-->

<!--
The MM Menu provides a few commands for manipulating [Multiple Master or
Apple distortable fonts](../multiplemaster/#MM). If the current font is
a MM itself font the menu also includes a list of all font instances
that make up this one. This menu is available in the [font
view](#fontview) and the [outline glyph view](#outline-char).
-->
MM (マルチプルマスター) メニューには、
[マルチプルマスターフォントまたは Apple 変形可能フォント](../multiplemaster/#MM)
をいじるための 2, 3 のコマンドがあります。
もし現在のフォントが MM そのものならば、
メニューにはそれを構成するすべてのフォントインスタンスのリストが含まれています。
このメニューは
[フォントビュー](#フォントビュー-font-view)
および
[アウトライングリフビュー](#グリフビュー-glyph-view)
で使用可能です。


[table_of_contents]


<!--
### Font View
-->
### フォントビュー (Font View)

<!--
The menu as it appears in the font view.
-->
フォントビューで表示されるメニューの内訳


<!--
#### Create MM
-->
#### MMを作成(C) (Create MM)

<!--
Brings up the [multiple master dialog](../multiplemaster/) and allows
you to create your own multiple master font from scratch.
-->
[マルチプルマスターダイアログ](../multiplemaster/)
を起動し、
あなた自身のマルチプルマスターフォントをスクラッチから作成できるようにします。


<!--
#### MM Valid
-->
#### MMが正しいか検査(V) (MM Valid)

<!--
Checks that the current multiple master font can be saved. So each
master design must match in:
-->
現在のマルチプルマスターフォントを保存することが可能かどうか検査します。
そのためには、各マスターフォントは以下の点で一致しなければなりません:

<!--
-   Contours
    -   There must be the same number of contours and
    -   each contour must have the same number of points and
    -   each spline on the contour must be the same type (ie it can't
        correspond to a straight line in one font and a curve in
        another)
-   References
    -   There must be the same number of references and
    -   Each corresponding reference must refer to the same encoding
-   Hints
    -   Same number of hints
-   HintMasks (Counter masks are not supported here)
    -   HintMasks at corresponding points must specify a corresponding
        set of hints
-   Kerning
    -   If a glyph kerns with another glyph in one font, then a
        corresponding kerning pair must exist in all designs
-->
-   輪郭
    -   ちょうど同じ個数の輪郭が存在し、
    -   各輪郭は同じ個数の点を含み、
    -   輪郭上の各スプラインは同じ型でなければならない
        (例えば、あるフォントにおける直線に、別のフォントの曲線が対応づけられていてはいけないということです)
-   参照
    -   ちょうど同じ個数の参照が存在しなければならず、
    -   対応する各参照は同じ文字コードを参照していなければならない
-   ヒント
    -   同じ個数のヒント
-   ヒントマスク (この場合、カウンタマスクはサポートされていません)
    -   対応する点に位置するヒントマスクは対応するヒントセットを指定していなければならない
-   カーニング
    -   ある文字と別の文字が 1 個のフォントでカーニングの対象になるとしたら、
        対応するカーニングペアがすべてのデザインに存在しなければならない


<!--
#### MM Info
-->
#### マルチプルマスター情報(I) (MM Info)

<!--
Brings up the [multiple master dialog](../multiplemaster/) and allows
you to modify the current multiple master font.
-->
[マルチプルマスターダイアログ](../multiplemaster/)
を起動し、現在のマルチプルマスターフォントを変更できるようにします。


<!--
#### Blend to New Font...
-->
#### 補間結果を新フォントに(B)... (Blend to New Font...)

<!--
Allows you to create a blended version of the current multiple master
font set as a stand alone font.
-->
現在のマルチプルマスターフォントセットを混ぜ合わせたバージョンを、
独立したフォントとして新しく作成します。


<!--
#### MM Change Default Weights
-->
#### MMの標準ウェイトを変更(W) (MM Change Default Weights)

<!--
Allows you to change the default weights assigned to each master design
used in blending the default instance of the font
-->
混ぜ合わせによってフォントのデフォルトインスタンスを作成する際に、
各マスターデザインに割り当てられている標準の重みづけを変更することができます。


<!--
#### (sub font name)
-->
#### (サブフォント名) (sub font name)

<!--
Clicking on a different sub font name in the menu will cause that
sub-font to be displayed instead of the current one. The subfonts are
the master designs and the default blended font.
-->
メニュー上の異なるサブフォント名をクリックすると、そのサブフォントが現在のサブフォントの代りに表示されます。
サブフォントはサブフォントはマスターデザインであり、混ぜ合わせ結果のフォントのデフォルトです。


<!--
### Glyph View
-->
### グリフビュー (Glyph View)

<!--
The menu as it appears in the <a name="outline-char">outline glyph</a> view.
-->
アウトライングリフビューで表示されるメニューの内訳


<!--
#### MM Reblend
-->
#### MMの補間を再作成(R) (MM Reblend)

<!--
Reblends the default version of the current glyph
-->
現在のグリフのデフォルトの版をもう一度混ぜ合わせます。


<!--
#### View
-->
#### 表示(V) (View)

<!--
A submenu which allows you to choose which of the designs of this glyph
you want displayed in the background of the view
-->
このグリフのどのデザインをビューの背景に表示するかを選択可能なサブメニューです。


<!--
#### (sub font name)
-->
#### (サブフォント名) (sub font name)

<!--
Clicking on a different sub font name in the menu will cause the glyph
from that sub-font to be displayed instead of the current one. The
subfonts are the master designs and the default blended font.
-->
メニュー上の異なるサブフォント名をクリックすると、そのサブフォントが現在のサブフォントの代りに表示されます。
サブフォントはサブフォントはマスターデザインであり、混ぜ合わせた結果のフォントのデフォルトです。
