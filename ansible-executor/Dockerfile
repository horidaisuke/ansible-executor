FROM library/docker:20.10.23
ENV ANSIBLE_VERSION 7.3.0
ENV ANSIBLE_LINT_VERSION 6.10.2
RUN apk update \
 && apk add --no-cache \
    bash \
    ca-certificates \
    curl \
    openssh-client \
    openssl \
    py3-cryptography \
    py3-pip \
    python3\
    sshpass \
 && apk add --update --virtual .build-deps \
    build-base \
    libffi-dev \
    openssl-dev \
    python3-dev \
 && pip3 install --upgrade \
    pip \
 && pip3 install \
    ansible==${ANSIBLE_VERSION} \
    ansible-lint==${ANSIBLE_LINT_VERSION} \
 && rm -rf /root/.cache/pip \
 && apk del .build-deps \
 && rm -rf /var/cache/apk/*
