---
published: true
layout: default.ja
title: BDF 情報 (属性) ダイアログ
---
<!--
published: true
layout: default
title: BDF Info (Properties) Dialog
-->

![BDF Info dialog](/assets/img/dialogs1-bdfinfo.png)

<!--
If your font contains bitmaps you may want control over 
the BDF Properties associated with those bitmaps. Each
pixel size (bitmap strike) has its own set of properties.
-->
フォントにビットマップが含まれている場合、
それらのビットマップに付随する BDF の属性をいじりたくなる場合があります。
個別のピクセルサイズ (ビットマップストライク) ごとに、各々に固有の属性の組が存在します。

<!--
The X11 consortium has defined certain conventional properties and
defines their meaning in the [X Long Font
Descriptor](http://ftp.xfree86.org/pub/XFree86/4.5.0/doc/xlfd.txt)
specification.
-->
X コンソーシアムはお決まりの属性をいくつか定義し、
それらの意味を
[X 論理フォント記述子](http://ftp.xfree86.org/pub/XFree86/4.5.0/doc/xlfd.txt)
の仕様で定義しています。

<!--
When you first create a bitmap strike (with [Element->Bitmaps
Available](../elementmenu/#Bitmap+Strikes+Available...)) it will 
have no properties associated with it. If you then generate a bdf file
based on that FontForge will give you some default properties.
-->
最初にビットマップストライクを
([<span class="command">エレメント(L)->使用するビットマップ(B)</span>](../elementmenu/#使用するビットマップa-bitmap-strikes-available) で)
作成した時点では、
それに伴う属性は全く定義されていません。
その後、BDF ファイルを生成した時に、FontForge はいくつかのデフォルト属性を呈示します。

<!--
You may view these default properties in this dialog by pressing the
`[Default All]` button -- this will remove any current properties
(except for `RESOLUTION_Y`) and replace them with the defaults that
FontForge calculates).
-->
このダイアログに含まれるそれらのデフォルト属性値は、
このダイアログで
<span class="command">すべてデフォルトに</span>
ボタンを押すことによって見ることができます
-- これは現在の属性値を
(`RESOLUTION_Y` を除いて)
すべて削除し、
FontForge が算出したデフォルト値に置き換えます。

<!--
You may select any property and press the `[Default This]` button to
find its default value (There are some properties that FontForge cannot
default, you'll have to figure these out yourself).
-->
任意の属性を選択して、
<span class="command">この項目をデフォルトに</span>
を押すことによって、その項目のデフォルト値を知ることができます
(FontForge がデフォルトを設定することができない属性がいくつかあるので、
それらの値については自分で見つけ出す必要があります。

<!--
You may use the `[Delete]` button to remove a property.
-->
属性を削除するのには
<span class="command">削除</span>
ボタンが使えます。

<!--
You may use the up and down arrows buttons to move the selected property
up or down in the list (as far as I know, there is no functional reason
for doing this, but if your esthetics prefer a different ordering you
may enforce it).
-->
上矢印キーと下矢印キーを使って選択した属性をリスト内で上下に動かすことができます
(私の知るかぎりでは、これを行う機能上の理由は存在しませんが、
あなたの美的感覚で異なる順序づけを好む場合、
それを強制することができます)。

<!--
To change a property name depress the mouse on it. You should get a list
of all standard properties. At the bottom of the property list is a
special line labeled "New...", clicking on it brings up the same popup
menu and allows you to create a new property.
-->
属性名を変更する場合、名前の上でマウスを押してください。
標準属性の全リストが表示されるはずです。
属性リストの一番下には "新規..." という特殊なラベルを含む行があります。
それをクリックすると同じポップアップメニューが起動し、新しい属性名を作成することができます。

<!--
To change the value of a property, click in the value field and type in
the new version.
-->
属性値を変更する場合、値フィールドをクリックして、新しい値を入力してください。

<!--
To select a property without bringing up the popup menu or the editing
field, click on the extreme left of the property.
-->
ポップアップメニューや編集フィールドを起動しないで属性を選択したい場合、
属性の一番左の部分をクリックしてください。

<!--
The one essential property that FontForge can't always guess correctly
is the resolution (in particular `RESOLUTION_Y`). When you press
`[Default All]` FontForge will retain the current value of this property
and base the others on it.
-->
FontForge が常に推測できない本質的な属性の一つに解像度
(特に `RESOLUTION_Y`) があります。
<span class="command">すべてデフォルトに</span>
を押した時、
FontForge はこの属性の現在の値を保持し、
それに基づいてその他の値を計算します。
