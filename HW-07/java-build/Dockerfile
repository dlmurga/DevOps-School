FROM ubuntu:20.04
RUN DEBIAN_FRONTEND=noninteractive apt update \
    && apt install -y default-jdk maven git
WORKDIR /package-07
RUN git clone http://github.com/efsavage/hello-world-war.git ./
WORKDIR /package-07/hello-world-war
RUN mvn package
