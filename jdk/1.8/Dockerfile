FROM jnoee/centos:7.6

ENV JAVA_DIR /usr/java
ENV JAVA_NAME jdk1.8.0_221
ENV JAVA_HOME ${JAVA_DIR}/${JAVA_NAME}
ENV JAVA_FILE jdk-8u221-linux-x64.tar.gz
ENV PATH  ${PATH}:${JAVA_HOME}/bin

RUN curl https://obs.cn-south-1.myhuaweicloud.com/report/${JAVA_FILE} -O && tar xvf ${JAVA_FILE} && mv ${JAVA_NAME} ${JAVA_DIR}/. && rm ${JAVA_FILE}

CMD ["/bin/bash"]