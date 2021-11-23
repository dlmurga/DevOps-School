FROM ubuntu:latest
RUN DEBIAN_FRONTEND=noninteractive apt update \
    && apt install -y default-jdk maven
WORKDIR /package-07
ADD https://github.com/efsavage/hello-world-war.git /package7
RUN mvn package --file hello-world-war/pom.xml
