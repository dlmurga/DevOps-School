FROM ubuntu:20.04
ARG DEBIAN_FRONTEND=noninteractive
ENV PACKAGE_DIR="/package-07"
RUN apt update \
    && apt install default-jdk -y \
    && apt install maven -y \
    && apt install git -y \
    && rm -rf /var/lib/apt/lists/*
WORKDIR $PACKAGE_DIR
RUN git clone http://github.com/efsavage/hello-world-war.git
RUN mvn package -f $PACKAGE_DIR/hello-world-war/pom.xml
RUN cp -r $PACKAGE_DIR/hello-world-war/target/ /build-app-07

ENV CATALINA_HOME="/usr/local/tomcat"
ADD http://dlcdn.apache.org/tomcat/tomcat-9/v9.0.55/bin/apache-tomcat-9.0.55.tar.gz /tmp/
WORKDIR $CATALINA_HOME
RUN tar zxvf /tmp/apache-tomcat-*.tar.gz -C $CATALINA_HOME --strip-components 1 \
    && rm -rf /tmp/apache-tomcat-*.tar.gz \
    && chmod -R +x $CATALINA_HOME/bin/ \
    && cp -r $PACKAGE_DIR/hello-world-war/target/hello-world-war-1.0.0 $TOMCAT_HOME/webapps/
EXPOSE 8080
CMD $CATALINA_HOME/bin/catalina.sh run
