FROM ubuntu:22.04

# 编译 confluent-kafka 支持 kerberos 认证
# https://github.com/confluentinc/confluent-kafka-python/blob/master/INSTALL.md#install-from-source-on-debian-or-ubuntu
RUN apt update && apt install -y \
    wget \
    software-properties-common \
    lsb-release \
    gcc \
    make \
    python3 \
    python3-pip \
    python3-dev \
    libsasl2-modules-gssapi-mit
RUN DEBIAN_FRONTEND=noninteractive apt install -y krb5-user
RUN wget -qO - https://packages.confluent.io/deb/7.8/archive.key | apt-key add -
RUN add-apt-repository "deb https://packages.confluent.io/clients/deb $(lsb_release -cs) main"
RUN apt update 
RUN apt install -y librdkafka-dev
RUN pip install --no-binary confluent-kafka confluent-kafka