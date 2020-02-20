FROM python:3.7-slim

RUN apt-get update \
 && apt-get install -y \
    ca-certificates curl gnupg2 zip jq bash-completion \
 && apt-get autoremove -y \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

RUN pip install --no-cache-dir --upgrade \
    pip setuptools onelogin-aws-cli

WORKDIR /tmp
COPY pgp.key .
RUN gpg --import pgp.key
RUN curl -o awscliv2.zip https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip && \
    curl -o awscliv2.sig https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip.sig && \
    gpg --verify awscliv2.sig awscliv2.zip && \
    unzip awscliv2.zip && ./aws/install --update && \
    rm -r pgp.key awscliv2.sig awscliv2.zip aws
