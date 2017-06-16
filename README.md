# Docker Images for MultiChain

The [`tilkal/multichain`] images come in two flavors.

The `tilkal/multichain:<version>` variant is based on [`bitnami/minideb`].<br>
Supported tags: [`latest`] [`1.0-beta-2`]

The `tilkal/multichain:<version>-nanoserver` variant is based on [`microsoft/nanoserver`].<br>
Supported tags: [`latest-nanoserver`] [`1.0-beta-2-nanoserver`]


# Usage

```shell
# Creating a blockchain named testchain
docker run -v node1-data:/root/.multichain --entrypoint multichain-util tilkal/multichain create testchain
```

```shell
# Starting a node of a blockchain named testchain
docker run -v node1-data:/root/.multichain tilkal/multichain testchain
```

```shell
# Adding a node to an existing blockchain named testchain
docker run -v node2-data:/root/.multichain tilkal/multichain testchain@<address>:<port>
```

```shell
# Granting access to a node added to a blockchain named testchain from a running node
docker exec <container> multichain-cli testchain grant <address> connect,send,receive
```


# License

**`Dockerfile` license information:**
> Copyright (c) 2017 Tilkal SAS<br>
> License: MIT License, see [LICENSE](https://github.com/Tilkal/docker-multichain/blob/master/LICENSE)

**MultiChain license information:**
> Copyright (c) 2014-2017 Coin Sciences Ltd<br>
> License: GNU General Public License version 3, see [COPYING](https://github.com/MultiChain/multichain/blob/master/COPYING)<br>
>
> Portions copyright (c) 2009-2016 The Bitcoin Core developers<br>
> Portions copyright many others - see individual files


[`bitnami/minideb`]: https://store.docker.com/community/images/bitnami/minideb
[`microsoft/nanoserver`]: https://store.docker.com/images/nanoserver
[`tilkal/multichain`]: https://store.docker.com/community/images/tilkal/multichain

[`latest`]: https://github.com/Tilkal/docker-multichain/blob/0177cba2606466810be3806dc14e25a65ec4809d/1.0/minideb/Dockerfile
[`1.0-beta-2`]: https://github.com/Tilkal/docker-multichain/blob/0177cba2606466810be3806dc14e25a65ec4809d/1.0/minideb/Dockerfile

[`latest-nanoserver`]: https://github.com/Tilkal/docker-multichain/blob/0177cba2606466810be3806dc14e25a65ec4809d/1.0/nanoserver/Dockerfile
[`1.0-beta-2-nanoserver`]: https://github.com/Tilkal/docker-multichain/blob/0177cba2606466810be3806dc14e25a65ec4809d/1.0/nanoserver/Dockerfile
