================
クイックスタート
================

このページでは、FlexConfirmMailをOutlookに導入する手順を解説します。

.. contents::
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

インストール後の流れ
--------------------

.. list-table::
   :widths: 10 10

   * - 1. FlexConfirmMailは「送信」ボタンをクリックした際に有効になるアドインです。

     - .. figure:: _static/SendButton.png
          :width: 95%

   * - 2. メールの送信時に右図（クリックで拡大）のような確認ダイアログが表示されるようになります。

     - .. figure:: _static/MainDialog.png
          :width: 95%

   * - 3. 宛先と添付ファイルにすべてチェックを入れると、カウントダウン後に実際に送信されます。

     - .. figure:: _static/CountDialog.png
          :width: 95%

   * - 4. この一連の挙動はカスタマイズ可能です。

          次の「設定とカスタマイズ」で基本的なセットアップを解説します。

     - 
 
設定とカスタマイズ
==================

社内ドメインを設定する
----------------------

.. list-table::
   :widths: 10 10

   * - 1. FlexConfirmMailは宛先を社内・社外で分けて確認する機能を備えてます。

          この区別は「社内ドメイン」設定に基づきます。

     - .. figure:: _static/TrustedDomainsExample.png
          :width: 95%

   * - 2. 「FlexConfirmMail設定 > 社内ドメイン」を選択し、自分の会社のドメインを記入します。

          例えば右の例では「clear-code.com」を社内ドメインとして登録しています。

     - .. figure:: _static/TrustedDomains.png
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

記事のまとめ
============

ここまでの手順で達成できたこと
------------------------------

これで最初の導入手順は完了です。ここまでの手順で、次の3点が達成できました。

* 誤送信対策アドインFlexConfirmMailをOutlookに導入することができました。
* 基本的な設定が完了し、社内・外部の宛先ごとにチェックできるようになりました。
* 注意が必要な添付ファイルを送信時に自動検出できるようになりました。

既に基本的なセットアップは完了していますので、後は好みに応じて動作をカスタマイズください。

具体的なカスタマイズの手順については、次の各リンク先にまとまっています。

ここからどこへ？
----------------

* FlexConfirmMailのよくある設定と運用タスクは :any:`howto` にまとまっています。
* リリースサイクルなどのプロジェクト全体に関する情報は :any:`support` にまとまっています。
