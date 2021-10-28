# Podman stack

This repository contains some podman stack startables with `make` command.  
This will be designed to resolve `podman-compose` network issues on MacOS.

# Usage

## General

You could retrieves informations about make target simply with `make` command :

```shell
cd mariadb
make
```

## Examples

### MariaDB latest

To start `mariadb:latest` with default environment values :

```shell
cd mariadb
make latest-up
```

To stop and remove container :

```shell
cd mariadb
make latest-down
```

#### Environment override

You could override all variables present in makefile (presented into help).  
For example to override default user password :

```shell
cd mariadb
make user_pass=toto latest-up
```
