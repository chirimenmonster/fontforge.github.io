---
published: true
layout: default.ja
title: メトリックビュー
---
<!--
published: true
layout: default
title: The Metrics View
-->


[table_of_contents]


![](/assets/img/dialogs1-MetricsView.png)

<!--
The metrics view allows you to examine how glyphs look together and to
alter the spacing between them. You may apply various OpenType features
to those glyphs and see how they are altered.
-->
メトリックビューは、グリフを並べた時にどのように見えるかを表示し、
グリフ間のスペーシングを変更することができます。
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
メトリックビューがフォントビューのメニューから呼び出された場合、
選択されている任意のグリフ (おそらく、最初の 15 個程度) が選択された順番にビューに表示されます。
アウトライン・ビットマップのどちらかのグリフビューから呼び出された場合、
編集中のグリフだけが表示されます。
ビットマップグリフビューから
(またはビットマップフォントを表示中のフォントビューから)
呼び出されたときはメトリックビューはビットマップ表示となりますが、
そこではビットマップのメトリックを編集できません
(メトリック編集は、アウトラインを表示しているビューから行わなければなりません)。

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
    (<span class="command">表示->グリフを挿入</span>)
3.  メトリックビューを開く前に、フォントビューで文字を個別に順番に選択します。
    メトリックビューを開いたときに選択した順序で表示されます
4.  FontForge には独自の風変わりな
    [入力メソッド](#非-ascii-文字の入力)
    があります

<!--
The mid portion of the view is taken up with the displayed glyphs. For
outline glyphs these are sized so that the em-height of the font just
fits in this region. There are grey lines between the glyphs marking the
origin of the glyph on the right and the width of the glyph on the left.
The baseline is also drawn in grey.
-->
ビューの中央部分は表示中のグリフが占めています。
アウトライングリフの場合は、これらの大きさはフォントの em ハイトがこの領域にちょうど一致するように設定されます。
グリフとグリフの間には灰色の線があり、
右側にある次のグリフの原点と左側にある前のグリフの送り幅の位置を区切っています。
ベースラインも灰色の線で表示されています。

<!--
A metrics view may be in one of three modes (Metrics->Window Type)
-->
メトリックビューは、3つのモードのいずれかになります
(<span class="command">メトリック-\>ウィンドウタイプ</span>)。

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
グリフのうちどれか 1 つがアクティブになっています。
そのグリフは緑の線が左 (グリフの原点) 側にあり、
青い線が右 (グリフの横幅) 側にあります。
この線をドラッグすることにより幅を変更することができます。
グリフの左サイドベアリング (lbearing) は、
グリフをクリックして左から右に引っ張ることにより変更することができます。
緑の線をドラッグして動かせば、
このグリフと左にあるグリフの間のカーニングを設定することができます。
(小さなピクセルサイズに対して
[<span class="command">デバイステーブル</span>](#デバイステーブル)
を作成したい場合、
[<span class="command">カーニングペアの詳細</span>ダイアログ](#kern-pair-closeup)
を使用する必要があります)


<!--
Kerning
-->
### カーニング

![](/assets/img/dialogs1-To-unkerned.png) ![](/assets/img/dialogs1-To-kerned.png)

<!--
The active glyph may be changed by clicking on any of the glyphs.
-->
アクティブなグリフは、グリフのどこかをクリックすれば変更することができます。

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
表示エリアの下にあるのはテキストフィールドのグリフ一覧です。
表示されているどの文字でも、このフィールドに新しい値を入力すれば、
そのグリフの対応するメトリックの値を変更することができます。

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
最初のグリフがヘブライ文字またはアラビア文字
(その他任意の右から左に書く言語) として表示される場合、
表示エリア全体が右から左に表示されます。

<!--
**Note** there is a very complicated algorithm given in the Unicode spec
for displaying mixed right to left and left to right passages. This is
not followed here. The direction determination is done by the first
glyph alone.
-->
**注意** 右から左へ書く文字と左から右へ書く文字が混在したテキストを表示する、
非常に複雑なアルゴリズムが Unicode の規格で定められていますが、
このソフトウェアはそれに従っていません。
書字方向は最初のグリフだけを見て決めています。

![](/assets/img/dialogs1-VerticalMetrics.png)

![](/assets/img/dialogs1-HebrewMetrics.png)

<!--
You can make the window display vertical metrics and kerning by
View->Vertical. (This is only available if your font has vertical
metrics enabled, Element->Font Info->General->Has Vertical Metrics).
In this mode you can change vertical width, vertical kerning, etc.
-->
<span class="command">表示(V)->縦書き(V)</span>
を選ぶと、
ウィンドウに縦書きメトリックとカーニングを表示することができます
(フォントに縦書きメトリックが存在する場合に限ります。
<span class="command">エレメント(L)-\>フォント情報(F)...-\>一般情報-\>縦書きメトリックが存在</span>
をチェックする必要があります)。
このモードでは縦書きの字送り、カーニングなどを変更できます。

<!--
If you double click on one of the displayed glyphs then FontForge will
bring up a outline glyph view to allow you to edit that glyph.
-->
表示されたグリフのどちらかをダブルクリックすると、
FontForge はアウトライングリフビューを起動し、
そのグリフが編集できる状態になります。

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
### 非 ASCII 文字の入力法

<!--
Most of us are stuck with keyboards that only have ASCII characters on
them. Or at best some sub-set of ISO 8859-1 characters. How can the full
range of unicode characters be entered?
-->
ほとんどの人は、ASCII 文字しかキートップに書かれていないキーボードに制約されています。
良くても ISO 8859-1 文字のわずかなサブセットだけです。
Unicode の全領域の文字を入力するにはどうすればいいでしょうか?

<!--
X supplies a sophisticated mechanism for entering characters via
stand-alone [input method servers](../../reference/xim/). FontForge supports
this to some extent now.
-->
X Window System は、
CJK 文字をスタンドアローンの
[インプットメソッドサーバ](../../reference/xim/)
経由で入力する洗練されたメカニズムを提供しています。
FontForge は現在、これにある程度対応しています。

<!--
Aside from that, many versions of X supply a "Compose Character" key, or
something equivalent. The X software will map a sequence of keystrokes
to one character in whatever the native encoding may be.
-->
この方法の他に、
X Window System の多くのバージョンは "Compose Character" キーか、
何らかの等価な手段を提供しています。
X Window System のソフトウェアは、
ネイティブなエンコーディングが何であっても、
複数打鍵の列を 1 文字に変換するでしょう。

<!--
My keyboard doesn't have such a key, and my X doesn't do this. But I
have implemented something along those lines for those of us with less
expensive keyboards. If you are in a mode where text entry is possible
then press the F12 key and follow it by a series of keystrokes. Accented
characters may be built using the following:
-->
私のキーボードにはその種のキーはありませんし、
私の X Window System にもその機能はありません。
しかし安価なキーボードを使う我々のために、私はその考えに沿ってある方法を実装しました。
テキスト入力が可能なモードにいるときに F12 キーを押してから決まったやりかたで打鍵を行ってください。
以下の入力方法で、アクセントつき文字が表示できます。

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
    `   グレーブアクセント
    0   リング
    "   ダブルグレーブ (またはトノス)
    '   アキュートアクセント
    /   スラッシュ
    .   ドットアバブ
    :   ダイエレシス（ウムラウト）
    7   ブリーブ
    ,   ドットビロー
    ^   サーカムフレクス
    6   キャロン
    5   セディラ
    ~   チルダ
    _   マクロン
    4   オゴネク

<!--
So Â may be built by [F12] \^ A, and A with diaeresis and macron may be
built with [F12] : \_ A.
-->
これにより、 Â は [F12] ^ A で組み立てられ、
ダイエレシスとマクロンのついた A は [F12] : \_ A で組み立てることができます。

<!--
Greek letters may also be created. If you start with [F12] @ and follow
with:
-->
ギリシャ文字を作成することもできます。
[F12] @ に続けて以下のとおり入力すると表の文字が入力できます。

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
これは Symbol フォントで使用されている対応です。
(小文字も対応は同じなので、 [F12] @ a と入力すると小文字のアルファが入力できます)。
アクセントつきギリシャ文字を組み立てることもできます。
[F12] @ " A はトノスつき大文字アルファとなります。

<!--
Finally the following special characters may be built:
-->
それに加え、以下の特殊文字を組み立てることができます。

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
これでもまだ、Unicode のほとんどの文字は入力できません。
それでも、[F12] を 2 回押すと起動するダイアログで、
Unicode の任意の文字を選択して入力することができます。

<!--
If you type [F12] by mistake then an Escape will get you out of accent
mode.
-->
間違って [F12] キーを押してしまった場合、 Escape キーを押すとアクセントモードを抜けることができます。


<!--
### Kerning By Class
-->
### 文字クラスによるカーニング

<!--
Often it is a good idea to create classes of glyphs which kern alike.
For example A, À, Á, Â, Â, Ã and Ä probably all kern alike (but note
that o and ô probably kern quite differently after a T), and rather than
create separate kerning pairs for each of the "A"s above, they could all
be placed in a class of glyphs which kern alike.
-->
同じカーニングが適用されるグリフのクラスを定義することが良策であることがしばしばあります。
例えば、
A, À, Á, Â, Â, Ã, Ä
の各文字のグリフはおそらく同じカーニングが適用でき
(ただし、o と ô は、T の後ろに来たときのカーニングが全く異なるだろうことに注意してください)、
上に挙げた "A" の類にそれぞれ別々のカーニングペアを定義せずに、
同じようにカーニングを行う文字のクラスに対して定義を行うことができるでしょう。

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
後者を選択した場合、
FontForge は適切なクラスのセットを推測しようとします
(選択されたグリフを見て、複数のクラスに分割します)。
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
<span class="command">自動カーニング</span>
では、 `Default Separation` と `Min Kern` フィールドが使用されます。
すべてのグリフ間の視覚的な間隔を一定にするというカーニングの目標に対して、
`Default Separation` フィールドはその望ましい値を指定します。
`Min Kern` の値は、単にダイアログが無駄なゴミでいっぱいになるのを防ぐためのものです。
<span class="command">自動カーニング</span>
が2つのグリフを 1 em 単位でカーニングすることを提案している場合、
人間の目には違いがわからないので、それを含める意味はありません。
そのため、 自動カーニングによって提案されたカーニングの値（絶対値）が `Min Kern` より小さい場合、
FontForge はその値を無視します。
`[] Touching` を選択すると、
自動カーニングの動作は少し異なり、
視覚的距離を目標値にしようとするのではなく、
最小間隔を目標値にしようとします
(これはめったに役立ちませんが、たまに、文字どうしが実際に接触するようなテキストが望まれることがあります)。
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
その下にあるのはより興味深い情報です。
1 個のカーニングクラスは、実際には 2 個のクラスの組からなります
—— 1 つはペアの先頭のグリフの組、もう 1 つはペアの 2 番目のグリフの組です。
それぞれのクラスのリストの下には新クラスの追加・既存クラスの編集・削除を行うためのボタンがあります。
個々のグリフクラスはグリフ名を空白で区切ったリストです。
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
(クラスリストの一番下に \<New\> というエントリがあり、
ここをクリックすると、新しいクラスが作成されます)。
クラスの右側にある小さな長方形を押すと、クラスをフォントビューウィジェットの選択項目として定義できます。
クラスを削除するには、クラスを選択（クリック）して [削除] ボタンを押します。

<!--
The kerning classes can be fairly complex. You can search for a glyph by
typing its name in the "Select Glyph" field. This will highlight the
class containing that glyph.
-->
カーニングクラスは非常に複雑になることもあります。
"グリフを選択" フィールドでグリフ名をタイプすることにより、
グリフを検索することができます。
その結果、そのグリフが含まれているクラスがハイライト表示されます。

<!--
Class 0 is usually magic. You almost never set it, it contains any
glyphs not mentioned elsewhere. In OpenType, class 0 of the first
character can be set and behaves normally.
-->
通例、クラス 0 は特別な意味を持ちます。
これをユーザが設定することはほとんど無いでしょうが、
他のどのクラスにも含まれていない全ての文字の集まりのことです。
OpenType では、最初の文字のクラス 0 を設定することができ、
通常どおりにふるまいます。

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
各クラスの下にはカーニング値の一覧表があります。
最初のグリフクラスとして利用可能な物は縦に並び、
2 番目のグリフクラスは横に並んでいます。
クラスを (上のクラスリストで) どれか 1 個選択すると、
カーニング値の表示はそのクラスの欄までスクロールします。
マウスを表示欄の上に移動してしばらく待つと、
その欄の文字クラスの組合せを構成するグリフを表示するポップアップウィンドウが表示されます。
ディスプレイでカーニング値をクリックすると、
ダイアログがカーニングの視覚的な量を表示します。

<!--
The kerning dialog displays a representative glyph from each class and
allows you to adjust the kerning between them (and all other class
members of each class). You can select which glyphs to display in the
pulldown menus. You can enter a new kerning offset by typing in a value,
or you can click on the second glyph of the kern pair and drag it
around.
-->
カーニングダイアログは各クラスの代表グリフを表示し、
そこでそれらグリフ字 (各クラスに含まれる他のグリフ全ての組合せを含む) の間のカーニングを調整することができます 。
どのグリフを表示するかはプルダウンメニューで選ぶことができます。
新しいカーニングオフセットはキーボードで数値入力することもできますし、
2 番目のグリフをクリックしてからドラッグすることによっても設定可能です。


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
また、 "デバイステーブル" というものを作成することができます。
この名前からはそれが何だかよく分かりません。
フォントを小さなピクセルサイズでラスタライズする時、
丸め誤差が非常に重要になります。
とくにカーニングでは、丸めの対象になるのがアウトラインの位置
(それらをピクセルグリッドに合わせるため) と、
グリフの送り幅およびカーニング値そのものの 3 つあるため、
事態はとくに深刻です。
その結果、150 ピクセルで完璧にカーニングが行われていたものが
12 ピクセルで近すぎたり遠すぎたりすることになります。

![](/assets/img/dialogs1-kern-We-150.png)

<!--
Kerning at 150 pixels
-->
150 ピクセルでのカーニング

![](/assets/img/dialogs1-kern-We-12.png)

<!--
Kerning at 12 pixels (magnified by 2)
-->
12 ピクセルでのカーニング（2倍に拡大）

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
もちろん、カーニング値を微妙に調節して、
12 ピクセルで正しく見えるようにできたはずですが、
今度は 14 ポイントで問題が起こるでしょう。
そういうわけで、 OpenType ではデバイステーブルという概念を導入し、
このテーブルを用いて特定のポイントサイズで小さな修正ができるようにしています。
単純にディスプレイサイズをよく使われる小さい値 (例えば 10-24) に設定して、
カーニングを目で確かめてください。
醜い結果が得られた場合、 "デバイステーブル補正" フィールドに値を入力すると、
指定された表示サイズのスペーシング (だけ) が指定したピクセル数だけ変更されます。
上の例では、12 ピクセル表示では 1 ピクセルの補正が適切でしょう。

<!--
Because small pixel sizes can be hard to examine, you can change the
magnification (rasterized at the same size, but each pixel made twice as
big).
-->
小さなピクセルサイズは目で確かめるのが困難なため、
拡大率を変更することができます
(同じサイズでラスタライズされますが、各ピクセルが 2 倍に拡大されます)。


<!--
### Kern Pair Closeup
-->
### カーニングペアの詳細

<!--
[Device Tables](#Device+Table) may also be created in a
number of other cases. The example above was for a kerning class.
Kerning pairs may also have tables attached to them with the
Metrics->Kern Pair Closeup dialog, which looks similar to the Kerning
Class dialog above.
-->
[デバイステーブル](#デバイステーブル) は他の多数の場合にも作成することができます。
上の例はカーニングクラスに対するものでした。
カーニングペアにも、上のカーニングクラスダイアログとよく似た
<span class="command">メトリック->カーニングペアの詳細</span>
ダイアログが用意されています。

![](/assets/img/dialogs1-kernpairclose.png)
