# ベースイメージの指定
FROM ubuntu:20.04

# PHPのインストール
RUN apt update                                       && \
  apt install -y software-properties-common        && \
  LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php && \
  apt update                                       && \
  apt install -y php8.0 php8.0-mysql

# PHP の設定ファイルを追加
COPY ./docker/app/mail.ini /etc/php/8.0/cli/conf.d/mail.ini

RUN apt install -yqq msmtp msmtp-mta

COPY ./docker/app/mailrc /etc/msmtprc

RUN apt install -y curl iputils-ping procps vim tree