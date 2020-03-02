---
published: true
layout: default.ja
title: メトリックビュー
---


[table_of_contents]


![](/assets/img/dialogs1-MetricsView.png)

メトリックビューでは、複数のグリフがどのように見えるかを確認したり、
それらの間の間隔を変更したりすることができます。
さまざまな OpenType の機能をこれらのグリフに適用し、
見た目の変化を確認することができます。

メトリックビューがフォントビューから作成された場合、
選択していたグリフ（最初の15個など）は、
選択された順序でビューに表示されます。
メトリックビューがアウトラインまたはビットマップグリフビューから作成された場合、
そのグリフのみが表示されます。
メトリックビューがビットマップグリフビューから作成された場合
（またはそのビューがビットマップフォントを表示しているときにフォントビューから作成された場合）、
メトリックビューにはビットマップが表示されますが、
ビットマップのメトリックは編集できません（アウトラインを表示するビューでメトリックの編集を行う必要があります）。

メニューバーの下には、一連のフィールドがあります。
最初は、選択した機能の中でどのルックアップを適用するかを決める文と言語の現在の組み合わせを示し、
次は、表示のための追加のユニコード文字を入力するテキストフィールドであり、
最後に、ルックアップサブテーブルのプルダウンリストがあります。
このテーブルはカーニングペアを作成する場合に使用されます（カーニングペアはそのサブテーブルの一部になります）。
その下には、フォントで定義されているすべての機能を示すリストがあります。
この画面でアクティブにするものを選択できます。
（注： 機能はアルファベット順に並んでいます。
ルックアップが実行される順序ではありません（大抵はその順序ではありません））。

文字を入力するときに、タイプして入力することはできません:

1.  フォントビューで文字（またはグリフ）を選択し、
    適切な場所のメトリックスビューにドラッグ&ドロップします
2.  ビューメニューを使用して、文字またはグリフを変更または挿入します
    （表示->グリフを挿入）
3.  メトリックビューを開く前に、フォントビューで文字を個別に順番に選択します。
    メトリックビューを開いたときに選択した順序で表示されます
4.  FontForgeには独自の風変わりな
    [入力メソッド](#Entering+non-ASCII+characters)
    があります


ビューの中央部分は、表示されているグリフで占められます。
アウトライングリフの場合、フォントの em-height がこの領域にちょうど収まるようにこれらのサイズが設定されます。
グリフの間に灰色の線があり、右側のグリフの原点と左側のグリフの幅を示しています。
ベースラインも灰色で描画されます。

メトリックビューは、3つのモードのいずれかになります（メトリック->ウィンドウタイプ）。

-   カーニングのみ -- 任意のペア間のカーニングを調整できます。
    グリフは表示されていますが、送り幅は設定できません
-   送り幅のみ -- 表示されている任意のグリフの送り幅を調整できます。
    カーニングは設定できません
-   両方 -- 以下を参照してください

グリフうちの1つがアクティブになります。
そのグリフには、左側（原点）に緑色の線があり、右側（幅）に青色の線があります。
この線をドラッグして幅を変更できます。
グリフをクリックして左または右にドラッグすると、グリフの左側のベアリング (lbearing) を変更できます。
緑色の線をドラッグして、このグリフとその左のグリフの間のカーニングを変更できます。
（小さなピクセルサイズの [デバイステーブル](#Device+Table) を作成する場合は、
[カーニングペアクローズアップダイアログ](#Kern+Pair+Closeup) を使用する必要があります）


カーニング

![](/assets/img/dialogs1-To-unkerned.png) ![](/assets/img/dialogs1-To-kerned.png)

グリフをクリックしてアクティブなグリフを変更できます。

矢印キーの up、down は、フィールドの値を1ずつ増加、減少させます。
Shift-up または -down で増減は10ずつになり、
Ctrl-Shift-up または -down では5ずつにになります。
Alt-up、-down、-left、-right を押すと、カーソルが上、下、左、右のフィールドに移動します。

表示領域の下には、テキストフィールドのセットがあります。
これらのフィールドのいずれかに新しい数値を入力して、グリフの対応するメトリックを変更できます。

単語のリストをメトリックビューに読み込むことができると便利な場合があります（1文字ずつ入力する必要がなくなります）。
テキスト入力フィールドにはプルダウンリストがあり、このリストの下部には、ファイルから単語リストを読み込むためのエントリがあります。
一度ファイルを選択すると、プルダウンリストに選択肢が表示されるようになります。
上下矢印キーを使用して、単語リスト内を移動できます。

表示される最初のグリフがヘブライ語やアラビア語（または他の右から左の言語）である場合、
表示領域全体が右から左に表示されます


**注** 右から左、左から右への記述方向を混在して表示するために Unicode 仕様で規定されている非常に複雑なアルゴリズムがあります。
ここではそれに従いません。
記述方向の決定は、最初のグリフのみによって行われます。


![](/assets/img/dialogs1-VerticalMetrics.png)

![](/assets/img/dialogs1-HebrewMetrics.png)

View->Vertical により、垂直メトリックとカーニングする表示ウィンドウを生成できます。
（これは、フォントで垂直メトリックが有効になっている場合にのみ使用できます。
Element->Font Info->General->Has Vertical Metrics.
このモードでは、垂直幅、垂直カーニングなどを変更できます。

表示されているグリフのいずれかをダブルクリックすると、
FontForge はアウトライングリフビューを表示して、そのグリフを編集できるようにします。

![](/assets/img/dialogs1-MetricsView-features.png)

左の例では、入力テキストは "f" の後に "i" が続いており、
'liga' 機能がオンになると、これは "fi" の合字になります。
次に、"a" の後に "b" が続きますが、
'smcp' （スモールキャップ） 機能がオンになっているため、
これらは小文字ではなくスモールキャピタル文字になります。
最後に "1", "/", "2" が入力され、
'frac' （対角分数）機能がオンになると、
これら3つの入力グリフは出力時には1/2のグリフになります。

注： このウィンドウは完全なレイアウトエンジンではありません。
すべてのグリフは同じ文の中にあるかのように扱われ、すべての機能がすべてのグリフに適用されます。
ベースラインの位置合わせは行われません。

### ASCII以外の文字を入力する

### Entering non-ASCII characters

私たちのほとんどは、ASCII文字のみがオンになっているキーボードで立ち往生しています
それら。 または、せいぜいISO 8859-1文字のサブセット。 どうすればフル
Unicode文字の範囲を入力しますか？

Most of us are stuck with keyboards that only have ASCII characters on
them. Or at best some sub-set of ISO 8859-1 characters. How can the full
range of unicode characters be entered?

Xは、文字を入力するための洗練されたメカニズムを提供します
スタンドアロン[入力メソッドサーバー]（../../ reference / xim /）。 FontForgeのサポート
これは今ある程度。

X supplies a sophisticated mechanism for entering characters via
stand-alone [input method servers](../../reference/xim/). FontForge supports
this to some extent now.

それとは別に、Xの多くのバージョンは「文字の作成」キーを提供します。
同等のもの。 Xソフトウェアはキーストロークのシーケンスをマップします
ネイティブエンコーディングが何であれ1文字になります。

Aside from that, many versions of X supply a "Compose Character" key, or
something equivalent. The X software will map a sequence of keystrokes
to one character in whatever the native encoding may be.

私のキーボードにはそのようなキーがありませんし、Xはこれを行いません。 しかし、私
少ない人たちのためにそれらの線に沿って何かを実装しました
高価なキーボード。 テキスト入力が可能なモードの場合
次に、F12キーを押して、一連のキーストロークを実行します。 アクセント付き
文字は次を使用して作成できます。

My keyboard doesn't have such a key, and my X doesn't do this. But I
have implemented something along those lines for those of us with less
expensive keyboards. If you are in a mode where text entry is possible
then press the F12 key and follow it by a series of keystrokes. Accented
characters may be built using the following:

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

So Â may be built by [F12] \^ A, and A with diaeresis and macron may be
built with [F12] : \_ A.

Greek letters may also be created. If you start with [F12] @ and follow
with:

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

This is the mapping used by the Symbol font. (Lower case letters are
created similarly so [F12] @ a yields a lower case alpha). Accented
greek letters may also be built up, [F12] @ " A yields Alpha tonos.

Finally the following special characters may be built:

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

This still misses most unicode characters. But pressing [F12] twice will
bring up a dialog which will allow you to select any character in
unicode.

If you type [F12] by mistake then an Escape will get you out of accent
mode.


### Kerning By Class

多くの場合、同様にカーニングするグリフのクラスを作成することをお勧めします。
たとえば、A、À、Á、Â、Â、Ã、Äはおそらくすべてカーニングに似ています（ただし、
そのoとôはT）の後、おそらくかなり異なったカーニングであり、
上記の「A」のそれぞれに対して個別のカーニングペアを作成します。
同様にカーニングするグリフのクラスに配置されます。

Often it is a good idea to create classes of glyphs which kern alike.
For example A, À, Á, Â, Â, Ã and Ä probably all kern alike (but note
that o and ô probably kern quite differently after a T), and rather than
create separate kerning pairs for each of the "A"s above, they could all
be placed in a class of glyphs which kern alike.

The [Element->Font Info->Lookups](../lookups/) provides an interface
to this.

![](/assets/img/dialogs1-kerningformat.png)

それはすべてを示すダイアログを表示します
GPOSルックアップ（カーニングは1つ）とそのサブテーブル。 各セット
カーニングクラスは、独自のサブテーブルに存在します。 カーニングを作成するとき
サブテーブルには、個々のカーニングのセットが必要かどうかを尋ねられます
カーニングクラスに基づくペアまたは行列。

It brings up a dialog showing all the
GPOS lookups (of which kerning is one) and their subtables. Each set of
kerning classes lives in its own subtable. When you create a kerning
subtable you will be asked whether you want a set of individual kerning
pairs or a matrix based on kerning classes.

後者を選択した場合、FontForgeに良いものを推測させることができます
クラスのセット（選択されたグリフを見て分割します）
それらをクラスに入れます）。 「クラス内距離」により、いくつかの制御が可能になります
FontForgeがクラスに入るものについていかにうるさいのかについて。 （これは
em単位であり、おおよそ、平均誤差であると考えられます
2つの異なるグリフが他のグリフと相互作用する方法）。 値1は
非常にうるさく、ほぼすべてのクラスに1人のメンバーが含まれます。 20の値
（1000emフォント）はかなりゆるいです。

If you choose the latter then you may have fontforge try to guess a good
set of classes for you (it will look at the glyphs selected and divide
them into classes). The `Intra Class Distance` gives you some control
over how picky fontforge will be about what goes into a class. (This can
be thought of as being in em-units and being, roughly, the average error
in how two different glyphs interact with other glyphs). A value of 1 is
very picky and almost all classes will have one member. A value of 20
(in a 1000em font) is fairly loose.

AutoKerningでは、「デフォルトの分離」フィールドと「Min Kern」フィールドが使用されます。
すべてのグリフを光学的に分離するカーニングの目標
定数であり、「デフォルトの分離」フィールドは
望ましい値。 「Min Kern」の値は、単にダイアログが
無駄なジャンクでいっぱい。 AutoKerningが2つのグリフを示唆している場合
1 em単位でカーニングする必要があります。これにより、
人間の目とそれを含めることに意味はありません。カーニング値
（絶対値で）AutoKernによって提案された値が「Min Kern」よりも小さい場合
FontForgeはその値を無視します。 「[] Touching」を選択すると、
AutoKerningは、作成を試みるのではなく、わずかに異なる方法で動作します
光学距離は、これが
最小間隔が望ましい値である（これはめったに役に立たないが、
時折、文字が実際に触れる場所にテキストを設定したい
お互い）。 `[]だけカーニンググリフが近い`フラグは、FontForge
負のカーニングオフセットのみを生成します。つまり、
グリフを互いに近づけます。

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

![](/assets/img/dialogs1-kerningclass.png)

各カーニングクラスは[lookup
サブテーブル]（../ lookups /）とサブテーブル名が上部に表示されます
ダイアログ。

Each kerning class belongs to a [lookup
subtable](../lookups/) and the subtable name is displayed at the top of
the dialog.

しかし、より興味深いものはこれに続きます。 クラスごとのカーニング
クラスの2つのセットで構成されます-最初のグリフの1つのセット
ペアとペアの2番目のグリフ用の1つ。 グリフクラスは、
グリフ名のスペース区切りリスト（ほとんどのグリフについては、
Unicode文字自体を入力すると、FontForgeはそれを
グリフ名）。

But the more interesting stuff follows this. A kerning by class actually
consists of two sets of classes -- one set for the first glyph of the
pair and one for the second glyph of the pair. A glyph class consists of
a space separated list of glyph names (For most glyphs you may also
enter the unicode character itself, and fontforge will convert that to a
glyph name).

クラスを編集するには、単に入力します（クラスリストの一番下に
\ <New \>というエントリです。ここをクリックすると、新しいクラスが作成されます）。
クラスの右側にある小さな長方形を押すと、
フォントビューウィジェットで選択としてクラスを定義します。 してもいいです
クラスを選択（クリック）してクラスを削除します
[削除]ボタン。

To edit a class, simply type in it (at the very bottom of the class list
is an entry called \<New\>, clicking here will create a new class).
Pressing the little rectangle at the right of the class will allow you
to define your class as a selection in a font view widget. You may
delete a class by selecting it (clicking in it) and pressing the
[Delete] button.

カーニングクラスはかなり複雑になる場合があります。 グリフを検索するには
「Select Glyph」フィールドに名前を入力します。 これにより、
そのグリフを含むクラス。

The kerning classes can be fairly complex. You can search for a glyph by
typing its name in the "Select Glyph" field. This will highlight the
class containing that glyph.

クラス0は通常魔法です。 設定することはほとんどありません。
他で言及されていないグリフ。 OpenTypeでは、最初のクラス0
文字を設定でき、正常に動作します。

Class 0 is usually magic. You almost never set it, it contains any
glyphs not mentioned elsewhere. In OpenType, class 0 of the first
character can be set and behaves normally.

クラスの下には、カーニング値の表示があります。 可能性
最初のグリフクラスは垂直方向にリストされ、可能な2番目のグリフ
クラスは水平にリストされます。 クラスを選択すると（
上記のクラスリスト）カーニング値の表示はスクロールして表示されます
そのクラス。 マウスをディスプレイに移動させて休ませると、
ポップアップウィンドウが表示され、クラスを構成するグリフが表示されます
そのポイントで交差します。 のカーニング値をクリックすると
表示、dlgはその量の視覚的表現を表示します
字詰め。

Underneath the classes is a display of kerning values. The possible
first glyph classes are listed vertically, the possible second glyph
classes are listed horizontally. When you select a class (in one of the
class lists above) the display of kerning values will scroll to display
that class. If you move the mouse into the display and let it rest, a
popup window will appear showing the glyphs that make up the classes
which intersect at that point. If you click on a kerning value in the
display, the dlg displays a visual representation of that amount of
kerning.

カーニングダイアログには、各クラスの代表的なグリフが表示され、
それらの間のカーニングを調整することができます（および他のすべてのクラス
各クラスのメンバー）。 表示するグリフを選択できます
プルダウンメニュー。 値を入力して、新しいカーニングオフセットを入力できます。
または、カーニングペアの2番目のグリフをクリックしてドラッグすることができます
周り。

The kerning dialog displays a representative glyph from each class and
allows you to adjust the kerning between them (and all other class
members of each class). You can select which glyphs to display in the
pulldown menus. You can enter a new kerning offset by typing in a value,
or you can click on the second glyph of the kern pair and drag it
around.


### Device Table

また、「デバイステーブル」と呼ばれる名前を作成することもできます。
あまり有益ではありません。 フォントが小さなピクセルサイズでラスタライズされる場合
丸め誤差が重要になり、これは特に当てはまります
カーニング、丸みを帯びる3つのものがあります。
アウトライン（ピクセルグリッドに合わせるため）、
グリフ、カーニング値自体。 結果はその何かです
150pixelsで完全にカーニングされているように見えますが、近すぎるか遠すぎる可能性があります
12ピクセル離れている

You can also create something called a "Device Table", a name which is
not very informative. When a font is rasterized at small pixel sizes
rounding errors become important, and this is particularly true of
kerning, there are three things that get rounded: The locations of the
outlines (to fit them to a pixel grid), the advance widths of the
glyphs, and the kerning value itself. The result is that something which
looks perfectly kerned at 150pixels may be either too close or too far
apart at 12pixels

![](/assets/img/dialogs1-kern-We-150.png)

Kerning at 150 pixels

![](/assets/img/dialogs1-kern-We-12.png)

Kerning at 12 pixels (magnified by 2)

カーニング値は、正しく見えるまでわずかに調整できます。
もちろん12ピクセルですが、14ピクセルで壊れる可能性があります。 だからOpenType
デバイステーブルの概念があります
特定のポイントサイズでの修正。 表示サイズを単に
小さいが一般的な値（10〜24など）とカーニングを調べます。 もし
結果がいので、「Device Table Correction」に値を入力します
フィールド。これにより、指定された位置のピクセル数だけ間隔が変更されます。
表示サイズ（および他のサイズなし）。 上記の場合、1の修正は
12pxディスプレイに適しています。

You could adjust the kerning value slightly until it looked right at
12pixels, of course, but that might break it at 14 pixels. So OpenType
has the concept of a Device Table which allows you to add small
corrections at particular point sizes. Simply set the Display Size to a
small, but common, value (say 10-24) and examine the kerning. If the
results are ugly then type a value into the "Device Table Correction"
field, and this will change the spacing by that many pixels at the given
display size (and no other). In the case above a correction of 1 might
be appropriate for the 12px display.

小さなピクセルサイズを調べるのは難しいため、変更することができます
倍率（同じサイズでラスタライズされますが、各ピクセルは
大きい）。

Because small pixel sizes can be hard to examine, you can change the
magnification (rasterized at the same size, but each pixel made twice as
big).


### Kern Pair Closeup

[デバイステーブル]（＃Device + Table）は、
その他のケースの数。 上記の例はカーニングクラス用です。
カーニングペアには、
「メトリック」->「カーニングペアクローズ」ダイアログ。カーニングに似ています
上記のクラスダイアログ。

[Device Tables](#Device+Table) may also be created in a
number of other cases. The example above was for a kerning class.
Kerning pairs may also have tables attached to them with the
Metrics->Kern Pair Closeup dialog, which looks similar to the Kerning
Class dialog above.

![](/assets/img/dialogs1-kernpairclose.png)
