FROM postgres:14.5
COPY pg_hba.conf /usr/share/postgresql/14.5/
COPY postgresql.conf /usr/share/postgresql/14.5/
COPY  init-db.sql /docker-entrypoint-initdb.d/
ENV POSTGRES_USER gordonuser
ENV POSTGRES_DB ddev
ENV POSTGRES_PASSWORD gordonpass
