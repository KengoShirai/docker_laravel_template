# 初期化

- コンテナ側からホスト側へファイルやディレクトリをコピー
  - docker exec -it <appコンテナ名> /bin/bash
  - docker cp <コンテナID>:/usr/local/etc/php/php.ini-production ./config/php/php.ini（コピー済み）
  - docker cp <コンテナID>:/etc/apache2/sites-enabled/000-default.conf ./config/php/000-default.conf（コピー済み）
    - DocumentRootを各環境に合わせる

- my.cnfを作成
  - touch ./config/mysql/my.cnf（作成済み）

- Laravelプロジェクトを作成
  - docker exec -it <appコンテナ名> /bin/bash
  - cd /var/www/html/
  - composer create-project --prefer-dist laravel/laravel <プロジェクト名> "<バージョン>.*"

- database.phpを修正
  - my.cnfと文字コードを合わせる 
