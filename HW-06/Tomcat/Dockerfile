FROM tomcat:9.0
LABEL maintainer="dl.murga@yandex.ru"
RUN apt update && apt install maven -y
ENV HOME_DIR="/home/ubuntu/hw-06-tomcat"
ADD https://github.com/efsavage/hello-world-war.git $HOME_DIR
WORKDIR $HOME_DIR/hello-world-war/
RUN mvn package && cp -r target/hello-world-war-1.0.0 /var/lib/tomcat9/webapps/
