===========
IP ブロック
===========

| IP ブロックは、パスワードの認証の失敗によりアクセス元の IP アドレスからの接続を制限する機能です。
| IP ブロックされた接続元は、ブロックされている IP アドレスとは別の IP アドレスからシステム管理者(Administrator)、もしくは、メール通知先ログインIDに登録されているユーザにより登録を解除することが可能です。

.. tip:: 接続元の IP アドレスの安全性が確認できている場合、事前にホワイトリストに登録しておくことを推奨します。


IP ブロックの設定
====================

| IP ブロックに関連する設定ついては、システム設定の :doc:`../system/password` の下記の項目を参考にして下さい。

同一IP連続ログイン試行上限
  | 同一IPアドレスから連続でログインに失敗した回数が閾値を超えた場合、アクセス元のIPアドレスをブラックリストに登録します。

| 例えば、同一IP連続ログイン試行上限が 5 (回)と設定されていた場合、5 回連続でパスワードの認証に失敗したタイミングで接続元の IP アドレスからの接続がブロックされます。


ホワイトリスト
==============

| ホワイトリストに IP アドレスを登録することで、 **同一IP連続ログイン試行上限** を超えてログインに失敗した場合にも、ブロックされることなく Exastro OASE にアクセスできます。

| ホワイトリスト画面では、Exastro OASE を利用して作業を行う上で共通に必要となる以下の機能を提供します。

* ホワイトリストの登録、更新、無効


前提条件
--------

| ホワイトリストの操作には、下記の条件を満たしている必要があります。

* ホワイトリストの操作を行うユーザは、システム管理者(Administrator)、もしくは、メール通知先ログインIDであること。

.. tip::
   | メール通知先ログインID は、:doc:`../system/password` の :menuselection:`メール通知先ログインID` を参照して下さい。

.. _whitelist_manual:

操作手順
--------

| 画面上部のメニューから :menuselection:`管理 --> ホワイトリスト` を開きホワイトリストを一覧で表示します。

.. figure:: /images/ja/whitelist/disp_index.png
   :scale: 60%
   :align: center

   ホワイトリスト一覧画面

| :guilabel:` 編集` をクリックし、ホワイトリストの追加、更新もしくは無効の設定を行います。

.. figure:: /images/ja/whitelist/edit_index.png
   :scale: 60%
   :align: center

   ホワイトリスト編集画面

.. table:: ホワイトリスト編集画面機能

   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | 構成要素         | 説明                                                                                                                          |
   +==================+===============================================================================================================================+
   | キャンセル       | 変更内容を破棄してホワイトリスト編集画面を閉じ、ホワイトリスト画面に戻ります。                                                |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | リセット         | 値を変更する前のホワイトリスト編集画面に戻ります。                                                                            |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | 追加             | 編集欄が1行追加されます。                                                                                                     |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | 保存             | 変更内容を保存してホワイトリスト編集画面を閉じ、ホワイトリスト画面に戻ります。                                                |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | 更新             | :kbd:`更新` - 既存の設定を変更する際に選択します。                                                                            |
   +                  +                                                                                                                               +
   |                  | :kbd:`無効` - 既存の設定を無効にする際に選択します。                                                                          |
   +                  +                                                                                                                               +
   |                  | 選択状態で :guilabel:` 保存` を押下すると、選択した内容が反映されます。※新規追加行にはプルダウンメニューは表示されません。   |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | IPアドレス       | 入力必須項目です。ワイルドカードを使用できます。                                                                              |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | 最終更新者       | ホワイトリストの情報を更新したユーザの名前が表示されます。                                                                    |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | 登録日時         | ホワイトリストに登録された日時が表示されます。                                                                                |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | 追加行削除ボタン | ホワイトリスト編集画面の :guilabel:`追加ボタン` を押下した場合、欄内に押下可能な :guilabel:`` が表示されます。               |
   +                  +                                                                                                                               +
   |                  | :guilabel:`` を押下すると、追加行が削除されます。                                                                            |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+

| :guilabel:` 保存` をクリックし、設定内容を反映します。

ブラックリスト
==============

| **同一IP連続ログイン試行上限** を超えてログインに失敗した場合に、接続元の IP アドレスがブラックリストに登録され、Exastro OASE への接続がブロックされます。

| ブラックリスト画面では、Exastro OASE を利用して作業を行う上で共通に必要となる以下の機能を提供します。

* ブラックリストの登録、更新、無効
* ブラックリストの自動登録


前提条件
--------

| ブラックリストの操作には、下記の条件を満たしている必要があります。

* ブラックリストの操作を行うユーザは、システム管理者(Administrator)、もしくは、メール通知先ログインIDであること。

.. tip::
   | メール通知先ログインID は、:doc:`../system/password` の :program:`メール通知先ログインID` を参照して下さい。

操作手順
--------

| 画面上部のメニューから :menuselection:`管理 --> ブラックリスト` を開きブラックリストを一覧で表示します。

.. figure:: /images/ja/blacklist/disp_index.png
   :scale: 60%
   :align: center

   ブラックリスト一覧画面

| :guilabel:` 編集` をクリックし、ブラックリストの追加、更新もしくは無効の設定を行います。

.. figure:: /images/ja/blacklist/edit_index.png
   :scale: 60%
   :align: center

   ブラックリスト編集画面

.. table:: ブラックリスト編集画面機能

   +------------------+--------------------------------------------------------------------------------------------------------------------------------+
   | 構成要素         | 説明                                                                                                                           |
   +==================+================================================================================================================================+
   | キャンセル       | 変更内容を破棄してブラックリスト編集画面を閉じ、ブラックリスト画面に戻ります。                                                 |
   +------------------+--------------------------------------------------------------------------------------------------------------------------------+
   | リセット         | 値を変更する前のブラックリスト編集画面に戻ります。                                                                             |
   +------------------+--------------------------------------------------------------------------------------------------------------------------------+
   | 追加             | 編集欄が1行追加されます。                                                                                                      |
   +------------------+--------------------------------------------------------------------------------------------------------------------------------+
   | 保存             | 変更内容を保存してブラックリスト編集画面を閉じ、ブラックリスト画面に戻ります。                                                 |
   +------------------+--------------------------------------------------------------------------------------------------------------------------------+
   | 更新             | :kbd:`更新` - 既存の設定を変更する際に選択します。                                                                             |
   +                  +                                                                                                                                +
   |                  | :kbd:`無効` - 既存の設定を無効にする際に選択します。                                                                           |
   +                  +                                                                                                                                +
   |                  | 選択状態で :guilabel:` 保存` を押下すると、選択した内容が反映されます。※新規追加行にはプルダウンメニューは表示されません。    |
   +------------------+--------------------------------------------------------------------------------------------------------------------------------+
   | IPアドレス       | 入力必須項目です。ワイルドカードを使用できます。                                                                               |
   +------------------+--------------------------------------------------------------------------------------------------------------------------------+
   | 最終更新者       | ブラックリストの情報を更新したユーザの名前が表示されます。                                                                     |
   +------------------+--------------------------------------------------------------------------------------------------------------------------------+
   | 登録日時         | ブラックリストに登録された日時が表示されます。                                                                                 |
   +------------------+--------------------------------------------------------------------------------------------------------------------------------+
   | 追加行削除ボタン | ブラックリスト編集画面の :guilabel:`追加ボタン` を押下した場合、欄内に押下可能な :guilabel:`` が表示されます。                |
   +                  +                                                                                                                                +
   |                  | :guilabel:`` を押下すると、追加行が削除されます。                                                                             |
   +------------------+--------------------------------------------------------------------------------------------------------------------------------+

| :guilabel:` 保存` をクリックし、設定内容を反映します。


ブラックリストとホワイトリストの関係
====================================

| Exastro OASE ではブラックリストとホワイトリストに同じIPアドレスが登録されている場合、 **ホワイトリストが優先** されます。


IP ブロックによりログインできなくなってしまった場合
===================================================

.. include:: ../include/unblock_method.rst