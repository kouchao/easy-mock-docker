FROM node:8.16.2-alpine

ENV EASY_MOCK_VERSION 1.6.0

WORKDIR /usr/src

ARG source=https://github.com/easy-mock/easy-mock/archive/v${EASY_MOCK_VERSION}.tar.gz

RUN wget -c ${source} -O easy-mock.tar.gz && \
    tar -zxvf easy-mock.tar.gz && \
    mv easy-mock-${EASY_MOCK_VERSION} easy-mock && \
    cd easy-mock && \
    npm i --registry https://registry.npm.taobao.org

ADD ./default.json /usr/src/easy-mock/config/default.json

EXPOSE 7300

CMD cd easy-mock && npm run dev