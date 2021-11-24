FROM openjdk:18-jdk-alpine
ENV CATALINA_HOME="/usr/local/tomcat"
ADD http://dlcdn.apache.org/tomcat/tomcat-9/v9.0.55/bin/apache-tomcat-9.0.55.tar.gz /tmp/
WORKDIR $CATALINA_HOME
RUN tar zxvf /tmp/apache-tomcat-*.tar.gz -C $CATALINA_HOME --strip-components 1 \
    && rm -rf /tmp/apache-tomcat-*.tar.gz \
    && chmod -R +x $CATALINA_HOME/bin/
#ADD /java-app-dir/hello-world-war-1.0.0 $CATALINA_HOME/webapps/
#    && cp -r /run-app-07/hello-world-war-1.0.0 $CATALINA_HOME/webapps/
EXPOSE 8080
CMD $CATALINA_HOME/bin/catalina.sh run

