FROM jnoee/alpine:3.11

ENV JAVA_DIR /usr/java
ENV JAVA_NAME jdk1.8.0_241
ENV JAVA_HOME ${JAVA_DIR}/${JAVA_NAME}
ENV JAVA_FILE server-jre-8u241-linux-x64.tar.gz
ENV PATH ${PATH}:${JAVA_HOME}/bin
ENV GLIBC_FILE glibc-2.31-r0.apk

RUN apk --no-cache add bash ca-certificates wget && \
wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub && \
wget https://obs.cn-south-1.myhuaweicloud.com/report/${GLIBC_FILE} && \
apk add ${GLIBC_FILE} && \
rm -rf *.apk && \
rm -rf /var/cache/apk/* \
wget https://obs.cn-south-1.myhuaweicloud.com/report/${JAVA_FILE} && \
tar xvf ${JAVA_FILE} && mkdir ${JAVA_DIR} && mv ${JAVA_NAME} ${JAVA_DIR}/. && rm -f ${JAVA_FILE}

CMD ["/bin/bash"]