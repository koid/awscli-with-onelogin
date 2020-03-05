FROM python:3.7-slim

RUN apt-get update \
 && apt-get install -y \
    ca-certificates curl jq bash-completion \
 && apt-get autoremove -y \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

RUN pip install --no-cache-dir --upgrade \
    pip awscli onelogin-aws-cli

WORKDIR /tmp
