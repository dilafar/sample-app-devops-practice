FROM mysql:8.0.33
LABEL Author="Fadhil"

ENV MYSQL_ROOT_PASSWORD=admin123
ENV MYSQL_DATABASE=accounts

ADD db_backup.sql  docker-entrypoint-initdb.d/db_backup.sql
