# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.241.1/containers/ubuntu/.devcontainer/base.Dockerfile

# [Choice] Ubuntu version (use ubuntu-22.04 or ubuntu-18.04 on local arm64/Apple Silicon): ubuntu-22.04, ubuntu-20.04, ubuntu-18.04
ARG VARIANT="jammy"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>
ARG HOME="/home/vscode"
RUN apt-get update \
    && apt-get --yes install xz-utils \
    && apt-get --yes install build-essential \
    && apt-get --yes install gdb \
    && cd ${HOME} \
    && mkdir -p dlang \
    && wget https://dlang.org/install.sh -O dlang/install.sh \
    && chmod +x dlang/install.sh \
    && dlang/install.sh install \
    && chown -R vscode:vscode dlang \
    && echo "source ~/dlang/dmd-2.100.0/activate" >>.bashrc



