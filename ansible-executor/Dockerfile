FROM library/docker:20.10.8
ENV ANSIBLE_VERSION 2.9.27
ENV ANSIBLE_LINT_VERSION 5.2.0
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
