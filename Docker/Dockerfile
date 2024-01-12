FROM mariadb:lts AS db-base

# ポート開放
EXPOSE 3306

# my.cnfのコピー
COPY ./my.cnf /etc/mysql/conf.d/my.cnf

# 権限の付与
RUN chmod 644 /etc/mysql/conf.d/my.cnf

# 共通の環境変数を設定
ENV MARIADB_ROOT_PASSWORD=12345


FROM db-base AS db-dev

# 開発環境用の環境変数
ENV MARIADB_DATABASE=FriedShrimp



FROM phpmyadmin:latest AS pma

# ポート開放
EXPOSE 80

# 環境変数の設定
ENV PMA_HOST=db
ENV PMA_USER=root
ENV PMA_PASSWORD=12345