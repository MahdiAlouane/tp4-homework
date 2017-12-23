FROM openjdk:8-jdk-alpine
VOLUME /tmp
EXPOSE 8080
ADD /target/product-service-0.0.1-SNAPSHOT.jar //
CMD sleep 120  && \
	java -Dfile.encoding=UTF-8 -Djava.security.egd=file:/dev/./urandom -jar /product-service-0.0.1-SNAPSHOT.jar