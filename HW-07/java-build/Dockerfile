FROM ubuntu:20.04
ARG DEBIAN_FRONTEND=noninteractive
ENV PACKAGE_DIR="/package-07"
RUN apt update \
    && apt install default-jdk -y \
    && apt install maven -y \
    && apt install git -y
WORKDIR $PACKAGE_DIR
RUN git clone http://github.com/efsavage/hello-world-war.git
RUN mvn package -f $PACKAGE_DIR/hello-world-war/pom.xml
