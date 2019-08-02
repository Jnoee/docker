FROM jnoee/centos:7.6

ENV JAVA_DIR /usr/java
ENV JAVA_NAME jdk1.8.0_144
ENV JAVA_HOME ${JAVA_DIR}/${JAVA_NAME}
ENV JAVA_FILE jdk-8u144-linux-x64.tar.gz
ENV PATH  ${PATH}:${JAVA_HOME}/bin

ADD ${JAVA_FILE} ${JAVA_DIR}

CMD ["/bin/bash"]