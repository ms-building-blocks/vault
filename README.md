# wdijkerman/vault

![Docker Stars](https://img.shields.io/docker/stars/wdijkerman/vault.svg) ![Docker Pulls](https://img.shields.io/docker/pulls/wdijkerman/vault.svg) [![](https://images.microbadger.com/badges/image/wdijkerman/vault.svg)](https://microbadger.com/images/wdijkerman/vault "Get your own image badge on microbadger.com") [![Build Status](https://travis-ci.org/dj-wasabi/vault.svg?branch=master)](https://travis-ci.org/dj-wasabi/vault) 

## Introduction

This is an Docker container for Vault running on Alpine.

The versions in this Docker container:

* alpine: 3.7
* vault: 0.9.6
* python: 2.7.13

### Volumes

The following volumes are available:

* /vault/ssl
* /vault/config
* /vault/audit

### User

Vault is running as user vault. With the following capabilities (which are configured in this container)it should be no problem running Vault as non-root user:

- cap_ipc_lock (Should not swap. Also `--cap-add IPC_LOCK` should be added to the command line when to start the Vault container.)

The UID used in this container is 1051. So make sure the id is already available on the host running the container when host mounts are used.

### Versions

- `0.6.2`, [(Dockerfile)](https://github.com/dj-wasabi/vault/blob/d4fe374d29508926bed6c188b05c0764016f3a52/Dockerfile)
- `0.6.5`, [(Dockerfile)](https://github.com/dj-wasabi/vault/blob/66494b152453c34e0094517383b2a2e38f5fdb8b/Dockerfile)
- `0.7.2`, [(Dockerfile)](https://github.com/dj-wasabi/vault/blob/de4519d83b9c33a66d4f47dd4c0f688f358834bd/Dockerfile)
- `0.7.3`, [(Dockerfile)](https://github.com/dj-wasabi/vault/blob/14574e99a643df5ea788c080f4407db2c1d682cb/Dockerfile)
- `0.8.0`, [(Dockerfile)](https://github.com/dj-wasabi/vault/blob/99fd6aa38f4e7da3a4cbaa7adf74665b4a6e5f00/Dockerfile)
- `0.8.1`, [(Dockerfile)](https://github.com/dj-wasabi/vault/blob/79b143040f4720610034ea08462957403dce7c9c/Dockerfile)
- `0.9.2`, [(Dockerfile)](https://github.com/dj-wasabi/vault/blob/702f4fc7518d0891386f78d9f8d8f0b2b86893a5/Dockerfile)
- `0.9.6`, `latest` [(Dockerfile)](https://github.com/dj-wasabi/vault/blob/master/Dockerfile)

### Python?

Python is also installed in the container. Python is used for testing the container, which is done with the tool `testinfra`.
You can see in the `tests` directory a file named `test_vault.py` which will be executed. (Still WiP)

## Install the container

Just run the following command to download the container:

```bash
docker pull wdijkerman/vault
```

### Arguments

There are several arguments that can be used for configuring this container.

Environment | Description
--- | ---
CONSUL_HOST | The fqdn or ip of the Consul agent. Default: `consul`
CONSUL_PORT | The port on which Consul is available. Default: `8500`
CONSUL_SCHEME | 
CONSUL_TLS_SKIP_VERIFY |
CONSUL_TOKEN | 

--cap-add IPC_LOCK

## Tests

Testinfra

## how to's

[Setting up a secure Consul cluster](https://werner-dijkerman.nl/2017/01/09/setting-up-a-secure-consul-cluster-with-docker/)
[Configuring Access Control Lists](https://werner-dijkerman.nl/2017/01/11/configuring-access-control-lists-in-consul/)
[Setting up a secure Vault with a Consul backend](https://werner-dijkerman.nl/2017/01/15/setting-up-a-secure-vault-with-a-consul-backend/)

## License

The MIT License (MIT)

See file: License

## Issues

Please report issues at https://github.com/dj-wasabi/consul/issues 

Pull Requests are welcome!
