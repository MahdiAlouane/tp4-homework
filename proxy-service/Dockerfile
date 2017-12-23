FROM openjdk:8-jdk-alpine
VOLUME /tmp
EXPOSE 9999
ADD /target/proxy-service-0.0.1-SNAPSHOT.jar //
CMD sleep 80  && \
	java -Dfile.encoding=UTF-8 -Djava.security.egd=file:/dev/./urandom -jar /proxy-service-0.0.1-SNAPSHOT.jar