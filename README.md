# SyncDir

This Docker image can be used to keep two directories (mounted as volumes) in sync.

## Why?

It's really common to use mounted volumes with the source code of a project from the host filesystem to a container during development. If the environment machine is a Mac, the volume is mounted using either really slow drivers like vboxfs or fuseosx.

This image can be used to avoid the application to constantly access the files over a remote filesystem and use a local named volume instead

## How to use

Run this image in a separate container with two volumes. The source directory must be mounted on `/source` and the target volume must be mounted in `/target`. For example:

```sh
docker run -v `pwd`:/source -v app_src:/target instedd/syncdir
```
