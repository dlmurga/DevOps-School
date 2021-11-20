FROM tomcat:9.0
LABEL maintainer="dl.murga@yandex.ru"
RUN apt update && apt install maven -y
ADD https://github.com/efsavage/hello-world-war.git /package
WORKDIR /package/hello-world-war
RUN mvn package && cp -r target/hello-world-war-1.0.0 /var/lib/tomcat9/webapps/
