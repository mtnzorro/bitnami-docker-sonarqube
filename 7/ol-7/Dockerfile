FROM bitnami/oraclelinux-extras:7-r200
LABEL maintainer "Bitnami <containers@bitnami.com>"

# Install required system packages and dependencies
RUN install_packages glib2 glibc keyutils-libs krb5-libs libblkid libcom_err libffi libgcc libmount libselinux libstdc++ libuuid libxml2 libxslt ncurses-libs nss-softokn-freebl openssl-libs pcre readline xz-libs zlib
RUN bitnami-pkg unpack postgresql-client-10.6.0-20 --checksum 34531f23cac0fdda367b49d58af800496dd7e2c1ffc03fbae0230c8daba6332f
RUN bitnami-pkg install java-1.8.191-20 --checksum 385a62502dbd62180858f6d4f6afde334dad9862e0caab022c2327b467d1283d
RUN bitnami-pkg unpack sonarqube-7.4.0-20 --checksum 7754bdb94591aec02e51f88d810ac40cf3e4970063541ef8a944395c3c91b9e3

COPY rootfs /
ENV BITNAMI_APP_NAME="sonarqube" \
    BITNAMI_IMAGE_VERSION="7.4.0-ol-7-r38" \
    PATH="/opt/bitnami/postgresql/bin:/opt/bitnami/java/bin:/opt/bitnami/sonarqube/bin/linux-x86-64/:$PATH" \
    POSTGRESQL_CLIENT_CREATE_DATABASE_NAME="" \
    POSTGRESQL_CLIENT_CREATE_DATABASE_PASSWORD="" \
    POSTGRESQL_CLIENT_CREATE_DATABASE_USERNAME="" \
    POSTGRESQL_HOST="postgresql" \
    POSTGRESQL_PORT_NUMBER="5432" \
    POSTGRESQL_ROOT_PASSWORD="" \
    POSTGRESQL_ROOT_USER="postgres" \
    SMTP_HOST="" \
    SMTP_PASSWORD="" \
    SMTP_PORT="" \
    SMTP_PROTOCOL="" \
    SMTP_USER="" \
    SONARQUBE_DATABASE_NAME="bitnami_sonarqube" \
    SONARQUBE_DATABASE_PASSWORD="" \
    SONARQUBE_DATABASE_USER="bn_sonarqube" \
    SONARQUBE_ELASTICSEARCH_PORT_NUMBER="" \
    SONARQUBE_ENABLE_DEMO_DATA="no" \
    SONARQUBE_JAVA_OPTS="" \
    SONARQUBE_PASSWORD="bitnami" \
    SONARQUBE_PORT_NUMBER="" \
    SONARQUBE_USERNAME="admin"

EXPOSE 9000

ENTRYPOINT [ "/app-entrypoint.sh" ]
CMD [ "nami", "start", "--foreground", "sonarqube" ]
