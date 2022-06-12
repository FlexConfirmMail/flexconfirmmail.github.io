========
開発情報
========

このページではFlexConfirmMailの技術情報と最新の開発動向についてまとめています。

* FlexConfirmMailのソースコードは `FlexConfirmMail/Outlook <https://github.com/FlexConfirmMail/Outlook>`_ で公開しています。
* バグ報告などは `GitHub Issues <https://github.com/FlexConfirmMail/Outlook/issues>`_ で受け付けています。
* FlexConfirmMailの一般的な使い方は :any:`quickstart` を参照ください。

開発履歴
========

2022年6月12日 :any:`quickstart` を更新しました。
  * 「インストール後の流れ」などの節を追加しました。
  * 全体的にスクリーンショットを増補しました。

2022年4月13日 FlexConfirmMail v22.0を公開しました。
  * 多国語（英語・中国語）に対応しました。
  * 社内ドメインのみの場合は確認をスキップできるようにしました。
  * UIツールキットをWPFに移行し、新しい設定画面を追加しました。

技術解説
========

1. FlexConfirmMailの基本的な仕組み
----------------------------------

1.1. Officeアドインとは
+++++++++++++++++++++++

Officeのアドインは一連の「イベント」から成り立っています。
イベントとは、例えばドキュメントの表示・保存・削除といった主な処理の節目のことで、
アドイン開発者はそれぞれのイベントに対して任意の処理を挟むことができます。

例えば、Outlookであれば次のようなイベントが定義され、独自の処理を挟めるようになっています。

* Outlookの起動 ("Startup"イベント)
* 新しいメールの受信 ("NewMail"イベント)
* メールの表示 ("ItemLoad"イベント)
* メールの送信 ("ItemSend"イベント)
* ... などなど

この中でも、とくにFlexConfirmMailは「メールの送信」のイベントに処理を挟むアドインです。

1.2. 送信イベントに処理を挟む
+++++++++++++++++++++++++++++

OfficeのAPI仕様では、次のような関数を定義することで、メールの送信の途中で任意の処理を挟めるようになっています。

.. code::

   void ApplicationEvents_11_ItemSendEventHandler(object Item, out bool Cancel)
   {
      /* 任意の処理 */
   }

この関数は次の２つの引数をとります：

* 一番目の引数 `Item` は送信メールを表すオブジェクトです。
* 二番目の引数 `Cancel` は「送信をキャンセルするか否か？」を表す真偽値です。

ここで重要なのは二番目の引数の `Cancel` です。
FlexConfirmMailは一見複雑なアドオンに見えるのですが、ことOutlookの視点から見る限り、
FlexConfirmMailの役割は、この `Cancel` の値を `true` or `false` のどちらにセットするかという判定に尽きます
（具体的には、送信を実行する場合は `false` をセットし、中止する場合は `true` をセットします）。

次の図は、処理の流れをフローチャートで示したものです。
FlexConfirmMailのロジックが実は極めて単純であることが見て取れると思います [#f1]_

**図: FlexConfirmMailのフローチャート**

.. figure:: _static/Flowchart.svg
   :width: 600

この構成から導かれるポイントとして、FlexConfirmMailは実際のメールの送信処理を行わないという点があります。
あくまで送信を行うのはOutlookの役割なので、
メールが宛先に配送される流れ自体はFlexConfirmMailの利用の有無にかかわらずまったく同じです。

.. rubric:: 脚注

.. [#f1] もちろん「このロジックをどのように操作可能なUIとして表現するか？」は非常に難しいポイントで、
    様々に工夫をこらしている部分ではあるのですが、背後にある動作モデルそのものは記述の通り甚だ単純です。