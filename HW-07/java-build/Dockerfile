FROM ubuntu:20.04
RUN DEBIAN_FRONTEND=noninteractive apt update \
    && apt install -y default-jdk maven
WORKDIR /package-07
ADD http://github.com/efsavage/hello-world-war.git /package-07/
WORKDIR /package-07/hello-world-war
RUN mvn package
