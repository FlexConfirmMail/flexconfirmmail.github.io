================
クイックスタート
================

このページでは、FlexConfirmMailをOutlookに導入する方法について解説します。

.. contents:: 目次
   :local:
   :backlinks: none

インストール
============

* 初期セットアップの流れを解説した動画 「`2分で始める誤送信対策 <https://www.youtube.com/watch?v=cBfAGb6Ub20>`_」も用意しています。
* 動画の方が分かりやすいという方は上のリンクからご覧ください。

FlexConfirmMailをインストールする
---------------------------------

.. list-table::
   :widths: 10 10

   * - 1. FlexConfirmMailの最新のEXEインストーラを :any:`download` から取得します。

     - .. figure:: _static/download.png
          :width: 95%

   * - 2. FlexConfirmMailSetup.exe を実行します。

     - .. figure:: _static/installer.png
          :width: 95%
 
   * - 3. ウィザード完了後、Outlookの「ホーム」にFlexConfirmMailが追加されていれば成功です。

     - .. figure:: _static/Ribbon.png
          :width: 95%

.. hint::

   * FlexConfirmMailを構成するファイルは :file:`C:\\Program Files\\FlexConfirmMail` に格納されます。
   * 詳しいファイルの一覧とそれぞれの説明は脚注 [#f1]_ に掲載しています。
   * 単一のインストールで32ビット・64ビットの両方のOutlookに対応しています。

インストール後の流れ
--------------------

.. list-table::
   :widths: 10 10

   * - 1. FlexConfirmMailは「送信」ボタンをクリックした際に有効になるアドオンです。

     - .. figure:: _static/SendButton.png
          :width: 95%

   * - 2. メールの送信時に右図（クリックで拡大）のような確認ダイアログが表示されるようになります。

     - .. figure:: _static/MainDialog.png
          :width: 95%

   * - 3. 宛先と添付ファイルにすべてチェックを入れると、カウントダウン後に実際に送信されます。

     - .. figure:: _static/CountDialog.png
          :width: 95%

   * - 4. この一連の挙動はカスタマイズ可能です。詳しくは次章の「設定とカスタマイズ」を参照ください。

     - 
 
設定とカスタマイズ
==================

社内ドメインを設定する
----------------------

.. list-table::
   :widths: 10 10

   * - 1. FlexConfirmMailは宛先を社内・社外で分けて確認する機能を備えてます。

     - .. figure:: _static/TrustedDomainsExample.png
          :width: 95%

   * - 2. 「FlexConfirmMail設定 > 社内ドメイン」を選択し、自分の会社のドメインを記入します。

          例えば右の例では「clear-code.com」を社内ドメインとして登録しています。

     - .. figure:: _static/TrustedDomains.png
          :width: 95%

   * - 3. 「設定を保存して終了」を押下すれば完了です。

     -

.. versionadded:: 22.0

   基本設定の「宛先が社内ドメインのみの場合は確認をスキップする」にチェックを入れると、
   社内の宛先のみのメールは、確認ダイアログを表示せずに送信できます。

   .. figure:: _static/SkipIfNoExt.png
      :align: left
      :width: 300


注意が必要なドメインを設定する
------------------------------

.. list-table::
   :widths: 10 10

   * - 1. FlexConfirmMailは注意が必要な宛先を検出する機能を備えています。

     - .. figure:: _static/UnsafeDomainsExample.png
          :width: 95%

   * - 2. 「FlexConfirmMail設定 > 注意が必要なドメイン」を選択し、ドメインを記入します。

          例えば「gmai.com」などのドメインの打ち間違え対策に利用できます。

     - .. figure:: _static/UnsafeDomains.png
          :width: 95%

   * - 3. 「設定を保存して終了」を押下すれば完了です。

     -

注意が必要なファイル名を設定する
--------------------------------

.. list-table::
   :widths: 10 10

   * - 1. FlexConfirmMailは、注意が必要な添付ファイルを検出して、警告を促す機能を備えています。

     - .. figure:: _static/UnsafeFilesExample.png
          :width: 95%

   * - 2. 「FlexConfirmMail設定 > 注意が必要なファイル名」を選択し、キーワードを設定します。

          例えば「社外秘」など、機密性の高いファイルによく付与するワードを設定ください。

     - .. figure:: _static/UnsafeFiles.png
          :width: 95%

   * - 3. 「設定を保存して終了」を押下すれば完了です。

     -

運用に関するヒント
==================

インストーラをサイレント実行する
--------------------------------

組織の端末に配布する時などに、FlexConfirmMailをサイレントインストールしたい場合は、
次のように/SILENTオプションを利用します::

    % FlexConfirmMailSetup.exe /SILENT

アドオンが自動的に無効化されるのを防止する
------------------------------------------

Office 2013以降にはパフォーマンスを自動的に最適化する機能が組み込まれており、
`その一環としてアドオンを自動的に無効化することがあります。 <https://docs.microsoft.com/en-US/office/vba/outlook/Concepts/Getting-Started/support-for-keeping-add-ins-enabled>`_

FlexConfirmMailが自動的に無効化されるのを防止するには、
グループポリシーで下記の設定を追加ください。

1. グループポリシーエディタを開き、「ユーザーの構成」を開く。

2. 「管理用テンプレート > Microsoft Outlook 2016 > その他」を順番に選択する。

3. 「管理対象アドオンの一覧」の項目をダブルクリックする。

4. 設定を「有効」にした上で、オプション欄の「表示」ボタンをクリックする。

5. 値の名前に FlexConfirmMail と入力し、値を 1 に設定する。

   .. figure:: _static/resiliency.png
      :width: 60%

6. 「OK」ボタンを押下して確定する。

.. rubric:: 脚注

.. [#f1] FlexConfirmMailのインストーラを実行すると、プログラムフォルダ
   :file:`C:\\Program Files\\FlexConfirmMail` に以下のファイルが展開されます。
   
   .. list-table::
      :header-rows: 1
      :widths: 4 15
       
      * - ファイル
        - 説明
      * - FlexConfirmMail.dll
        - FlexConfirmMail本体
      * - {en,zh}/FlexConfirmMail.dll
        - 多言語対応リソース
      * - FlexConfirmMail.dll.manifest
        - FlexConfirmMailマニフェスト         
      * - FlexConfirmMail.vsto
        - Outlook向けのアドオン定義
      * - fcm.ico
        - アイコン画像
      * - unins000.exe
        - アンインストーラ
      * - unins000.dat
        - アンインストーラ
      * - Microsoft.Office.Tools.Common.v2.0.Utilities.dll
        - VSTOアドオンライブラリ
      * - Microsoft.Office.Tools.Outlook.v2.0.Utilities.dll
        - VSTOアドオンライブラリ
