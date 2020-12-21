FROM postgres:13.1

ARG DOCKER_ENV
ARG POSTGRES_USER_READER
ARG POSTGRES_PASSWORD_READER
ARG POSTGRES_USER_WRITER
ARG POSTGRES_PASSWORD_WRITER

COPY build/${DOCKER_ENV}/init.sql /docker-entrypoint-initdb.d/init.sql

RUN sed -i "s|user_reader|${POSTGRES_USER_READER}|g" /docker-entrypoint-initdb.d/init.sql
RUN sed -i "s|password_reader|${POSTGRES_PASSWORD_READER}|g" /docker-entrypoint-initdb.d/init.sql
RUN sed -i "s|user_writer|${POSTGRES_USER_WRITER}|g" /docker-entrypoint-initdb.d/init.sql
RUN sed -i "s|password_writer|${POSTGRES_PASSWORD_WRITER}|g" /docker-entrypoint-initdb.d/init.sql

CMD ["docker-entrypoint.sh", "postgres"]
