FROM library/docker:25.0.5
ENV ANSIBLE_VERSION 11.1.0
ENV ANSIBLE_LINT_VERSION 24.12.2
COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh \
 && apk update \
 && apk add --no-cache \
    bash \
    ca-certificates \
    curl \
    git \
    openssh-client \
    openssl \
    py3-cryptography \
    py3-pip \
    sshpass \
 && apk add --update --virtual .build-deps \
    build-base \
    libffi-dev \
    openssl-dev \
    python3-dev \
 && python3 -m venv venv \
 && source venv/bin/activate \
 && pip install --upgrade pip \
 && pip install --ignore-installed \
    ansible==${ANSIBLE_VERSION} \
    ansible-lint==${ANSIBLE_LINT_VERSION} \
 && rm -rf /root/.cache/pip \
 && apk del .build-deps \
 && rm -rf /var/cache/apk/*
ENTRYPOINT ["/entrypoint.sh"]