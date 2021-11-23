FROM ubuntu:20.04
ENV DEBIAN_FRONTEND=noninteractive
RUN apt update \
    && apt install default-jdk -y \
    && apt install maven -y \
    && apt install git -y
WORKDIR /package-07
RUN git clone http://github.com/efsavage/hello-world-war.git ./
RUN mvn package -f hello-world-war/pom.xml
