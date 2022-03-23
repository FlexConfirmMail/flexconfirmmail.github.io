============
よくある質問
============

一般的な質問
============

ソフトウェアの構成を教えて下さい
--------------------------------

FlexConfirmMail for Outlookは以下のファイルから構成されています。

.. list-table::
   :widths: 10 5
   :header-rows: 1

   * - ファイル
     - 説明
   * - FlexConfirmMail.dll
     - FlexConfirmMail本体
   * - FlexConfirmMail.dll.manifest
     - マニフェスト
   * - FlexConfirmMail.vsto
     - VSTOアドオン
   * - fcm.ico
     - アイコンファイル
   * - unins000.exe
     - アンインストーラ
   * - unins000.dat
     - アンインストーラ
   * - Microsoft.Office.Tools.Common.v4.0.Utilities.dll
     - VSTOライブラリ
   * - Microsoft.Office.Tools.Outlook.v4.0.Utilities.dll
     - VSTOライブラリ

管理者向け
==========

サイレントインストールするには
------------------------------

FlexConfirmMailをサイレントインストールしたい場合は、
`/SILENT` オプションを利用します::

    % FlexConfirmMailSetup.exe /SILENT

アドオンが自動的に無効化されるのを防止したい
--------------------------------------------

Office 2013以降にはパフォーマンスを自動的に最適化する機能が組み込まれています。

FlexConfirmMailが最適化機能で無効化されるのを防ぐには、
グループポリシーで設定を追加します。

- グループポリシーエディタを開、「ユーザーの構成」を開く。
- 「管理用テンプレート > Microsoft Outlook 2016 > その他」を順番に選択する。
- 「管理対象アドオンの一覧」の項目をダブルクリックする。
- 設定を「有効」にした上で、オプション欄の「表示」ボタンをクリックする。
- 値の名前に ``FlexConfirmMail`` と入力し、値を ``1`` に設定する。
- 「OK」ボタンを押下して確定する。

詳細は `Microsoft公式ドキュメント`_ を参照ください。

.. _Microsoft公式ドキュメント: https://docs.microsoft.com/ja-jp/office/vba/outlook/Concepts/Getting-Started/support-for-keeping-add-ins-enabled
