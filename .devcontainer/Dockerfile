
# Base image
FROM python:3.11-slim

RUN apt-get update && apt-get install -y \
    curl \
    git \
    sudo \
    && apt-get clean && rm -rf /var/lib/apt/lists/*


ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
    && echo "$USERNAME ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers
    

RUN pip install --upgrade pip autopep8

RUN pip install --no-cache-dir jupyter


USER $USERNAME

EXPOSE 8888
