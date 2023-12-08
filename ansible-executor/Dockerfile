FROM library/docker:24.0.7
ENV ANSIBLE_VERSION 8.6.1
ENV ANSIBLE_LINT_VERSION 6.22.1
RUN apk update \
 && apk add --no-cache \
    bash \
    ca-certificates \
    curl \
    git \
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
 && pip3 install --ignore-installed \
    ansible==${ANSIBLE_VERSION} \
    ansible-lint==${ANSIBLE_LINT_VERSION} \
 && rm -rf /root/.cache/pip \
 && apk del .build-deps \
 && rm -rf /var/cache/apk/*
