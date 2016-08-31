FROM ubuntu:14.04
MAINTAINER Alexander Schneider <alex.schneider@microsoft.com>
RUN apt-get update && apt-get install -y software-properties-common openssh-server openjdk-6-jdk
RUN mkdir /var/run/sshd
RUN useradd -ms /bin/bash jenkins
RUN echo "jenkins:CHANGEME" | chpasswd
RUN add-apt-repository ppa:ubuntu-toolchain-r/test
RUN add-apt-repository ppa:george-edison55/cmake-3.x
RUN apt-get update && apt-get install -y \
    gcc-4.9 g++-4.9 cmake git
RUN update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-4.9 60 --slave /usr/bin/g++ g++ /usr/bin/g++-4.9
RUN git clone --recursive https://github.com/Azure/azure-iot-sdks.git
WORKDIR /azure-iot-sdks/c/build_all/linux
RUN ./setup.sh && ./build.sh