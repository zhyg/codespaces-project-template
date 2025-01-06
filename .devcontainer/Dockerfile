FROM ubuntu:24.04

# Install essential packages
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
        git \
        curl \
        ca-certificates \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
