FROM alpine:3.11

# 设置编码
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:UTF-8

# 设置阿里镜像
RUN echo http://mirrors.aliyun.com/alpine/v3.11/main/ > /etc/apk/repositories
RUN apk update && apk upgrade

# 设置时区
RUN apk --update add tzdata && \
    cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo "Asia/Shanghai" > /etc/timezone && \
    apk del tzdata