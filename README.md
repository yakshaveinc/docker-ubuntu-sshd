# docker-ubuntu-sshd

[![License](https://img.shields.io/github/license/uchida/docker-ubuntu-sshd.svg?maxAge=2592000)](https://tldrlegal.com/license/creative-commons-cc0-1.0-universal)

Ubuntu image with SSH access. Useful for testing deployments, and do local development using same tools (like Ansible) as with any Ubuntu server.

Available from Docker Hub as [yakshaveinc/docker-ubuntu-sshd](https://hub.docker.com/r/yakshaveinc/docker-ubuntu-sshd).

## Login information

|user  |password|
|------|--------|
|root  |root    |
|ubuntu|ubuntu  |

## Image tags

- `20.04`, `latest`

## Usage

Run image and expose it on port 2222 for local access only.
```bash
docker run --detach -p 127.0.0.1:2222:22 yakshaveinc/docker-ubuntu-sshd
```

Connect with SSH ignoring non-actual security warning.
```bash
ssh root@127.0.0.1 -p 2222 -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null
# or ssh root@localhost -p 2222
# or ssh ubuntu@localhost -p 2222
```

## Installed packages

- openssh-server
- python
- python-apt
- sudo

## License

Contents on this repository are dedicated to [![CC0 public domain](http://i.creativecommons.org/p/zero/1.0/80x15.png "CC0 public domain")](https://creativecommons.org/publicdomain/zero/1.0/).
No rights reserved.

License for distributed Docker images follows one of [Ubuntu Project](http://www.ubuntu.com/about).
