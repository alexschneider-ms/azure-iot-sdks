FROM ubuntu:16.04
MAINTAINER Alexander Schneider <alex.schneider@microsoft.com>
RUN apt-get update && apt-get install -y \
    gcc \
    g++ \
    cmake \
    git \
    pkg-config \
    uuid-dev \
    libcurl4-openssl-dev \
    libssl-dev \
    openssh-server \
    openjdk-8-jdk
RUN mkdir /var/run/sshd
RUN useradd -ms /bin/bash jenkins
RUN echo "jenkins:CHANGEME" | chpasswd
RUN git clone --recursive https://github.com/Azure/azure-iot-sdks.git
WORKDIR /azure-iot-sdks/c/build_all/linux
RUN ./setup.sh && ./build.sh