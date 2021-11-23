FROM ubuntu:latest
RUN DEBIAN_FRONTEND=noninteractive apt update \
    && apt install wget -y \
    && apt install -y default-jdk maven
WORKDIR /package-07
RUN wget https://github.com/efsavage/hello-world-war.git
RUN mvn package --file hello-world-war/pom.xml
