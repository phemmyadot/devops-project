FROM mysql:8.0.33
LABEL "project"="devops-project"
LABEL "author"="Babafemi Adojutelegan"

ENV MYSQL_ROOT_PASSWORD="devopspass"
ENV MYSQL_DATABASE="accounts"

ADD db_backup.sql /docker-entrypoint-initdb.d/db_backup.sql