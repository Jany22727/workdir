FROM ruby:2.6-alpine

RUN apk add --update \
    build-base \
    mariadb-dev \
    sqlite-dev \
    nodejs \
    tzdata \ 
    &&  rm -rf /var/cache/apk/*

COPY ./tiger_test.tar .
RUN tar -xvf tiger_test.tar

WORKDIR tiger_test
RUN gem update --system \ 
    && gem install rails -v "5.0"  \
    && gem install bundler  \
    && bundle instal
CMD ["rails", "server", "-b", "0.0.0.0", "-p", "3100"]

