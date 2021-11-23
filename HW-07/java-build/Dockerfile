FROM ubuntu:20.04
ENV DEBIAN_FRONTEND=noninteractive
RUN apt update \
    && apt install default-jdk \
    && apt install maven \
    && apt install git
WORKDIR /package-07
RUN git clone http://github.com/efsavage/hello-world-war.git ./
RUN mvn package -f hello-world-war/pom.xml
