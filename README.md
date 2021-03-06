## Supported tags and respective `Dockerfile` links

* [`2.0.0-beta3, 2.0-beta3, 2-beta3` (*2.0-beta/beta3/Dockerfile*)](https://github.com/akai-z/docker-alpine-libstorj/blob/master/2.0-beta/beta3/Dockerfile)
* [`2.0.0-beta2, 2.0-beta2, 2-beta2` (*2.0-beta/beta2/Dockerfile*)](https://github.com/akai-z/docker-alpine-libstorj/blob/master/2.0-beta/beta2/Dockerfile)
* [`1.0.3, 1.0, 1, latest` (*1.0/Dockerfile*)](https://github.com/akai-z/docker-alpine-libstorj/blob/master/1.0/Dockerfile)

## Alpine version

`3.8`

## What is Libstorj?

Asynchronous multi-platform C library and CLI for encrypted file transfer on the Storj network.

**Note: The library is deprecated.**

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

* `BUILDER_URL`  
Allows to change library source builder shell script URL.  
([Click here to know more about the script](https://github.com/akai-z/libstorj-alpine-source-builder))

## Authors

* Ammar K.

## License

[GNU General Public License version 2](https://github.com/akai-z/docker-alpine-libstorj/blob/master/LICENSE)
