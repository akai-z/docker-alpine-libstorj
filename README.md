Docker Alpine Libstorj
======================

This is an Alpine Linux based Libstorj Docker image.

## What is Libstorj?

Asynchronous multi-platform C library and CLI for encrypted file transfer on the Storj network.

([Click here to know more about Libstorj](https://github.com/storj/libstorj))

## What is Storj?

Storj is a platform, token, and suite of decentralized applications that allows you to store data in a secure and decentralized manner.

Check the following links to know more about Storj:  
https://storj.io/  
https://github.com/storj/storj

## Docker Build-Args

The following args could be passed during Docker image build-time:

* `VERSION`  
Allows to change Libstorj version.
  - Using specific version: `VERSION=tags/<GIT_TAG>`
  - Latest version: `VERSION=latest`

* `REPOSITORY`  
Allows to change Github repository name.  
`REPOSITORY=<GITHUB_USERNAME>/<GITHUB_REPOSITORY_NAME>`

## Authors

* Ammar K.

## License

[GNU General Public License version 2](https://github.com/akai-z/docker-alpine-libstorj/blob/master/LICENSE)
