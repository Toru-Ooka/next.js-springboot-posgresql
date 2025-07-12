FROM postgres:15-alpine

ENV POSTGRES_DB=backend_db
ENV POSTGRES_USER=backend_user
ENV POSTGRES_PASSWORD=backend_password

COPY init.sql /docker-entrypoint-initdb.d/

EXPOSE 5432