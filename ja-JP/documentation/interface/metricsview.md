---
published: true
layout: default.ja
title: メトリックビュー
---


[table_of_contents]


![](/assets/img/dialogs1-MetricsView.png)

<!--
The metrics view allows you to examine how glyphs look together and to
alter the spacing between them. You may apply various OpenType features
to those glyphs and see how they are altered.
-->
メトリックビューでは、複数のグリフがどのように見えるかを確認したり、
それらの間の間隔を変更したりすることができます。
さまざまな OpenType の機能をこれらのグリフに適用し、
見た目の変化を確認することができます。

<!--
If the metrics view is created from the font view then any selected
glyphs (well, the first 15 or so) will be displayed in the view in the
order they were selected. If it is created from an outline or bitmap
glyph view then only that glyph is displayed. If it is created from a
bitmap glyph view (or from the font view when that view is displaying a
bitmap font) then the metrics view will display bitmaps, but will not
allow you to edit the bitmaps metrics (you must do your metrics editing
in a view displaying outlines).
-->
メトリックビューがフォントビューから作成された場合、
選択していたグリフ（最初の15個など）は、
選択された順序でビューに表示されます。
メトリックビューがアウトラインまたはビットマップグリフビューから作成された場合、
そのグリフのみが表示されます。
メトリックビューがビットマップグリフビューから作成された場合
（またはそのビューがビットマップフォントを表示しているときにフォントビューから作成された場合）、
メトリックビューにはビットマップが表示されますが、
ビットマップのメトリックは編集できません（アウトラインを表示するビューでメトリックの編集を行う必要があります）。

<!--
Underneath the menu bar is a series of fields. The first shows the
current script and language combination being used to determine what
lookups to apply within the selected features, the next is a text field
which allows you to enter additional unicode characters to be displayed,
and finally there is a pulldown list of lookup subtables, this will be
used if you create a kerning pair (the kerning pair will become part of
that subtable). Underneath that is a list showing all features defined
in the font. You may select which ones you want to be active in this
display. (Note the features are listed in alphabetic order -- this is
not the order in which the lookups will be executed (or not usually the
order)).
-->
メニューバーの下には、一連のフィールドがあります。
最初は、選択した機能の中でどのルックアップを適用するかを決める文と言語の現在の組み合わせを示し、
次は、表示のための追加のユニコード文字を入力するテキストフィールドであり、
最後に、ルックアップサブテーブルのプルダウンリストがあります。
このテーブルはカーニングペアを作成する場合に使用されます（カーニングペアはそのサブテーブルの一部になります）。
その下には、フォントで定義されているすべての機能を示すリストがあります。
この画面でアクティブにするものを選択できます。
（注： 機能はアルファベット順に並んでいます。
ルックアップが実行される順序ではありません（大抵はその順序ではありません））。

<!--
If you wish to enter characters you cannot type:
-->
文字を入力するときに、タイプして入力することはできません:

<!--
1.  Select the character (or glyph) in the fontview and then drag and
    drop it into the metrics view at the appropriate place
2.  Use the View menu to change or insert a character or glyph
    (View->Insert Glyph After)
3.  Select the characters individually and in order in the font view
    before you open the metrics view, when you do open it the characters
    will appear in the order you selected them
4.  FontForge has its own funky [input method](#Entering+non-ASCII+characters)
-->
1.  フォントビューで文字（またはグリフ）を選択し、
    適切な場所のメトリックスビューにドラッグ&ドロップします
2.  ビューメニューを使用して、文字またはグリフを変更または挿入します
    （表示->グリフを挿入）
3.  メトリックビューを開く前に、フォントビューで文字を個別に順番に選択します。
    メトリックビューを開いたときに選択した順序で表示されます
4.  FontForgeには独自の風変わりな
    [入力メソッド](#非-ascii-文字の入力)
    があります

<!--
The mid portion of the view is taken up with the displayed glyphs. For
outline glyphs these are sized so that the em-height of the font just
fits in this region. There are grey lines between the glyphs marking the
origin of the glyph on the right and the width of the glyph on the left.
The baseline is also drawn in grey.
-->
ビューの中央部分は、表示されているグリフで占められます。
アウトライングリフの場合、フォントの em-height がこの領域にちょうど収まるようにこれらのサイズが設定されます。
グリフの間に灰色の線があり、右側のグリフの原点と左側のグリフの幅を示しています。
ベースラインも灰色で描画されます。

<!--
A metrics view may be in one of three modes (Metrics->Window Type)
-->
メトリックビューは、3つのモードのいずれかになります（メトリック->ウィンドウタイプ）。

<!--
-   Kerning only -- you may adjust the kerning between any pairs of
    glyphs shown, but you may not set any advance widths
-   Advance Width only -- you may adjust the advance width of any glyph
    shown, but you may not set kerning
-   Both -- see below
-->
-   カーニングのみ -- 任意のペア間のカーニングを調整できます。
    グリフは表示されていますが、送り幅は設定できません
-   送り幅のみ -- 表示されている任意のグリフの送り幅を調整できます。
    カーニングは設定できません
-   両方 -- 以下を参照してください

<!--
One of the glyphs is active. That glyph has a green line on its left (at
its origin) and a blue line on its right (its width). You may change the
width by dragging this line. You may change the left side bearing
(lbearing) of the glyph by clicking on the glyph and dragging it left or
right. You may change the kerning between this glyph and the one to its
left by dragging the green line around. (If you wish to create a [Device
Table](#Device+Table) for small pixel sizes you must use the [Kern Pair
Closeup dialog](#Kern+Pair+Closeup))
-->
グリフうちの1つがアクティブになります。
そのグリフには、左側（原点）に緑色の線があり、右側（幅）に青色の線があります。
この線をドラッグして幅を変更できます。
グリフをクリックして左または右にドラッグすると、グリフの左側のベアリング (lbearing) を変更できます。
緑色の線をドラッグして、このグリフとその左のグリフの間のカーニングを変更できます。
（小さなピクセルサイズの [デバイステーブル](#デバイステーブル) を作成する場合は、
[カーニングペアクローズアップダイアログ](#kern-pair-closeup) を使用する必要があります）


<!--
Kerning
-->
カーニング

![](/assets/img/dialogs1-To-unkerned.png) ![](/assets/img/dialogs1-To-kerned.png)

<!--
The active glyph may be changed by clicking on any of the glyphs.
-->
グリフをクリックしてアクティブなグリフを変更できます。

<!--
The up and down arrow keys will increase and decrease the field's value by
a single unit. Holding Shift-up or -down will accelerate this by 10 and
Ctrl-Shift-up or -down by 5. Holding Alt-up, -down, -left or -right will move
the cursor to the field above, below, left or right.
-->
矢印キーの up、down は、フィールドの値を1ずつ増加、減少させます。
Shift-up または -down で増減は10ずつになり、
Ctrl-Shift-up または -down では5ずつにになります。
Alt-up、-down、-left、-right を押すと、カーソルが上、下、左、右のフィールドに移動します。

<!--
Underneath the display area are a set of text fields. You may type in
new numbers for any of these fields to change the corresponding metrics
of the glyph.
-->
表示領域の下には、テキストフィールドのセットがあります。
これらのフィールドのいずれかに新しい数値を入力して、グリフの対応するメトリックを変更できます。

<!--
Sometimes it is handy to be able to load a list of words into the
metrics view (so that you don't have to type them one by one). The text
entry field has a pull down list, and at the bottom of this list is an
entry to load a word list from a file. Once you select this, and your
file, the pulldown list will ill up with choices. You may use the
up/down arrow keys to move through the word list.
-->
単語のリストをメトリックビューに読み込むことができると便利な場合があります（1文字ずつ入力する必要がなくなります）。
テキスト入力フィールドにはプルダウンリストがあり、このリストの下部には、ファイルから単語リストを読み込むためのエントリがあります。
一度ファイルを選択すると、プルダウンリストに選択肢が表示されるようになります。
上下矢印キーを使用して、単語リスト内を移動できます。

<!--
If the first glyph to be displayed is in Hebrew or Arabic (or any other
right to left language) then the entire display area will be shown right
to left
-->
表示される最初のグリフがヘブライ語やアラビア語（または他の右から左の言語）である場合、
表示領域全体が右から左に表示されます

<!--
**Note** there is a very complicated algorithm given in the Unicode spec
for displaying mixed right to left and left to right passages. This is
not followed here. The direction determination is done by the first
glyph alone.
-->
**注** 右から左、左から右への記述方向を混在して表示するために Unicode 仕様で規定されている非常に複雑なアルゴリズムがあります。
ここではそれに従いません。
記述方向の決定は、最初のグリフのみによって行われます。

![](/assets/img/dialogs1-VerticalMetrics.png)

![](/assets/img/dialogs1-HebrewMetrics.png)

<!--
You can make the window display vertical metrics and kerning by
View->Vertical. (This is only available if your font has vertical
metrics enabled, Element->Font Info->General->Has Vertical Metrics).
In this mode you can change vertical width, vertical kerning, etc.
-->
View->Vertical により、垂直メトリックとカーニングする表示ウィンドウを生成できます。
（これは、フォントで垂直メトリックが有効になっている場合にのみ使用できます。
Element->Font Info->General->Has Vertical Metrics.
このモードでは、垂直幅、垂直カーニングなどを変更できます。

<!--
If you double click on one of the displayed glyphs then FontForge will
bring up a outline glyph view to allow you to edit that glyph.
-->
表示されているグリフのいずれかをダブルクリックすると、
FontForge はアウトライングリフビューを表示して、そのグリフを編集できるようにします。

![](/assets/img/dialogs1-MetricsView-features.png)

<!--
In the example at left, the input text is an "f" followed by an "i",
and as the 'liga' feature is turned on, this becomes the "fi" ligature.
Then an "a" followed by a "b", but as the 'smcp' (small caps) feature is
on these become small-caps letters rather than lower case. Finally "1",
"/" and "2" were entered, and as the 'frac' (diagonal fractions) feature
is turned on these three input glyphs become the onehalf glyph on
output.
-->
左の例では、入力テキストは "f" の後に "i" が続いており、
'liga' 機能がオンになると、これは "fi" の合字になります。
次に、"a" の後に "b" が続きますが、
'smcp' （スモールキャップ） 機能がオンになっているため、
これらは小文字ではなくスモールキャピタル文字になります。
最後に "1", "/", "2" が入力され、
'frac' （対角分数）機能がオンになると、
これら3つの入力グリフは出力時には「1/2」のグリフになります。

<!--
Note: This window is not a full blown layout engine. All the glyphs will
be treated as if they were in the same script, and all features will be
applied to all glyphs. Baseline alignment will not be done.
-->
注： このウィンドウは完全なレイアウトエンジンではありません。
すべてのグリフは同じ文の中にあるかのように扱われ、すべての機能がすべてのグリフに適用されます。
ベースラインの位置合わせは行われません。

<!--
### Entering non-ASCII characters
-->
### 非 ASCII 文字の入力

<!--
Most of us are stuck with keyboards that only have ASCII characters on
them. Or at best some sub-set of ISO 8859-1 characters. How can the full
range of unicode characters be entered?
-->
私たちのほとんどは、ASCII 文字しか持たないキーボードにこだわっています。
あったとしても、せいぜい ISO 8859-1 文字のサブセットくらいです。
Unicode 文字の全範囲を入力するにはどうすればよいでしょうか?

<!--
X supplies a sophisticated mechanism for entering characters via
stand-alone [input method servers](../../reference/xim/). FontForge supports
this to some extent now.
-->
X Window System は、スタンドアロンの
[インプットメソッドサーバ](../../reference/xim/)
によって文字を入力する洗練されたメカニズムを提供しています。
FontForge は現在、これをある程度サポートしています。

<!--
Aside from that, many versions of X supply a "Compose Character" key, or
something equivalent. The X software will map a sequence of keystrokes
to one character in whatever the native encoding may be.
-->
それとは別に、X Window System の多くのバージョンは、
"Compose Character" キーか、またはそれと同等のものを提供しています。
X Window System のソフトウェアは、ネイティブなエンコーディングが何であったとしても、
キーストロークのシーケンスを1つの文字にマッピングします。

<!--
My keyboard doesn't have such a key, and my X doesn't do this. But I
have implemented something along those lines for those of us with less
expensive keyboards. If you are in a mode where text entry is possible
then press the F12 key and follow it by a series of keystrokes. Accented
characters may be built using the following:
-->
使用しているキーボードにそうしたキーがない場合、
使用している X Window System でこれらが提供されていない場合に備えて、
そうした方針に沿ったうえで、安価なキーボードが利用できるような仕組みを実装しました。
テキスト入力が可能なモードの場合に、F12キーを押してから一連のキーストロークを実行してください。
アクセント付き文字は以下のように作成することができます:

<!--
    `   grave accent                
    0   ring           
    "   double grave (or tonos)
    '   acute accent                
    /   slash           
    .   dot above
    :   diaeresis (umlaut)          
    7   breve           
    ,   dot below
    ^   circumflex                  
    6   caron           
    5   cedilla
    ~   tilde                       
    _   macron          
    4   ogonec
-->
    `   グレイブ・アクセント (grave accent)
    0   リング符号 (ring)
    "   ダブルグレイブ（またはトノス） (double grave (or tonos))
    '   アキュート・アクセント (acute accent)
    /   ストローク符号 (slash)
    .   上付きドット符号 (dot above)
    :   ダイエレシス（ウムラウト） (diaeresis (umlaut))
    7   ブレーヴェ (breve)
    ,   下付きドット符号 (dot below)
    ^   サーカムフレックス (circumflex)
    6   ハーチェク (caron)
    5   セディーユ (cedilla)
    ~   チルダ (tilde)
    _   マクロン (macron)
    4   オゴネク (ogonec)

<!--
So Â may be built by [F12] \^ A, and A with diaeresis and macron may be
built with [F12] : \_ A.
-->
したがって、 Â は [F12] ^ A で作成でき、
ダイエレシスとマクロンを含む A は [F12] ： \_ A で作成できます。

<!--
Greek letters may also be created. If you start with [F12] @ and follow
with:
-->
ギリシャ文字も作成できます。
開始は [F12] @ で続いて以下を入力します：

    A   Alpha                     
    B   Beta            
    C   Chi
    D   Delta                     
    E   Epsilon         
    F   Phi
    G   Gamma                     
    H   Eta             
    I   Iota
    J   (technical) Theta         
    K   Kappa           
    L   Lamda
    M   Mu                        
    N   Nu              
    O   Omicron
    P   Pi                        
    Q   Theta           
    R   Rho
    S   Sigma                     
    T   Tau             
    U   Upsilon
    V   final sigma               
    W   Omega           
    X   Xi
    Y   Psi                       
    Z   Zeta                

<!--
This is the mapping used by the Symbol font. (Lower case letters are
created similarly so [F12] @ a yields a lower case alpha). Accented
greek letters may also be built up, [F12] @ " A yields Alpha tonos.
-->
これは Symbol フォントで使用されるマッピングです。
（小文字も同様に作成されます。 [F12] @ a は小文字のアルファを生成します）
アクセント付きのギリシャ文字も作成することができ、
[F12] @ \" A は、トノス付きのアルファを生成します。

<!--
Finally the following special characters may be built:
-->
最後になりますが、次の特殊文字を作成できます:

    [F12] <space>   <no break space>          
    [F12] *         °                              
    [F12] @ *       <bullet>
    [F12] @ <space> <em space>
    [F12] #         £
    [F12] @ #       ¥
    [F12] $         <euro>
    [F12] @ $       ¢                              
    [F12] !         ¡
    [F12] +         ±                         
    [F12] -         <soft-hyphen>
    [F12] @ -       <en dash>
    [F12] @ .       ·                           
    [F12] 7 2       ½                              
    [F12] ;         . . .
    [F12] <         <less or equal>
    [F12] >         <greater or equal>           
    [F12] @ >       <triangle bullet>
    [F12] =         <quote dash>              
    [F12] ?         ¿                              
    [F12] A         Å
    [F12] C         Ç                           
    [F12] H         <right index>                
    [F12] O         <OE lig>
    [F12] P         §                           
    [F12] [         <single right quote>         
    [F12] ]         <single right quote>
    [F12] \         «                           
    [F12] @         <single guillemot>           
    [F12] a         å
    [F12] c         ç                           
    [F12] f         <female sign>                
    [F12] g         ©
    [F12] h         <left index>              
    [F12] m         <male sign>                  
    [F12] o         <oe lig>
    [F12] p         ¶                           
    [F12] r         ®                              
    [F12] s         ß
    [F12] t         TM                          
    [F12] z         <long s>                     
    [F12] {         <left dbl quote>
    [F12] }         <right dbl quote>         
    [F12] |         »                              
    [F12] @ |       <right single guillemot>

<!--
This still misses most unicode characters. But pressing [F12] twice will
bring up a dialog which will allow you to select any character in
unicode.
-->
ここには、まだほとんどの unicode 文字を見つけることができません。
ですが、 [F12] を2回押すとダイアログが表示され、
unicode の任意の文字を選択することができます。

<!--
If you type [F12] by mistake then an Escape will get you out of accent
mode.
-->
誤って [F12] をタイプすると、エスケープによりアクセントモードが終了します。


<!--
### Kerning By Class
-->
### クラスを用いたカーニング

<!--
Often it is a good idea to create classes of glyphs which kern alike.
For example A, À, Á, Â, Â, Ã and Ä probably all kern alike (but note
that o and ô probably kern quite differently after a T), and rather than
create separate kerning pairs for each of the "A"s above, they could all
be placed in a class of glyphs which kern alike.
-->
多くの場合、同じようなカーニングをするグリフのクラスを作成することをお勧めします。
たとえば、
A, À, Á, Â, Â, Ã, Ä
はおそらくすべて同じようなカーニング
（ただし、 o と ô はおそらく T の後ではかなり異なったカーニングをすることに注意してください）
をします。
上記の各 "A" について別々のカーニングペアを作成するよりも、
そのすべてを同様なカーニングをするグリフのクラスとして配置したほうがよいです。

<!--
The [Element->Font Info->Lookups](../lookups/) provides an interface
to this.
-->
そのためのインターフェースが
[Element->Font Info->Lookups](../lookups/)
で提供されています。

![](/assets/img/dialogs1-kerningformat.png)

<!--
It brings up a dialog showing all the
GPOS lookups (of which kerning is one) and their subtables. Each set of
kerning classes lives in its own subtable. When you create a kerning
subtable you will be asked whether you want a set of individual kerning
pairs or a matrix based on kerning classes.
-->
すべての GPOS ルックアップ（カーニングはその1つです）とそのサブテーブルを示すダイアログが表示されます。
カーニングクラスの各セットは、それ自身のサブテーブルに存在します。 カーニングサブテーブルを作成すると、
個々のカーニングペアのセットが必要か、カーニングクラスに基づくマトリクスが必要かが尋ねられます。

<!--
If you choose the latter then you may have fontforge try to guess a good
set of classes for you (it will look at the glyphs selected and divide
them into classes). The `Intra Class Distance` gives you some control
over how picky fontforge will be about what goes into a class. (This can
be thought of as being in em-units and being, roughly, the average error
in how two different glyphs interact with other glyphs). A value of 1 is
very picky and almost all classes will have one member. A value of 20
(in a 1000em font) is fairly loose.
-->
後者を選択した場合、 FontForge は適切なクラスのセットを推測しようとします（選択されたグリフを見て、複数のクラスに分割します）。
`Intra Class Distance` を使用すると、
クラスに入るものについて、気難しい FontForge がどのようになるかをある程度制御できます。
（これは em 単位、おおまかにいうと、
2つの異なるグリフが他のグリフとどのように相互作用するかについての平均誤差として解釈されます）。
値が 1 のときは非常にえり好みが激しく、ほとんどすべてのクラスはメンバーが1つとなります。
値が 20 （1000 em フォントに対して）の場合はかなり緩いです。

<!--
The `Default Separation` and `Min Kern` fields are used in AutoKerning.
The goal of kerning to to make the optical separation between all glyphs
to be constant, and the `Default Separation   `field specifies that
desired value. The `Min Kern` value is simply to prevent the dialog from
filling with useless junk. If AutoKerning suggests that two glyphs
should be kerned by 1 em unit then this won't make any difference to the
human eye and there is no point in including it. So if the kerning value
(in absolute value) suggested by AutoKern is less than `Min Kern` then
fontforge will ignore that value. Selecting `[]   Touching` makes
AutoKerning work in a slightly different way, instead of trying to make
the optical distance be the desired value this attempts to make the
minimum separation be the desired value (This is rarely useful, but
occasionally people want to set text where the letters actually touch
one another). The `[] Only kern glyphs closer `flag means that FontForge
will only generate negative kerning offsets, that is, offsets which will
move glyphs closer together.
-->
AutoKerning では、 `Default Separation` と `Min Kern` フィールドが使用されます。
すべてのグリフ間の視覚的な間隔を一定にするというカーニングの目標に対して、
`Default Separation` フィールドはその望ましい値を指定します。
`Min Kern` の値は、単にダイアログが無駄なゴミでいっぱいになるのを防ぐためのものです。
AutoKerning が2つのグリフを 1 em 単位でカーニングすることを提案している場合、
人間の目には違いがわからないので、それを含める意味はありません。
そのため、 AutoKern によって提案されたカーニングの値（絶対値）が `Min Kern` より小さい場合、
FontForge はその値を無視します。
`[] Touching` を選択すると、
AutoKerning の動作は少し異なり、
視覚的距離を目標値にしようとするのではなく、
最小間隔を目標値にしようとします
（これはめったに役立ちませんが、たまに、文字どうしが実際に接触するようなテキストが望まれることがあります）。
`[] Only kern glyphs closer`　のフラグは、
FontForge が負のカーニングオフセットのみを、
つまりグリフを互いに近づけるようなオフセットのみを生成することを意味します。

![](/assets/img/dialogs1-kerningclass.png)

<!--
Each kerning class belongs to a [lookup
subtable](../lookups/) and the subtable name is displayed at the top of
the dialog.
-->
各カーニングクラスは
[ルックアップサブテーブル](../lookups/)
に属し、サブテーブル名がダイアログの上部に表示されます。

<!--
But the more interesting stuff follows this. A kerning by class actually
consists of two sets of classes -- one set for the first glyph of the
pair and one for the second glyph of the pair. A glyph class consists of
a space separated list of glyph names (For most glyphs you may also
enter the unicode character itself, and fontforge will convert that to a
glyph name).
-->
しかし、より興味深いものを次に示します。
クラスによるカーニングは、実際には2セットのクラスで構成されます。
1セットは最初のグリフを含むセット、もう1セットはペアとなるの2番目のグリフを含むセットです。
グリフクラスは、空白で区切られたグリフ名のリストで構成されます
（大抵のグリフでは、 unicode 文字自体を入力することができ、
FontForge はそれをグリフ名に変換します）。

<!--
To edit a class, simply type in it (at the very bottom of the class list
is an entry called \<New\>, clicking here will create a new class).
Pressing the little rectangle at the right of the class will allow you
to define your class as a selection in a font view widget. You may
delete a class by selecting it (clicking in it) and pressing the
[Delete] button.
-->
クラスの編集は、クラスをタイプするだけです
（クラスリストの一番下に \<New\> というエントリがあり、
ここをクリックすると、新しいクラスが作成されます）。
クラスの右側にある小さな長方形を押すと、クラスをフォントビューウィジェットの選択項目として定義できます。
クラスを削除するには、クラスを選択（クリック）して [削除] ボタンを押します。

<!--
The kerning classes can be fairly complex. You can search for a glyph by
typing its name in the "Select Glyph" field. This will highlight the
class containing that glyph.
-->
カーニングクラスはかなり複雑になる場合があります。
"Select Glyph" フィールドに名前を入力して、グリフを検索できます。
これにより、そのグリフを含むクラスが強調表示されます。

<!--
Class 0 is usually magic. You almost never set it, it contains any
glyphs not mentioned elsewhere. In OpenType, class 0 of the first
character can be set and behaves normally.
-->
クラス0はたいてい呪文のようなものです。 
設定することはほとんどなく、他の場所で言及されていないグリフが含まれています。
OpenTypeでは、最初の文字のクラス0を設定でき、正常に動作します。

<!--
Underneath the classes is a display of kerning values. The possible
first glyph classes are listed vertically, the possible second glyph
classes are listed horizontally. When you select a class (in one of the
class lists above) the display of kerning values will scroll to display
that class. If you move the mouse into the display and let it rest, a
popup window will appear showing the glyphs that make up the classes
which intersect at that point. If you click on a kerning value in the
display, the dlg displays a visual representation of that amount of
kerning.
-->
クラスの下には、カーニング値の表示があります。
可能な最初のグリフクラスは垂直にリストされ、可能な2番目のグリフクラスは水平にリストされます。
クラスを選択すると（上記のクラスリストのいずれかで）、カーニング値の表示がスクロールしてそのクラスが表示されます。
マウスをディスプレイに移動して静止させると、ポップアップウィンドウが表示され、そのポイントで交差するクラスを構成するグリフが表示されます。
ディスプレイでカーニング値をクリックすると、
dlg がカーニングの視覚的な量を表示します。

<!--
The kerning dialog displays a representative glyph from each class and
allows you to adjust the kerning between them (and all other class
members of each class). You can select which glyphs to display in the
pulldown menus. You can enter a new kerning offset by typing in a value,
or you can click on the second glyph of the kern pair and drag it
around.
-->
カーニングダイアログには、各クラスの代表的なグリフが表示され、
グリフ間（そして各クラスの他のすべてのクラスメンバー間）のカーニングを調整できます。
プルダウンメニューで表示するグリフを選択できます。
値を入力して新しいカーニングオフセットを入力するか、カーニングペアの2番目のグリフをクリックしてドラッグします。


<!--
### Device Table
-->
### デバイステーブル

<!--
You can also create something called a "Device Table", a name which is
not very informative. When a font is rasterized at small pixel sizes
rounding errors become important, and this is particularly true of
kerning, there are three things that get rounded: The locations of the
outlines (to fit them to a pixel grid), the advance widths of the
glyphs, and the kerning value itself. The result is that something which
looks perfectly kerned at 150pixels may be either too close or too far
apart at 12pixels
-->
"デバイステーブル" と呼ばれるものを作成することもできますが、
この名前はあまり的を射たものではありません。
フォントが小さなピクセルサイズでラスタライズされると、丸め誤差が重要になってきます。
これは特にカーニングに当てはまります。
丸められるのは次の3つ、
アウトラインの位置（ピクセルグリッドに合わせるため）、
グリフの前進幅、
そして、カーニング値そのものです。
したがって、150 ピクセルでは完璧にカーニングされているように見えるものが、
12 ピクセルでは近すぎるか離れすぎている、という可能性があります。

![](/assets/img/dialogs1-kern-We-150.png)

<!--
Kerning at 150 pixels
-->
150 ピクセルでのカーニング

![](/assets/img/dialogs1-kern-We-12.png)

<!--
Kerning at 12 pixels (magnified by 2)
-->
12 ピクセルでのカーニング（2倍に拡大したもの）

<!--
You could adjust the kerning value slightly until it looked right at
12pixels, of course, but that might break it at 14 pixels. So OpenType
has the concept of a Device Table which allows you to add small
corrections at particular point sizes. Simply set the Display Size to a
small, but common, value (say 10-24) and examine the kerning. If the
results are ugly then type a value into the "Device Table Correction"
field, and this will change the spacing by that many pixels at the given
display size (and no other). In the case above a correction of 1 might
be appropriate for the 12px display.
-->
もちろん、12 ピクセルで正しく見えるようになるまでカーニング値を微調整できますが、
それによって 14 ピクセルでは崩れてしまうかもしれません。
そのため、 OpenType には、特定のポイントサイズで小さな修正を追加するようなデバイステーブルの概念があります。
表示サイズを小さいがよく使う値（10〜24など）に設定し、カーニングを調べます。
結果が良い場合は、 "Device Table Correction" フィールドに値を入力し、
それにより、指定された表示サイズについてはそのピクセル数だけ間隔が変更されます（他の表示サイズについては変更されません）。
上記の場合、12px の表示では 1 の修正が適切かもしれません。

<!--
Because small pixel sizes can be hard to examine, you can change the
magnification (rasterized at the same size, but each pixel made twice as
big).
-->
小さなピクセルサイズを調べるのは難しいため、
倍率を変更できます（同じサイズでラスタライズされますが、各ピクセルは2倍になります）。


### Kern Pair Closeup

<!--
[Device Tables](#Device+Table) may also be created in a
number of other cases. The example above was for a kerning class.
Kerning pairs may also have tables attached to them with the
Metrics->Kern Pair Closeup dialog, which looks similar to the Kerning
Class dialog above.
-->
[デバイステーブル](#デバイステーブル) は、他の多くの場面でも作成できます。
上記の例はカーニングクラス用です。
カーニングペアは、
上記の Kerning Class ダイアログに似た
Metrics->Kern Pair Closeup ダイアログを使用して、
テーブルをアタッチすることもできます。

![](/assets/img/dialogs1-kernpairclose.png)
