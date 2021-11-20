FROM tomcat:9.0
LABEL maintainer="dl.murga@yandex.ru"
RUN apt update \
    && apt install git -y \
    && apt install maven -y
RUN mkdir /package \
    && cd /package \
    && git clone https://github.com/efsavage/hello-world-war.git \
    && cd /package/hello-world-war \
    && mvn package \
    && cp -r /package/hello-world-war/target/hello-world-war-1.0.0 /var/lib/tomcat9/webapps/
