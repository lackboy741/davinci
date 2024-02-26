FROM registry.cn-shenzhen.aliyuncs.com/umer_snapshot/jdk:8
MAINTAINER umer <delivery@umer.com.cn>
RUN cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo 'Asia/Shanghai'>/etc/timezone

RUN cd / \
	&& mkdir -p /opt/davinci/
COPY ./target/davinci-server_0.3.1-0.3.1-SNAPSHOT-spring-boot.jar /opt/davinci/davinci-server.jar 
COPY ./davinci-ui/ /opt/davinci/davinci-ui/ 
COPY ./config /opt/davinci/config/
COPY ./userfiles /opt/davinci/userfiles/

ENV DAVINCI3_HOME /opt/davinci
ENV OPENSSL_CONF=/etc/ssl/
EXPOSE 8080

WORKDIR /opt/davinci

ENTRYPOINT ["java","-jar","davinci-server.jar"]

