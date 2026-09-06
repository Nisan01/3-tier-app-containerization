FROM mysql:8.0

LABEL maintainer="nishan-kiran-chauhan" \
      service="database" \
      description="MySQL Database customized with Auto-Initialization"

ENV MYSQL_ROOT_PASSWORD=root  \
    MYSQL_DATABASE=appdb


VOLUME [ "/var/lib/mysql" ]


COPY init.sql  /docker-entrypoint-initdb.d/


EXPOSE 3306


HEALTHCHECK --interval=10s --timeout=30s --start-period=30s --retries=5 \
            CMD mysqladmin ping -h localhost -u root -p${MYSQL_ROOT_PASSWORD} || exit 1