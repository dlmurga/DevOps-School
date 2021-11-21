FROM ubuntu:20.04
ENV TOMCAT_HOME="/usr/local/tomcat"
ENV PACKAGE_DIR="/package"
RUN apt update \
    && apt install default-jdk -y \
    && apt install wget -y \
    && useradd -m -d $TOMCAT_HOME -U -s /bin/false tomcat \
    && cd $TOMCAT_HOME \
    && wget http://dlcdn.apache.org/tomcat/tomcat-9/v9.0.55/bin/apache-tomcat-9.0.55.tar.gz \
    && tar zxvf apache-tomcat-*.tar.gz -C $TOMCAT_HOME --strip-components 1 \
    && rm -rf apache-tomcat-*.tar.gz \
    && chown -R tomcat:tomcat $TOMCAT_HOME \
    && chmod -R u+x $TOMCAT_HOME/bin
WORKDIR /
RUN apt install maven -y \
    && mkdir $PACKAGE_DIR \
    && cd $PACKAGE_DIR \
    && git clone https://github.com/efsavage/hello-world-war.git \
    && cd $PACKAGE_DIR/hello-world-war \
    && mvn package \
    && cp -r $PACKAGE_DIR/hello-world-war/target/hello-world-war-1.0.0 $TOMCAT_HOME/webapps/
EXPOSE 8080
CMD $TOMCAT_HOME/bin/catalina.sh run