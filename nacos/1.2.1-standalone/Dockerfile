FROM jnoee/alpine-jre:8

ENV WORK_PATH /home/apps
ENV NACOS_FILE nacos-server-1.2.1.tar.gz

EXPOSE 8848

WORKDIR $WORK_PATH

RUN wget https://obs.cn-south-1.myhuaweicloud.com/report/${NACOS_FILE} && \
tar xvf ${NACOS_FILE} && rm -f ${NACOS_FILE}

ENTRYPOINT ["${WORK_PATH}/nacos/bin/startup.sh"]
CMD ["-m","standalone"]