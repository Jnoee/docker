FROM alpine:3.11

# 设置编码
ENV LANG="zh_CN.UTF-8" LC_ALL="zh_CN.UTF-8"

# 设置清华镜像
RUN set -eux && \
	sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories

# 设置时区
RUN apk --update add tzdata && \
    cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo "Asia/Shanghai" > /etc/timezone && \
    apk del tzdata