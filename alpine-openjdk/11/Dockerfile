FROM jnoee/alpine:3.11

ENV JAVA_DIR="/usr/java/"
ENV JAVA_NAME="openjre"
ENV JAVA_HOME ${JAVA_DIR}/${JAVA_NAME}

ENV JDK_HOME="/usr/lib/jvm/default-jvm/"
ENV JDK_NAME="openjdk11"

ENV PATH ${PATH}:${JAVA_HOME}/bin

RUN apk add ${JDK_NAME} && \
${JDK_HOME}/bin/jlink --no-header-files --no-man-pages --compress=0 --strip-debug \
--add-modules java.base,java.logging,jdk.unsupported \
--output ${JAVA_HOME} && \
rm -rf ${JDK_HOME}

CMD ["/bin/bash"]