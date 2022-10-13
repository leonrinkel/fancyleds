FROM mcr.microsoft.com/vscode/devcontainers/base:bullseye

RUN \
    export DEBIAN_FRONTEND=noninteractive && \
    apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y \
        make curl unzip tar && \
    apt-get autoremove -y && \
    apt-get clean -y && \
    rm -rf /var/lib/apt/lists/*

ARG GCC_URL="https://armkeil.blob.core.windows.net/developer/Files/downloads/gnu-rm/10.3-2021.10/gcc-arm-none-eabi-10.3-2021.10-aarch64-linux.tar.bz2"
ARG GCC_TAR="gcc-arm-none-eabi-10.3-2021.10-aarch64-linux.tar.bz2"

RUN \
    curl -O ${GCC_URL} && \
    tar -C /opt -xvf ${GCC_TAR} && \
    rm ${GCC_TAR}

ENV GNU_INSTALL_ROOT="/opt/gcc-arm-none-eabi-10.3-2021.10/bin/"
ENV GNU_VERSION="10.3-2021.10"

ARG SDK_URL="https://nsscprodmedia.blob.core.windows.net/prod/software-and-other-downloads/sdks/nrf5/binaries/nrf5_sdk_17.1.0_ddde560.zip"
ARG SDK_ZIP="nrf5_sdk_17.1.0_ddde560.zip"

RUN \
    curl -O ${SDK_URL} && \
    unzip -d /opt ${SDK_ZIP} && \
    rm ${SDK_ZIP}

ENV SDK_ROOT="/opt/nRF5_SDK_17.1.0_ddde560"
