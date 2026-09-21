# stackblaze runtime image: official proxysql image with the binary built from this fork.
ARG BASE_IMAGE=proxysql/proxysql:3.0.11
FROM ${BASE_IMAGE}
ARG GIT_VERSION=unknown
LABEL org.opencontainers.image.source="https://github.com/stackblaze/proxysql" \
      org.opencontainers.image.version="${GIT_VERSION}" \
      org.opencontainers.image.description="ProxySQL + stackblaze patches: PG timeout/application_name GUC tracking, set_query_lock_on_hostgroup=2 (stay on locked HG, no 9006), pgsql-read_after_write_ms"
COPY src/proxysql /usr/bin/proxysql
RUN chmod 0755 /usr/bin/proxysql && /usr/bin/proxysql --version
