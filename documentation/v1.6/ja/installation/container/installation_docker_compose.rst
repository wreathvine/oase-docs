==============
Docker Compose
==============

| Docker Compose を利用した Docker 版 Exastro OASE の導入方法について説明します。
| 冗長構成には非対応のため、それらを必要とする場合、 :doc:`installation_kubernetes` 環境での利用を推奨します。
| 非コンテナ環境における導入の場合には、:doc:`../installer/installation_online` か :doc:`../installer/installation_offline` を参照して下さい。


前提条件
========
* Docker 環境が必要となります。
* Docker Compose が必要となります。
* git コマンドが必要となります。

コンテナ起動
============

資材の取得
----------

| Git コマンドを利用して Docker Compose での起動に必要な資材を取得します。

.. code-block:: bash

   git clone https://github.com/exastro-suite/oase-container.git

Docker Compose を使ったコンテナ起動
-----------------------------------

| docker-compose を利用して Exastro OASE コンテナを起動します。

.. code-block:: bash

    cd oase-container
    docker-compose up -d oase


接続確認
========

.. include:: ../../include/confirm_login.rst


環境情報
========

環境変数
--------

.. csv-table::
   :header: 設定名, 初期値, 説明
   :widths: 16,     25,   25

      DB_ROOT_PASSWORD, Ch@ngeMe, MariaDB の root パスワードを指定します。
      DB_HOST, mariadb, Exastro OASE が利用する MariaDB のFQDN(IPアドレス)を指定します。
      DB_PORT, 3306, Exastro OASE が利用する MariaDB の接続ポートを指定します。
      DB_DATABASE, OASE_DB, Exastro OASE が利用する MariaDB のデータベース名を指定します。
      DB_USER, OASE_USER, Exastro OASE が利用する MariaDB のユーザ名を指定します。
      DB_PASSWORD, Ch@ngeMe, Exastro OASE が利用する MariaDB のユーザのパスワードを指定します。
      BUSINESS_CENTRAL_ENDPOINT, central:8080, Exastro OASE が利用する Business Central のエンドポイント+ポート番号を指定します。
      KIE_SERVER_ENDPOINT, server:8080, Exastro OASE が利用する KIE サーバのエンドポイント+ポート番号を指定します。
      JBOSS_USER, admin, Exastro OASE が利用する Business Central のユーザ名を指定します。
      JBOSS_PASSWORD, admin, Exastro OASE が利用する Business Central のユーザのパスワードを指定します。
      MQ_HOST, rabbitmq, Exastro OASE が利用する RabbitMQ のをFQDN(IPアドレス)を指定します。
      MQ_USER, admin, Exastro OASE が利用する RabbitMQ のユーザ名を指定します。
      MQ_PASSWORD, Ch@ngeMe, Exastro OASE が利用する RabbitMQ のユーザのパスワードを指定します。
      MAIL_SMTP, {}, Exastro OASE が連携するメールサーバの情報を設定します。
      INTERVAL_TIME_<ANY>, 10, バックヤード系処理の処理間隔
      RABBITMQ_DEFAULT_USER, admin, RabbitMQ のユーザ名を設定します。
      RABBITMQ_DEFAULT_PASS, Ch@ngeMe, RabbitMQ のユーザのパスワードを設定します。
      MARIADB_ROOT_PASSWORD, Ch@ngeMe, MariaDB の root パスワードを設定します。
      MARIADB_DATABASE, OASE_DB, データベースの名前を設定します。
      MARIADB_USER, OASE_USER, データベースに接続するユーザ名を設定します。
      MARIADB_PASSWORD, Ch@ngeMe, データベースに接続するユーザのパスワードを設定します。
      MARIADB_ROOT_HOST, "%", MariaDB に root ログイン可能なホストを設定します。
      KIE_SERVER_LOCATION, http://kie-server:8080/kie-server/services/rest/server, KIE サーバのエンドポイントを指定します。
      KIE_SERVER_CONTROLLER, http://business-central:8080/business-central/rest/controller, KIE サーバコントローラのエンドポイントを指定します。
      KIE_MAVEN_REPO, http://business-central:8080/business-central/maven2, Maven リポジトリのエンドポイントを指定します。

コンフィグファイル設定
----------------------

なし

