FROM python:3.8-slim

# install git
RUN apt-get update && apt-get install git -y

# install python stuff
RUN python -m pip install --upgrade pip
RUN pip install flake8 --upgrade
RUN pip install autopep8 --upgrade
RUN pip install black
RUN pip install isort
RUN pip install bandit
RUN pip install pytest


# Create the user
ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -s /bin/bash -m $USERNAME \
    #
    # [Optional] Add sudo support. Omit if you don't need to install software after connecting.
    && apt-get update \
    && apt-get install -y sudo \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME


USER $USERNAME