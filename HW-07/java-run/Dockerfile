FROM openjdk:18-jdk-alpine
ENV CATALINA_HOME="/usr/local/tomcat"
WORKDIR /tmp
ADD http://dlcdn.apache.org/tomcat/tomcat-9/v9.0.55/bin/apache-tomcat-9.0.55.tar.gz ./
RUN mkdir $CATALINA_HOME \
    && tar zxvf apache-tomcat-*.tar.gz -C $CATALINA_HOME --strip-components 1 \
    && rm -rf apache-tomcat-*.tar.gz \
    && chmod -R u+x $CATALINA_HOME/bin
EXPOSE 8080
CMD $TOMCAT_HOME/bin/catalina.sh run

