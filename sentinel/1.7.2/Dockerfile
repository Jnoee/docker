FROM jnoee/alpine-jre:8

ENV WORK_PATH /home/apps
ENV SENTINEL_VERSION 1.7.2
ENV SENTINEL_FILE sentinel-dashboard-${SENTINEL_VERSION}.jar

ENV JAVA_SERVER_OPTS -Djava.security.egd=file:/dev/./urandom -server

EXPOSE 8080

WORKDIR $WORK_PATH

RUN wget https://github.com/alibaba/Sentinel/releases/download/${SENTINEL_VERSION}/${SENTINEL_FILE}

ENTRYPOINT java $JAVA_SERVER_OPTS $JAVA_OPTS -jar $SENTINEL_FILE