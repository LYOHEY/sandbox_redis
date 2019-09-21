FROM mariadb:10.3
COPY ./my.cnf /etc/mysql/conf.d/

RUN apt-get update \
    && apt-get install -y locales \
    && locale-gen ja_JP.UTF-8 \
    && echo "export LANG=ja_JP.UTF-8" >> ~/.bashrc
