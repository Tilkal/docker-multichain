# Docker Images for MultiChain

The [`tilkal/multichain`] images (see all [available tags]) come in two flavors:

1. **[`bitnami/minideb`]-based images**
    * [`2.0-alpha-2`]
    * [`latest`], `1.0.3`

2. **[`microsoft/nanoserver`]-based images**
    * [`2.0-alpha-2-nanoserver`]
    * [`latest-nanoserver`], `1.0.3-nanoserver`


# Volume

* `/root/.multichain` for the minideb-based images.
* `C:/Users/ContainerAdministrator/AppData/Roaming/MultiChain` for the Nano Server-based images.


# Usage

**Creating a blockchain named `testchain`**

`docker run --rm -v node1-data:<volume> --entrypoint multichain-util tilkal/multichain create testchain`

**Starting a node of a blockchain named `testchain`**

`docker run -v node1-data:<volume> tilkal/multichain testchain`

**Adding a node to an existing blockchain named `testchain`**

`docker run --rm -v node2-data:<volume> tilkal/multichain testchain@<node1-host>:<node1-port>`

**Granting access to a node added to a blockchain named `testchain` from a running node**

`docker exec <node1-container> multichain-cli testchain grant <node2-address> connect,send,receive`


# License

**`Dockerfile` license information:**

Copyright © 2017 Tilkal SAS [`MIT License`]

**MultiChain license information:**

Copyright © 2014-2017 Coin Sciences Ltd [`GPLv3`](https://github.com/MultiChain/multichain/blob/master/COPYING)

Portions copyright © 2009-2016 The Bitcoin Core developers

Portions copyright many others - see individual files


[`bitnami/minideb`]: https://store.docker.com/community/images/bitnami/minideb
[`microsoft/nanoserver`]: https://store.docker.com/images/nanoserver
[`tilkal/multichain`]: https://store.docker.com/community/images/tilkal/multichain
[available tags]: https://store.docker.com/community/images/tilkal/multichain/tags

[`latest`]: https://github.com/Tilkal/docker-multichain/blob/master/1.0/minideb/Dockerfile
[`2.0-alpha-2`]: https://github.com/Tilkal/docker-multichain/blob/master/2.0/minideb/Dockerfile

[`latest-nanoserver`]: https://github.com/Tilkal/docker-multichain/blob/master/1.0/nanoserver/Dockerfile
[`2.0-alpha-2-nanoserver`]: https://github.com/Tilkal/docker-multichain/blob/master/2.0/nanoserver/Dockerfile

[`MIT License`]: https://github.com/Tilkal/docker-multichain/blob/master/LICENSE
[`GPLv3`]: https://github.com/MultiChain/multichain/blob/master/COPYING
