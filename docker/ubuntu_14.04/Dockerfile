FROM ubuntu:14.04
MAINTAINER Alexander Schneider <alex.schneider@microsoft.com>
RUN apt-get update && apt-get install -y gcc cmake git openssh-server openjdk-6-jdk
RUN mkdir /var/run/sshd
RUN useradd -ms /bin/bash jenkins
RUN echo "jenkins:CHANGEME" | chpasswd
RUN git clone --recursive https://github.com/Azure/azure-iot-sdks.git
WORKDIR /azure-iot-sdks/c/build_all/linux
RUN ./setup.sh && ./build.sh