FROM python:3.8-slim

RUN apt-get update
RUN apt-get install git -y
RUN python -m pip install --upgrade pip
RUN pip install flake8 --upgrade
RUN pip install autopep8 --upgrade
RUN pip install black
RUN pip install isort
RUN pip install bandit
RUN pip install pytest