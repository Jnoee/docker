FROM jnoee/alpine:3.11

ENV JAVA_REPO https://obs.cn-south-1.myhuaweicloud.com/report
ENV JAVA_DIR /usr/java
ENV JAVA_NAME jdk1.8.0_241
ENV JAVA_HOME ${JAVA_DIR}/${JAVA_NAME}
ENV JAVA_FILE server-jre-8u241-linux-x64.tar.gz
ENV PATH ${PATH}:${JAVA_HOME}/bin

ENV LIB_REPO https://obs.cn-south-1.myhuaweicloud.com/report
EVN GLIBC_FILE glibc-2.31-r0.apk
ENV GLIBC_BIN_FILE glibc-bin-2.31-r0.apk
ENV GLIBC_I18_FILE glibc-i18n-2.31-r0.apk

COPY ./locale.md /locale.md
RUN cat locale.md | xargs -i /usr/glibc-compat/bin/localedef -i {} -f UTF-8 {}.UTF-8  && \
apk --no-cache add bash ca-certificates wget && \
wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub && \
wget ${LIB_REPO}/${GLIBC_FILE} && wget ${LIB_REPO}/${GLIBC_BIN_FILE} && wget ${LIB_REPO}/${GLIBC_I18_FILE} && \
apk add ${GLIBC_FILE} ${GLIBC_BIN_FILE} ${GLIBC_I18_FILE} && \
rm -rf *.apk && \
rm -rf /var/cache/apk/* && \
wget ${JAVA_REPO}/${JAVA_FILE} && \
tar xvf ${JAVA_FILE} && mkdir ${JAVA_DIR} && mv ${JAVA_NAME} ${JAVA_DIR}/. && rm -f ${JAVA_FILE}

CMD ["/bin/bash"]