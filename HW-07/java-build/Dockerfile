FROM ubuntu:latest
RUN DEBIAN_FRONTEND=noninteractive apt aupdate \
    && apt install -y default-jdk maven
WORKDIR /package-07
ADD https://github.com/efsavage/hello-world-war.git ./
RUN mvn package ./hello-world-war/pom.xml
