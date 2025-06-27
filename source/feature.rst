================
FlexConfirmMailの機能
================

このページでは、FlexConfirmMail for Outlookの機能と動作環境を紹介します。

.. contents::
   :local:
   :backlinks: none

機能紹介
============

* FlexConfirmMail for Outlookは、メール送信時起動します。確認が必要な項目を自動検出し、確認画面を表示し、送信者がすべての項目をチェックして初めて、メールを送信できます。



.. list-table::
   :widths: 5 10 10

   * - 宛先確認
     - To,Cc,Bccにある宛先の送信前チェックをするため、メールの送信時に右図（クリックで拡大）のような確認ダイアログが表示されるようになります。組織内として扱うドメインや、特に注意の必要なドメインなど
     - .. figure:: _static/MainDialog.png
          :width: 95%
   * - 添付ファイルチェック
     - 送信前の添付ファイルについて、特定の拡張子を持つファイルや、文字列を含むファイルなどに対しての警告表示が可能です。また添付ファイルの再確認のためファイル名の手動入力チェックが可能です。
     -
   * - メール送信前カウントダウン 
     - 送信ボタンを押してからあらかじめ設定した時間カウントダウン画面を表示し、カウントダウン後に実際に送信されます。
     - .. figure:: _static/CountDialog.png
          :width: 95%

   * - 会議通知連携
     - 会議の招待状を送信する際の宛先確認も可能です。
     - 

動作環境
==================

.. list-table::
   :widths: 10, 20

   * - 対応メールクライアント     
     - **Microsoft 365 Outlook（Outlook on the web）**
       **Microsoft Outlook for Windows（デスクトップアプリ）"**
        * 新しいOutlook       
        * クラシックOutlook（バージョン2024以降）                      
   * - 対応OS
     - Microsoft Windows10, 11
   * - 設定集中管理
     - 可能
   * - 対応言語
     - 日本語、英語
   * - その他要件
     - メールサーバーは以下のいずれかであること
        * Microsoft 365
        * Exchange Online


