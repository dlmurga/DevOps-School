FROM ubuntu:latest
RUN DEBIAN_FRONTEND=noninteractive apt install -y git default-jdk maven
WORKDIR /package
RUN git clone https://github.com/efsavage/hello-world-war.git
WORKDIR /package/hello-world-war
RUN mvn package
VOLUME ./app_dir
