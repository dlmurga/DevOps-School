FROM ubuntu:20.04
ARG DEBIAN_FRONTEND=noninteractive
ENV PACKAGE_DIR="/package-07"
RUN apt update \
    && apt install default-jdk -y \
    && apt install maven -y \
    && apt install git -y \
    && rm -rf /var/lib/apt/lists/*
WORKDIR $PACKAGE_DIR
RUN git clone http://github.com/efsavage/hello-world-war.git
RUN mvn package -f $PACKAGE_DIR/hello-world-war/pom.xml
CMD cp -r $PACKAGE_DIR/hello-world-war/target/hello-world-war-1.0.0 /build-app-07/