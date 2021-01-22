## Part 1 solutions

### 1.1

```
docker container ls -a

CONTAINER ID        IMAGE               COMMAND                  CREATED              STATUS                      PORTS               NAMES
d854324e9ded        nginx               "/docker-entrypoint.…"   About a minute ago   Up About a minute           80/tcp              optimistic_buck
3605b4980136        nginx               "/docker-entrypoint.…"   About a minute ago   Exited (0) 20 seconds ago                       naughty_chebyshev
0dc536581cb4        nginx               "/docker-entrypoint.…"   About a minute ago   Exited (0) 28 seconds ago                       admiring_cartwright

``` 

### 1.2

```
$ docker container ls -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES

$ docker image ls
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE

```