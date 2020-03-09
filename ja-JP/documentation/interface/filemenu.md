---
published: true
layout: default.ja
title: ファイルメニュー
---
<!--
published: true
layout: default
title: The File Menu
-->


<!--
* [New](#new)
* [Open](#open)
* [Browse Web](#browse-web)
    * [Browse Open Font Library](#browse-open-font-library)
* [Recent](#recent)
* [Close](#close)
* [Close Tab](#close)
<p style="border: 1px solid black>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"></p>
* [Save](#save)
* [Save As&hellip;](#save-as)
* [Save All](#save-all)
* [Generate Fonts&hellip;](#generate-fonts)
* [Generate Mac Family&hellip;](#generate-mac-family)
* [Generate TTC&hellip;](#generate-ttc)
* [Export&hellip;](#export) <br/>
* [Import&hellip;](#import)
* [Merge Feature Info&hellip;](#merge-feature-info)
* [Revert File](#revert)
* [Revert to Backup](#revert-to-backup)
* [Revert Glyph](#revert-glyph)
* [Clear Special Data](#clear-special-data) <br/>
* [Load Word List&hellip;](#load-word-list) <br/>
* [Print&hellip;](#print) <br/>
* [Execute Script&hellip;](#execute-script) <br/>
* [Preferences&hellip;](#preferences)
* [Script Menu](#script-menu)
* [X Resource Editor&hellip;](x-resource-editor) <br/>
* [Quit](#quit)
-->
* [新規(N) (New)](#新規n-new)
* [開く(O) (Open)](#開くo-open)
* [ウェブを表示 (Browse Web)](#ウェブを表示-browse-web)
    * [Open Font Library を表示 (Browse Open Font Library)](#open-font-library-を表示-browse-open-font-library)
* [最近開いたファイル(T) (Recent)](#最近開いたファイルt-recent)
* [閉じる(C) (Close)](#閉じるc-close)
* [タブを閉じる (Close Tab)](#タブを閉じる-close-tab)
* [保存(S) (Save)](#保存s-save)
* [ファイル名を指定して保存(A)&hellip; (Save As&hellip;)](#ファイル名を指定して保存a-save-as)
* [すべて保存(L) (Save All)](#すべて保存l-save-all)
* [フォントを出力(G)&hellip; (Generate Fonts&hellip;)](#フォントを出力g-generate-fonts)
* [Mac ファミリーを出力（F)&hellip; (Generate Mac Family&hellip;)](#mac-ファミリーを出力f-generate-mac-family)
* [TTC を出力 (Generate TTC&hellip;)](#ttc-を出力-generate-ttc)
* [書き出し(T)&hellip; (Export&hellip;)](#書き出しt-export)
* [取り込み(I)&hellip; (Import&hellip;)](#取り込みi-import)
* [機能情報を統合&hellip; (Merge Feature Info&hellip;)](#機能情報を統合-merge-feature-info)
* [ファイルを再読み込み(R) (Revert File)](#ファイルを再読み込みr-revert)
* [バックアップを復元(B) (Revert to Backup)](#バックアップを復元b-revert-to-backup)
* [グリフを戻す(Y) (Revert Glyph)](#グリフを戻すy-revert-glyph)
* [特殊データを消去 (Clear Special Data)](#特殊データを消去-clear-special-data)
* [単語リストの読み込み (Load Word List&hellip;)](#単語リストの読み込み-load-word-list)
* [印刷(P)&hellip; (Print&hellip;)](#印刷p-print)
* [スクリプトを実行(X)&hellip; (Execute Script&hellip;)](#スクリプトを実行x-execute-script)
* [環境設定(E)&hellip; (Preferences&hellip;)](#環境設定e-preferences)
* [スクリプトメニュー (Script Menu)](#スクリプトメニュー-script-menu)
* [X リソースエディタ (X Resource Editor&hellip;)](#x-リソースエディタ-x-resource-editor)
* [終了(Q) (Quit)](#終了q-quit)


* * * * *


<!--
#### New
-->
#### 新規(N) (New)

<!--
Creates a new font with (by default) ISO 8859-1 (Latin1) encoding. The
default encoding may be changed in the preference dialog.
-->
新しいフォントを
(デフォルトでは) ISO 8859-1 (Latin1) エンコーディングで作成します。
デフォルトのエンコーディングは環境設定ダイアログで変更可能です。


<!--
#### Open
-->
#### 開く(O) (Open)


![example of the dialog to open a font file](/assets/img/filemenu-openfont.png)

<!--
Brings up a file chooser and allows you to open a font in any of the
formats FontForge understands.
-->
ファイル選択画面が現れ、
FontForge が理解する全てのフォーマットのフォントを選べるように表示します。

<!--
If you open a truetype font containing bitmaps then you will be asked if
you want to load some of the bitmaps as well as the outlines.
-->
ビットマップフォントを含んだ TrueType フォントを開くときには、
アウトラインの他にどのビットマップを読み込むかを訊かれます。

<!--
By default this dialog will display all files with extensions of pfa,
pfb, pt3, sfd, ttf, otf, otb, t42, cef, cff, gsf, ttc, svg, ik, mf and
bdf (possibly others as FontForge comes to support more formats). You
can change this with the Filter pull down list -- there are several
standard filters, and you may define your own.
-->
このダイアログはデフォルトで拡張子
pfa, pfb, pt3, sfd, ttf, otf, otb, cef, cff, gsf, ttc, svg, ik, mf および bdf
(FontForge が他のフォーマットをサポートすればもっと増えるでしょう)
をもつファイルを全て表示します。
これは
<span class="command">フィルタ</span>
プルダウンリストで変更できます
-- 標準でいくつかのフィルタがあり、
また、自分で定義することもできます。

<!--
You may select multiple files (by holding down the shift or control
keys when clicking on them), and all selected files will be opened.
-->
複数のファイルを
(Shift または Control キーを押しながらクリックすることによって)
選択することができ、
その操作によって選択された全ファイルが開かれます。

<!--
FontForge can open macbinary resource files containing postscript and
truetype fonts (it does not open bitmap fonts currently)
-->
FontForge は PostScript や TrueType フォントを含んだ Mac バイナリリソースを開くことはできません
(現在はビットマップフォントを開きません)。

<!--
FontForge does not open Acorn RISC/OS files, but you can use
[acorn2sfd](../../utilities/acorn2sfd/) to convert them into
an sfd file which FontForge can then open.
-->
FontForge では Acorn RISC/OS フォントは開けませんが、
[acorn2sfd](../../utilities/acorn2sfd/)
を使えば FontForge が開ける SFD ファイルに変換することができます。<BR>

<!--
If you have [mf](http://www.tug.org/) and
[autotrace](http://sourceforge.net/projects/autotrace/) installed on
your machine FontForge will process metafont's mf files for you. But you
might want to use *pktrace, mftrace* or some other standalone program to
do the job.
-->
[mf](http://www.tug.org/)
と
[autotrace](http://sourceforge.net/projects/autotrace/)
がインストールされているならば、
FontForge は METAFONT の mf ファイルを処理することができます。
しかしながら、*pktrace や mftrace* などのスタンドアローンのプログラムに処理をしたほうがいいかもしれません。

<!--
When opening a TTC file, or a mac dfont -- files which potentially
contain several fonts -- you will be given a dlg showing a list of all
fonts in the file, you get to pick which you want to open. (FontForge
does not provide a way to open all fonts in a file at once). If you know
the fontname you are interested in you may append it to the filename in
the open dlg as: `Helvetica.dfont(Helvetica Bold)` or if you know the
font index `Helvetica.dfont(0)` (indeces start at 0, not 1).
-->
TTC ファイルまたは mac dfont (複数のフォントを含む可能性のあるファイル)
を開くと、
ファイル内のすべてのフォントのリストを示すダイアログが表示され、
開くものを選択できます。
(FontForgeは、ファイル内のすべてのフォントを一度に開く方法を提供しません)。
開きたいフォント名がわかっている場合は、
開いているダイアログのファイル名に次のように追加します:
`Helvetica.dfont(Helvetica Bold)`。
そうでなくて、フォントインデックスがわかっている場合には
`Helvetica.dfont（0）` (1ではなく0から始まります)
のように追加します。

<!--
When FontForge opens a pdb file (one that contains palm bitmap fonts) it
will open the first font it finds. In most formats it will list the
available fonts in a file and ask which you want, but palm fonts contain
no fontname so there is no way to identify them.
-->
FontForge が (palm ビットマップフォントを含む) pdb ファイルを開くときには、
最初に見つかったフォントを開きます。
ほとんどのフォーマットではファイル内の編集可能なフォントが一覧表示され、
どれを編集したいかを尋ねるのですが、
palm フォントにはフォント名がないのでそれらを識別する方法がないのです。

<!--
When importing a type3 font FontForge will ask you a few questions. It
shouldn't have to ask these questions, but this is an imperfect world
and FontForge an imperfect program. In some rare cases FontForge will
crash if it tries to do a remove overlap. The remove overlap
functionality is important for interpreting stroked paths so you really
should have it on. But if a crash happens then, turn it off (and the
crash should not repeat, but some functionality will be lost).
-->
Type3 フォントを取り込むときは、
FontForge はいくつかの事柄を質問します。
本来はこれらの質問は不要なはずですが、
世の中はそう完全ではなく、
FontForge も不完全なプログラムなのです。
ある特殊な場合には
FontForge はパスの重複を取り除こうとすると異常終了してしまいます。
重複除去の機能は太さのある線として表現されたパスを解釈する場合に重要なので、
通常はそれを使用可能にするべきです。
しかし、プログラムが異常終了する場合はその機能を停止してください
(この場合プログラムはクラッシュしないはずですが、いくつかの機能は使用できません)。

<!--
Not all font formats that fontforge supports have standard extensions.
Mac resource forks are one example, postscript cid, type0 and type3
fonts are another. FontForge can still open these formats, even if it
fails to display the file. You can always type the file name in yourself
if you don't see it in the file list.
-->
FontForge がサポートする全てのファイルフォーマットが標準的な拡張子をもっているわけではありません。
Mac のリソースファイルがその一例ですし、
他にも PostScript CID フォントや Type1, Type3 フォントがそうです。
FontForge はそれらのファイルが表示されていない場合でも、
それらのフォーマットのファイルを開くことができます。
ファイルリスト内に表示されていない場合、ファイル名を自分で打ち込むことが常に可能です。

<!--
FontForge can also read (many) fonts out of a pdf file. FontForge
usually does not list pdf files (because they aren't really designed as
mechanisms for transporting fonts and most such fonts will be incomplete
due to subsetting and other optimizations), but you can always type in
the name of one directly (or use the [Filter] button to define a filter
for pdf files).
-->
FontForge は、PDF ファイルから (多数の) フォントを読み込むこともできます。
FontForge は通常は PDF ファイルをリスト表示に含めません
(なぜなら、それらは本当はフォントを転送するための機能として設計されているわけではなく、
そのようなフォントは殆どの場合、
サブセット化を初めとする各種の最適化によって不完全な物になっているからです)
が、それを直接タイプ入力することは常に可能です
(または *.pdf を表示するために
<span class="command">フィルタ(F)</span>
ボタンを押してください)。

<!--
You can also force fontforge to rename all the glyphs in the font being
read in to fit some standard naming convention. See the section on
[namelists](../encodingmenu/#namelists) for more information.
-->
また、フォントの読み込み時に、グリフ名を何らかの標準的な命名規約に一致するように
FontForge が強制的に改名を行うように強制することもできます。
より詳しい情報については
[名前リスト](../encodingmenu/#namelists)
のセクションをご覧ください。

****

<!--
The dialog has several buttons at the top, one takes you to your home
directory, one to the directory above the current one and the other two
produce menus. The bookmark menu allows you to pick a directory from
your list of bookmarks, and to add to or remove from your list of
bookmarks, you may also move backwards and forwards on your directory
stack. The tools menu allows you to rearrange how the dialog works. You
may set it to show hidden files (on unix files beginning with "." are
"hidden"), you may set it so that directories are displayed amid other
files, in alphabetical order, so that directories precede normal files,
or so that there is a separate pane for directories.
-->
ダイアログの上部にはいくつかのボタンがあり、
1つはホームディレクトリに、
1つは現在のディレクトリの上のディレクトリに、
他の2つはメニューを生成します。 ブックマークメニューを使用すると、
ブックマークのリストからディレクトリを選択し、
ブックマークのリストに追加または削除したり、
ディレクトリスタックを前後に移動したりできます。 
ツールメニューを使用すると、
ダイアログの動作を再配置できます。
隠しファイルを表示するように設定できます
(UNIX では "." で始まるファイルは "非表示" です)、
ディレクトリが他のファイルの中でアルファベット順に表示され、
ディレクトリが通常のファイルに先行するように設定できます。
ディレクトリ用に個別のペインがあります。

****


<!--
#### Browse Web
-->
#### ウェブを表示 (Browse Web)

<!--
##### Browse Open Font Library
-->
##### Open Font Library を表示 (Browse Open Font Library)

<!--
Brings up a [dialog](../../reference/oflib/) which will browse fonts on the Open
Font Library website.
-->
Open Font Library の Web サイトでフォントを参照するダイアログを表示します。

<!--
#### Recent
-->
#### 最近開いたファイル(T) (Recent)

<!--
A submenu showing recently opened font files (it does not show the
current font).
-->
最近開いたフォントファイルを表示するサブメニューです
(現在のフォントは表示しません)。


<!--
#### Close
-->
#### 閉じる(C) (Close)

<!--
Closes the current window.
-->
現在のウィンドウを閉じます。

<!--
If this is a font view and the font has been changed, then it will ask
whether you want to save the font. It will also close any outline glyph,
bitmap glyph or metrics views associated with the font.
-->
閉じるウィンドウがフォントビューで、フォントに変更が加えられている場合、
そのフォントを閉じるかどうかを質問します。
ウィンドウを閉じるときには、
そのフォントのアウトライン文字、ビットマップ文字やメトリックビューを全て閉じます。


<!--
#### Save
-->
#### 保存(S) (Save)

<!--
Saves the current file. If it is associated with a spline font database
it will be saved there and a backup file will be created. If it is a new
font, or if the font has been read from a font file, then a Save As
dialog will pop up.
-->
現在のファイルを閉じます。
対応するスプラインフォントデータベースがある場合はそのファイルに保存され、
バックアップファイルが作成されます。
新規に作成したフォントの場合か、
フォントファイルから読み込まれた場合は、
<span class="command">ファイル名を指定して保存</span>
ダイアログが起動します。

<!--
If you are editing a font "Ambrosia.sfd" then the backup file will be
called "Ambrosia.sfd&tilde;".
-->
フォント "Ambrosia.sfd" を編集している場合、
バックアップファイルは "Ambrosia.sfd&tilde;" となります。


<!--
#### Save As...
-->
#### ファイル名を指定して保存(A)... (Save As...)

<!--
Allows you to give a new name to the current spline font database. Pops
up a file picker.
 Normally fonts are saved into "sfd" files (a single file containing all
the information needed to regenerate your font), but you may choose to
save it into a directory format where every glyph has its own file.
-->
現在のスプラインフォントデータベースを別の名前で保存することができます。
ファイル選択ダイアログが起動します。
通常、フォントは "sfd" ファイル
(フォントの再生成に必要なすべての情報を含む単一のファイル)
に保存されますが、
各グリフが独自のファイルを持つようなディレクトリ形式で保存することもできます。


<!--
#### Save All
-->
#### すべて保存(L) (Save All)

<!--
Saves all changed fonts. If any have not been named, it will pop up a
Save As file picker for that font.
-->
変更を加えた全てのファイルを保存します。
名前のついていないフォントがあれば、それに対して
<span class="command">ファイル名を指定して保存</span>
ファイル選択ダイアログが起動します。


<!--
#### Generate Fonts...
-->
#### フォントを出力(G) (Generate Fonts...)

<!--
[This generates font files](../generate/), both outline and bitmap. You
may choose not to generate either, you may generate an afm file or a pfm
file, you may select the type of postscript output, you may select which
pixelsizes of bitmap to generate. (See [that page](../generate/)for
more info)
-->
アウトラインとビットマップ両方の
[フォントファイルを出力します](../generate/)。
どちらも出力せずに、AFM ファイルや PFM ファイルを出力することができます。
PostScript 出力のタイプを選択したり、
どのピクセルサイズのビットマップを出力するかも選択できます。
(より詳しい情報は [このページ](../generate/) を参照してください)。


<!--
#### Generate Mac Family...
-->
#### Mac ファミリーを出力(F)... (Generate Mac Family...)

<!--
This is only available if there are multiple fonts open in the same
family, and if the current font is the "Plain" style of that family. It
generates a mac FOND structure containing references to all family
members, sfnt, and POST resources for all selected faces. It brings up a
[dialog](../generate/#generate-mac-family) very similar to the Generate fonts
dialog, but one that includes a list of all potential faces for family
members.
-->
このコマンドは、同じファミリーに属する複数のフォントを開いている時だけ利用可能です。
現在のフォントが「標準」スタイルとして扱われます。
このコマンドではファミリーの全メンバーへの参照を含む Mac の FOND データ構造と、
選択中の全書体に対する NFNT, sfnt および POST リソースを出力します。
この時、
<span class="command">フォントを出力</span>
ダイアログに非常によく似た
[ダイアログ](../generate/#generate-mac-family)
を起動しますが、
ファミリーに含まれる可能性のある全フォントの一覧を含んでいる点が異なります。


<!--
#### Generate TTC...
-->
#### TTC を出力... (Generate TTC...)

<!--
This is only available if there are multiple fonts open (they need not
be the same family). It opens a [dialog](../generate/#generate-ttc)
similar to the above listing all open fonts. You select which fonts go
into the ttc file and how they should be stored.
-->
これは、複数のフォントが開いている場合にのみ使用できます
(同じファミリーである必要はありません）)。
上記のような開いているすべてのフォントを一覧表示するようなダイアログが開きます。 
どのフォントを ttc ファイルに入れるか、およびそれらの保存方法を選択します。

<!--
#### Revert
-->
#### ファイルを再読込(R) (Revert)

<!--
Rereads the font from the file on the disk. All changes are lost.
-->
ディスクからフォントを読み込み直します。
全ての変更は失われます。


<!--
#### Revert To Backup
-->
#### バックアップを復元(B) (Revert To Backup)

<!--
Only available in the font view. When FontForge saves an sfd file (with
the [Save](#save) command, not the [Save As](#save-as) command) it
creates a backup version of the file containing the old data (this file
has the same name as the main branch with a "&tilde;" character appended to
it). This command will revert to the backuped version of the file (if
there is one).
-->
フォントビューでのみ使用可能です。
FontForge が SFD ファイルを
([<span class="command">ファイル名を指定して保存(A)</span>](#ファイル名を指定して保存a-save-as)
ではなく
[<span class="command">保存(S)</span>](#保存s-save)
コマンドで)
保存する時、
古いデータを含むバックアップ版のファイルを作成します
(このファイルの名前は本流のファイルと同じ名前に "&tilde;" を付け加えたものです)。
このコマンドは、(バックアップがある場合)、ファイルをバックアップした版に復元します。


<!--
#### Revert Glyph
-->
#### グリフを戻す(Y) (Revert Glyph)

<!--
Only available in the font and outline views. Rereads the font from the
sfd file on the disk searching for a glyph in that file with the same
name as the current glyph. All changes to this glyph will be lost (but
if the glyph has references then any changes made to the glyphs being
refered to will still be visible), *this command may be undone.*
-->
フォントビュー・アウトラインビューのみで利用可能です。
フォントをディスク上の SFD ファイルから読み込み直し、
そのフォント中に含まれている現在のグリフと同じ名前をもつグリフを探します。
全ての変更は失われます (ただし、そのグリフが他のグリフから参照されている場合、
参照されているグリフに対して今まで行われた変更はまだそのまま表示されています)。
*このコマンドは取り消しできません*。

<!--
So if you have changed the name of the glyph this command will fail.
-->
そのため、グリフ名を変更していると、このコマンドは失敗します。

<!--
If the font did not come from an sfd file this command will fail.
-->
フォントが SFD ファイルから読み込んだものでないお場合、コマンドは失敗します。

<!--
If the font has been reencoded and the glyph has references this
command may fail.
-->
フォントが再エンコードされたり、グリフに参照があると、コマンドは失敗します。

<!--
If you have made a global change to the font (like scaling it to a new
em-size) then the results may not be appropriate.
-->
フォントに大きなに変更を加えた場合
(新しい em サイズに拡大縮小するなど)、
結果は適切ではない可能性があります。


<!--
#### Clear Special Data
-->
#### 特殊データを消去 (Clear Special Data)

<!--
This function removes extra information in a font file that FontForge
cannot use.  The program that originally generated the font may have placed
information in the font file that is of no use to FontForge.
-->
この関数は、 FontForge が使用できないフォントファイルの余分な情報を削除します。
最初にフォントを生成したプログラムは、
FontForgeにとって役に立たないフォントファイルに情報を配置している可能性があります。

<!--
#### Export...
-->
#### 書き出し(T)... (Export...)

<!--
In the Outline view this allows you to export the splines that make up
the glyph into an encapsulated postscript (.eps), pdf, svg or xfig
format (.fig -- the conversion to fig format is not the best) file. You
may also have the glyph rasterized and output in either .xbm or .bmp (or
png if you have that library) formats (FontForge will prompt you for a
pixelsize. bmp also allows you to generate an anti-aliased image, and
you will be prompted for bits per pixel. 1 bit per pixel is a bitmap).
-->
アウトラインビューでは、
グリフを構成するスプラインを、
Encapsulated PostScript (EPS)、
PDF、SVG、Xfig (.fig -- fig フォーマットへの変換は最適ではありません)
のファイルに書き出すことができます。
また、グリフをラスタライズして
.xbm または .bmp (またはライブラリがあれば png) フォーマットに書き出すことができます
(FontForge はピクセルサイズを問い合わせます。
bmp ではアンチエイリアスされた画像を出力することもでき、
この時はビット毎のビット数を指定することができます。
1 ピクセルにつき 1 ビットの場合、ビットマップとなります)。

<!--
In the Bitmap view this allows you to export the current glyph as either
a .xbm or a .bmp (always as a bitmap) file.
-->
ビットマップビューでは、
現在のグリフを .xbmp または .bmp (常にビットマップとして) ファイルで書き出すこができます。

<!--
This menu item is not available in the Font or Metrics Views.
-->
このメニュー項目はフォントビューやメトリックビューでは使用できません。


<!--
#### Import...
-->
#### 取り込み(I)... (Import...)

<!--
In the Font View this allows you to import one or several bitmap fonts
(from a .bdf file or a ttf/otf/ttc file, TeX pk (gf) file, an X11 .pcf
file or a mac dfont) and merge it into the list of bitmap sizes stored
in the database. You may also load one bitmap font into the backgrounds
of the outline glyphs (So "A" from the bitmap font goes into the
background of the "A" outline glyph), this is to make tracing glyphs
easier. Be careful, you need to load a big bitmap for autotrace to be
useful. **NOTE:** FontForge is unable to read an encoding from pk files,
you will may need to set it with "Force Encoding" after you've loaded
the pk file.
-->
フォントビューでは
1 個または 2,3 個のビットマップフォントを
(.bdf ファイルまたは ttf/otf/ttc ファイル、
TeX の pk (gf) ファイル、
X11 の .pcf ファイル、
Mac の dfont から)
読み込み、
データベースにアウトライングリフと一緒に格納された各種のサイズのビットマップと併合することができます。
また、1 個のビットマップフォントをアウトライングリフの背景画像として取り込むことができ
(これによりビットマップフォントから得た "A" を "A" のアウトライングリフの背景に置くことができます)、
これによりトレース作業が簡単になります。
自動トレースで実用的なアウトラインを生成するためには、
大きなビットマップを読み込む必要があることにご注意ください。
**注意** FontForge は pk ファイルからエンコーディングを読み込むことができません。
pk ファイルを読み込んだ後で
<span class="command">エンコーディングを強制</span>
ダイアログで設定してやる必要があるでしょう。

<!--
You may also load images into the glyph backgrounds. There are two ways
to do this, you may either select several image files and they will be
loaded consecutively into selected glyphs, or you may select an image
template and all images whose filename match that template will be
loaded into the backgrounds of the appropriate glyphs. Image templates
look like "uni\*.png" or "enc\*.gif" or "cid\*.tiff". You select the
template by selecting a filename which matches that template -- So if you
select "uni1100.gif" then all image files which start with "uni" and end
with ".gif" and contain a valid unicode number will be loaded and placed
in the appropriate place. Files named "enc\*" or "cid\*" are handled
similarly except that they specify the current encoding (and the number
must be in decimal rather than hex).
-->
グリフの背景に画像を取り込むこともできます。
これを行うには 2 つの方法があり、
いくつかの画像ファイルを選択して選択されたグリフに順に取り込む方法と、
画像名テンプレートを選択してそのファイル名に一致する全ての画像を該当するグリフの背景に取り込む方法のどちらも可能です。
画像名テンプレートは
"uni\*.png" または "enc\*.gif" あるいは "cid\*.tiff"
といった形式が使えます。
-- したがって、
"uni1100.gif" を選択すると、
"uni" で始まり ".gif" で終わり、
有効な Unicode コード番号を含むすべての画像ファイルがロードされ、
適切な場所に配置されます。 
"enc\*" または "cid \*" という名前のファイルは、
現在のエンコードを指定することを除いて、
同様に処理されます
(そして、数値は 16 進数ではなく 10 進数でなければなりません)。

<!--
If you are editing a [multi-layered font](../multilayer/) then you can also
import an image into one of the foreground layers.
-->
[複数レイヤーフォント](../multilayer/)
を編集している場合
(かつ FontForge がその機能つきでコンパイルしてある場合)、
画像を前面レイヤのどれかに取り込むことも可能です。

<a name="bitmapfiles"></a>
<!--
*FontForge does best when given bitmap images. It will grey out the
foreground and make the background transparent. It will also compress
them when it stores them in the sfd file. It will handle most other
image formats but does not try to optimize them in anyway. Please use
bitmaps here.*
-->
*FontForge は、ビットマップ画像が指定された時に最もよく機能します。
前面を灰色にして背面を透明にします。
画像を SFD ファイルに保存する時圧縮を行います。
その他ほとんどの画像フォーマットも通常扱うことができますが、
それらに対しては最適化を一切試みません。
ここではビットマップを使用してください。*

<!--
You may load an encapsulated postscript file (or rather the sub-set of
postscript that FontForge understands) into the foreground of glyphs. As
with images above this may import either depending on the selection or a
template.
-->
EPS ファイル (と言うよりは、FontForge が解釈可能な PostScript のサブセット)
をグリフの前面に読み込むこともできます。
上に記した画像ファイルと同様に、これは選択範囲またはテンプレートに依存します。

<!--
If you have libxml2 on your system then FontForge will also be able to
import svg files. As with postscript, only a subset of svg is
understood).
-->
システムに libxml2 がインストールされていれば、
FontForge は SVG ファイルを取り込むことができます。
PostScript と同様に、
解釈可能なのは SVG のあるサブセットのみです。

<!--
In the Outline View this allows you to import an image into the
background (see the above remark about [bitmaps](#bitmapfiles)), or
import eps or fig files into the foreground (the xfig conversion is
really bad, the eps conversion is very limited).
-->
アウトラインビューではこの機能によって画像を背景に読み込むことができます
([ビットマップ](#bitmapfiles) に関する上の注意をお読みください)。
また、EPS か fig ファイルを前面に読み込むことも可能です
(xfig からの変換は非常にお粗末で、EPS からの変換機能は非常に限られています)。

<!--
In the Bitmap View this allows you to import a bitmap image into the
glyph.
-->
ビットマップビューで使用すると、ビットマップ画像を編集中のグリフに読み込むことができます。

<!--
This menu item is not available in the Metrics View
-->
このメニュー項目はメトリックビューでは使用できません。

<!--
In the font view you may select multiple files (by holding down the
shift or control keys when clicking on them), and all selected bitmap
fonts will be imported into the sfd.
-->
フォントビューでは
(Shift または Control キーを押しながらクリックして)
複数のファイルを選択することができ、
全ての選択されたフォントが SFD に取り込まれます。


<!--
#### Merge Feature Info...
-->
#### 機能情報を統合... (Merge Feature Info...)

<!--
Only available in the font view window. This command will allow you to
search for an [adobe feature file](../../reference/featurefile/) (.fea) for
feature/lookup information or an afm, ofm, tfm, pfm or mac resource file
containing kerning pairs for the specified font. In many cases it will
not be needed because when FontForge opens a .pfa or .pfb font it will
automagically search for an appropriate .afm file in the same place. But
sometimes afm files are stored in other directories. And sometimes you
want to import information from TeX, from mac resource files or from
windows pfm files.
-->
フォントビューウィンドウでのみ使用可能です。
このコマンドは指定されたフォントに対応する、
AFM, OFM, TFM, PFM またはカーニングペアを含む Mac のリソースファイルを検索します。
FontForge は .pfa または .pfb ファイルを開く時に、
適切な .afm ファイルが同じ場所にあるかの検索を自動的に行うので、
これはたいていの場合必要ありません。
しかし AFM ファイルは別のディレクトリに格納されている場合もあります。
そういうわけで、情報を TeX, Mac のリソースファイルや
Windows の pfm ファイルから読み込みたい場合も時にはあります。<BR>

<!--
**NOTE:** FontForge is unable to read an encoding from tfm/ofm files or
from mac resource files, it is your responsibility to ensure that the
encoding of your font matches that of the tfm file *BEFORE* merging
kerning information. This is unfortunate, sorry.
-->
**注意:** FontForge は TFM/OFM や Mac のリソースファイルからエンコーディングを読み込むことはできません。
編集中のフォントのエンコーディングが、TFM ファイルのそれと一致しているかどうかを、
カーニング情報を取り込む *前に* 確認するのはあなたの責任です。
不幸なことで、申し訳なくは思いますが。

<!--
Note: When loading a postscript font from a mac resource file, the
associated kerning data will be found in the FOND stored with a bitmap
font for this face. FontForge can't guess the name of this file when
loading the font. You must figure it out yourself.
-->
注意: PostScript フォントを Mac のリソースファイルから読み込むとき、
それに伴うカーニングデータはその書体のビットマップとともに FOND から捜し出せるでしょう。
FontForge はフォントを読み込むときにこのファイルの推測を行うことはできませんので、
あなた自身が指定を行う必要があります。


<!--
#### Load Word List...
-->
#### 単語リストの読み込み... (Load Word List...)

<!--
It can be helpful to create a set of words that demonstrate how specific
glyphs of the font look when placed next to each other.  This function allows
you to import a saved list of these words, instead of having to retype them.
-->
フォントの特定のグリフが隣り合って配置されたときにどのように見えるかを示す単語のセットを作成すると役立ちます。
この関数を使用すると、これらの単語を再入力する代わりに、保存したリストをインポートできます。

<!--
#### Print...
-->
#### 印刷(P)... (Print...)

<!--
Not available in the bitmap view. Allows you to print out all the glyphs
in the font, a text sample of the font, or specific glyphs at a very
large scale.
-->
ビットマップビューでは使用できません。
フォント内の全てのグリフ、そのフォントによるテキストサンプルの表示、
または非常に大きなサイズでの特定のグリフの表示のいずれかを印刷することができます。

<!--
See the section on [printing](../display/) for more information.
-->
より詳しい情報についてはセクション [印刷](../display/) を参照してください。


<!--
#### Execute Script...
-->
#### スクリプトを実行(X)... (Execute Script...)

<!--
Only in the font view. Brings up a dlg and allows you to enter a
[script](../../scripting/native/), which could be just calling a prewritten
script file. There is a [Call] button in the dlg to help you locate any
such files. The default extension is "\*.pe" (postscript edit) but you
can change that with the [Filter] button if you use something else.
-->
フォントビューでのみ使用可能です。
ダイアログが起動するので、そこに
[スクリプト](../../scripting/native/)
を入力すことができます。
ここで既に存在するスクリプトをそのまま実行することもできます。
ダイアログにはスクリプトファイルを読み込むための
<span class="command">呼び出す</span>
ボタンがあります。
デフォルトの拡張子は "\*.pe" (PostScript edit) ですが、
<span class="command">フィルタ(F)</CODE>
ボタンを使えば何らかの別のパターンを使うことができます。


<!--
#### Script Menu
-->
#### スクリプトメニュー (Script Menu)

<!--
Only in the font view. You may define up to 10
[scripts](../../scripting/native/#menu) that you want to execute frequently and
place them in this menu. The scripts may also be invoked by short cut
with the first one being invoked by Control-Meta(Alt)-1, the second
Control-Meta-2, and the tenth by Control-Meta-0. The scripts are set in
the [preferences dialog](../prefs/#script-menu)
-->
フォントビューでのみ使用可能です。
10 個までのよく実行される
[スクリプト](../../scripting/native/#menu)
を登録してこのメニューに追加することができます。
スクリプトにはショートカットが割り当てられ、
最初のスクリプトは Control-Meta(Alt)-1,
2 番目には Control-Meta-2,
10 番目は Control-Meta-0 で起動できます。
スクリプトは [環境設定ダイアログ](../prefs/#script-menu) で登録します。


<!--
#### Preferences...
-->
#### 環境設定(E)... (Preferences...)

<!--
This pops up a [dialog allowing you to configure various esoteric bits
of fontforge](../prefs/).
-->
これを選択すると、
[FontForge の多くの秘教的なビットを設定可能なダイアログ](../prefs/)
を起動します。

<!--
A number of things, like the colors used in FontForge, that might be
controlled from a preference window are controlled by [X
Resources](../../customizing/xres/) below.
-->
環境設定ウィンドウから設定可能であるべき多くの項目は
[X のリソース](../../customizing/xres/)
を用いて設定します。


<!--
#### X Resource Editor...
-->
#### X リソースエディタ... (X Resource Editor...)

<!--
[This dialog](../resedit/) allows you to edit FontForge's X Resources,
you may either save them to a file for perminant storage, or change the
current settings for this use of FontForge.
-->
[このダイアログ](../resedit/)
では、FontForge の X リソースを編集できます。
これらを永続的なストレージ用のファイルに保存するか、
FontForge の現在の設定を変更できます。

<!--
#### Quit
-->
#### 終了(Q) (Quit)

<!--
Exits the program, prompting you whether to save any changed fonts.
-->
変更された各ファイルを保存するどうかの確認を行ってからプログラムを終了します。
