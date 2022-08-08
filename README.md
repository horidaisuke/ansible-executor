# ansible-executor
Circleci executor installed ansible

## Usage

Define executor in `.circleci/config.yml` like this:

```yaml
executors:
  ansible-executor:
    docker:
      - image: horidaisuke/ansible-executor:latest
    shell: /bin/bash -leo pipefail
    environment:
      - BASH_ENV: /etc/profile
```

## Tags

Tags name is made from join of [simple tags of docker](https://hub.docker.com/_/docker) and [versions of ansible](https://github.com/ansible/ansible/tags).

* `20.10.17-ansible-5.8.0`, `latest`

## License

View [license information](https://github.com/horidaisuke/ansible-executor/blob/main/LICENSE) for the software contained in this image.

This license is inherited or included from licenses of [library/docker](https://hub.docker.com/_/docker) and [ansible](https://github.com/ansible/ansible/blob/devel/COPYING).
