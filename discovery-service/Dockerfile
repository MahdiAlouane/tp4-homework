FROM openjdk:8-jdk-alpine
VOLUME /tmp
EXPOSE 8761
ADD /target/discovery-service-0.0.1-SNAPSHOT.jar //
CMD sleep 40  && \
	java -Dfile.encoding=UTF-8 -Djava.security.egd=file:/dev/./urandom -jar /discovery-service-0.0.1-SNAPSHOT.jar