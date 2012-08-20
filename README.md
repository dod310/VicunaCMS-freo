# VicunaCMS-freo

[Vicuna CMS](http://vicuna.jp)のWordPress専用のテーマwp.Vicunaを、高機能CMS [freo](http://freo.jp)向けにカスタマイズしたものを公開しています。

## ライセンス

freoとwp.Vicunaのライセンスに順じます。

### freoのライセンス
> 配布しているプログラムは、個人・法人を問わず、自由に利用・複製・改変・再配布することができます。
> 各フッター部分に表示している著作権表記は、削除したければ削除可能です。
> プログラム内の著作権表示とライセンスの文章は削除できません。
> 再配布の際に対価を要求することもできますが、再配布物にはGPLを適用しなければなりません。
> <http://freo.jp/about/license.html>

### wp.Vicunaライセンス
> 利用するCMSのライセンスがコピーレフトである場合はCMSのライセンスに従い、そうでない場合はMITライセンスとして配布します。
> 個人・商用問わず利用が可能です。ビジネスサイトの構築や、wp.Vicunaを使用して第三者から有償でWEBサイトの構築を請け負うことができます。このライセンスはvicuna.jpで配布しているスキンにも適用されます。
> <http://wp.vicuna.jp/about/what/>

## ファイルのアップロード

ダウンロード後、templatesフォルダとcssフォルダを適用させるfreoのそれぞれのフォルダへアップロード、上書きして下さい。

## スキン、レイアウトの変更

スキンを変更する場合は、templates/internals/header.htmlの16行目

    {assign var='select_css' value='**style-future**'}

の**style-future**の部分を変更します。以下の5つを指定する事が出来ます。

* style-vega
* style-mono
* style-galaxy
* style-flat
* style-future

またtemplates/internals/header.htmlの17行目を

&lt;link rel="stylesheet" href="{$freo.core.http_url}{$smarty.const.FREO_CSS_DIR}{$select_css}import.css" type="text/css" media="all" /&gt;

と変更するとVicunaデフォルトのデザインに変更出来ます。

の中から適時、変更して下さい。templates/internals/header.htmlにも説明を記載してあります。

レイアウトを変更するには、templates/internals/header.htmlの27行目

    &lt;body class="{$select_css} {if $smarty.request.freo.mode == 'view'}individual {elseif $smarty.request.freo.mode == 'default' || $smarty.request.freo.mode == 'entry'}mainIndex {/if}{if $smarty.request.freo.mode == 'page'}single {if $smarty.get.id}individual{else}archives{/if}{else}double f900{/if}"&gt;

を変更します。

デフォルトでは、この行の最後の方でdouble f900と記入していますが、これにより

* double = ダブルカラム(右サイドバー)
* f900 = コンテンツ幅900px

にレイアウト指定してあります。

デフォルトではページはシングルカラムにしてありますが、シングル以外にする場合は、

    {if $smarty.request.freo.mode == 'page'}**single** 

の**single**の部分を**double**などに変更します。

また

    {if $smarty.request.freo.mode == 'page'}single {if $smarty.get.id}individual

の部分でページ表示の振り分けをしていますが、.htaccessの設定に因っては上手くいかないかも知れません。

デザイン、レイアウトの変更は以下を参考にして下さい。

* style-vega
* style-mono
* style-galaxy
* style-flat
* style-future

bodyのclass名付加部分のソースは使い易い様に改編なさる事をお薦めします。

## サンプル

* freoにVicuna CMSを適用させて実際に動かしている[サンプルページ](http://vc.metal-mad.com)

* [style-vega](http://vc.metal-mad.com/demo/style-vega/preview/index.html)
* [style-mono](http://vc.metal-mad.com/demo/style-mono/preview/index.html)
* [style-galaxy](http://vc.metal-mad.com/demo/style-galaxy/preview/index.html)
* [style-flat](http://vc.metal-mad.com/demo/style-flat/preview/index.html)
* [style-future](http://vc.metal-mad.com/demo/style-future/preview/index.html)

## 連絡先

* [Website](http://metal-mad.com)
* [Twitter](https://twitter.com/metalmadcom)