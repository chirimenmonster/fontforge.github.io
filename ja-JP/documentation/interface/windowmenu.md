---
published: true
layout: default.ja
title: ウィンドウメニュー
---
<!--
published: true
layout: default
title: The Window Menu
-->

[table_of_contents]


<!--
#### Open Outline
-->
#### アウトラインウィンドウを開く(U) (Open Outline)

<!--
In the font view this will open outline views on all selected glyphs (if
there are more than 15 or so it will ask whether you really meant to do
that).
-->
フォントビューでは、選択されたすべてのグリフのアウトラインを開きます
(一度に 15 個を超えるグリフを選択しているときは、本当に全部開くかどうか質問します)。

<!--
In the bitmap view it will open an outline view on the current glyph.
-->
ビットマップビューでは、そのグリフのアウトラインビューを開きます。

<!--
In the metrics view it will open an outline view on whatever glyph is
active.
-->
メトリックビューでは、すべてのアクティブなグリフのアウトラインビューを開きます。

<!--
This menu item is always grey in an outline view.
-->
アウトラインビューではこのメニュー項目はつねに灰色表示になっており、選択できません。

<!--
Note: It is possible to have more than one window displaying the same
glyph. Any editing that occurs in one should be reflected in all.
-->
注意: 同じグリフを 2 個以上のウィンドウで同時に表示することもできます。
あるウィンドウで行った編集操作はいつでも全てのウィンドウに反映されます。


<!--
#### Open Bitmap
-->
#### ビットマップウィンドウを開く(B) (Open Bitmap)

<!--
In the font view this will open bitmap views on all selected glyphs (if
there are more than 15 or so it will ask whether you really meant to do
that). If the font view is displaying a bitmap then it will open a
bitmap view showing that pixelsize, otherwise it will pick a pixelsize.
-->
フォントビューでは選択中のすべてのグリフのビットマップビューを開きます
(一度に 15 個を超えるグリフを選択しているときは、本当に全部開くか質問します)。
フォントビューがフォントのビットマップを表示しているときは、
そのピクセルサイズのビットマップビューを開きます。
それ以外の場合はあるサイズを自動的に選びます。

<!--
In the outline view it will open a bitmap view on the current glyph. It
will pick a pointsize.
-->
アウトラインビューでは、そのグリフのビットマップビューを開きます。
サイズは勝手に選ばれます。

<!--
In the metrics view it will open an outline view on whatever glyph is
active, as with the font view, if it is displaying a bitmap it will use
its pixelsize, otherwise it will pick a pixelsize.
-->
メトリックビューでは、全てのアクティブなグリフのビットマップビューを表示します。
フォントビューと同様に、ビットマップ表示のときにはそのピクセルサイズのビットマップを選び、
その他の場合はピクセルサイズは自動的に選びます。

<!--
This menu item is always grey in an bitmap view.
-->
このメニュー項目はビットマップビューではつねに灰色表示になっていて、選択できません。

<!--
Note: It is possible to have more than one window displaying the same
glyph. Any editing that occurs in one should be reflected in all.
-->
注意: 同じグリフを 2 個以上のウィンドウで同時に表示することもできます。
あるウィンドウで行った編集操作はいつでも全てのウィンドウに反映されます。


<!--
#### Open Metrics
-->
#### メトリックウィンドウを開く(M) (Open Metrics)

<!--
In the font view it will open a metrics view displaying all selected
glyphs (the order in which you selected those glyphs is important). The
new metrics view will display whatever the font view displays (outline
or bitmap).
-->
フォントビューでは、選択中のすべてのグリフを表示するメトリックビューを表示します
(それらのグリフが選択された順番は重要です)。
新規のメトリックビューは、フォントビューが表示しているのと同じ物
(アウトラインまたはビットマップ)を開きます。

<!--
In the outline view it will open a metrics view displaying the current
glyph. The display will be an outline.
-->
アウトラインビューでは、現在のグリフを表示するメトリックビューを表示します。
アウトラインを表示します。

<!--
In the bitmap view it will open a metrics view displaying the current
glyph. The display will be a bitmap in the current size.
-->
ビットマップビューでは、現在のグリフを表示するメトリックビューを表示します。
表示されるのは、現在のサイズのビットマップです。

<!--
This menu item is always grey in the metrics view.
-->
このメニュー項目はメトリックビューでは常に灰色表示になっていて、選択できません。

<!--
It is possible to have more than one metrics view open at a time.
-->
メトリックビューは、同時に 2 個以上開くことができます。


<!--
#### (window titles...)
-->
#### (ウィンドウタイトル...) (window titles...)

<!--
After that the window menu is just a list of all the open windows. If
the window has been changed (and not saved since) then it has a white
background. The names of font views are in red. Views connected to a
given font will all be displayed together (with the font view on top).
Clicking on an entry raises that window.
-->
メニューのこの後ろの部分は、開いているウィンドウの単なる一覧表示です。
ウィンドウで編集作業を行った (かつ、それから閉じていない) 場合、
その背景は白く表示されます。
フォントビューのウィンドウ名は赤で表示されます。
同じフォントを編集するビュー同士はまとめて表示されます (一番上にはフォントビューが来ます)。
メニューの項目をクリックすると、該当するウィンドウが最前面に表示されます。
