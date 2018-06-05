# container-from-scratch

sample codes showing how to create a linux container from scratch

## Go sample

The `go`  directory contains a single go source for creating a
container with all namespaces and uid/gid mapping to current user.

To try the code:

```bash
$ cd go
$ wget http://dl-cdn.alpinelinux.org/alpine/v3.6/releases/x86_64/alpine-minirootfs-3.6.2-x86_64.tar.gz
$ tar -xzf alpine-minirootfs-3.6.2-x86_64.tar.gz -C rootfs
$ go run demo-container.go run PROGRAM
```

where `PROGRAM` is a program available in the rootfs, `/bin/sh` for example

Original author: https://gist.github.com/lizrice/a5ef4d175fd0cd3491c7e8d716826d27

## Bash sample

The `bash` directory contains a bash script allowing to download a rootfs, 
run a container (with only PID namespace and memory cgroup limit) and eventually
hxecute a second program in the previous container.

To try the code:

```bash
$ cd bash
$ chmod +x demo-container.sh
$ ./demo-container.sh pull
$ ./demo-container.sh run PROGRAM
```

where `PROGRAM` is a program available in the rootfs, `/bin/sh` for example

> **Note**: the script makes use of `sudo`

Original author: https://github.com/eraclitux/containers-from-scratch