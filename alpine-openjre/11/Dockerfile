FROM jnoee/alpine:3.11 as jre

RUN apk --no-cache add openjdk11-jdk openjdk11-jmods; \
	/usr/lib/jvm/java-11-openjdk/bin/jlink --no-header-files --no-man-pages --compress=0 --strip-debug \
    --add-modules java.base,java.logging,jdk.unsupported \
    --output /opt/openjdk/jre;

FROM jnoee/alpine:3.11

COPY --from=jre /opt/openjdk/jre /opt/openjdk/jre

ENV JAVA_HOME=/opt/openjdk/jre \
    PATH="/opt/openjdk/jre/lib:/opt/openjdk/jre/bin:$PATH"

CMD ["/bin/bash"]