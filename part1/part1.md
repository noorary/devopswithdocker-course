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

### 1.3

```
$ docker container run -it devopsdockeruh/pull_exercise

Give me the password: basics
You found the correct password. Secret message is:
"This is the secret message"

```

Password was found on the devopsdockeruh/pull_exercise dockerhub page.


### 1.4

```
$ docker image pull devopsdockeruh/exec_bash_exercise

$ docker container run -d c52ece

$ docker container exec -it relaxed_dhawan bash

:/usr/app# tail -f ./logs.txt

"Docker is easy"
Fri, 22 Jan 2021 13:41:23 GMT
Fri, 22 Jan 2021 13:41:26 GMT
Fri, 22 Jan 2021 13:41:29 GMT
Fri, 22 Jan 2021 13:41:32 GMT
Secret message is:
"Docker is easy"

```

### 1.5

```
$ docker run -d --rm -it ubuntu
$ docker container ls

CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS               NAMES
a4e780381614        ubuntu              "/bin/bash"              6 seconds ago       Up 5 seconds                            naughty_vaughan

$ docker container exec -it a4e bash

:/# apt-get update
:/# apt-get install curl

:/# sh -c 'echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'

Input website:
helsinki.fi
Searching..
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="http://www.helsinki.fi/">here</a>.</p>
</body></html>

```

### 1.6

[Dockerfile]()

```
FROM devopsdockeruh/overwrite_cmd_exercise

CMD ["-c"]
```

Commands

```
$ docker build -t docker-clock .
$ docker container run docker-clock

1
2
3
4
....
```

### 1.7

[Dockerfile]()

```
FROM ubuntu:16.04

WORKDIR /docker-project2

COPY script.sh .

RUN apt-get update && apt-get install -y curl

RUN chmod +x script.sh

CMD ./script.sh
``` 

Commands 
```
$ docker build -t curler .
$ docker run -it curler

input helsinki.fi
```

### 1.8

Commands
```
$ touch logs.txt
$ docker run --rm -v $(pwd)/logs.txt:/usr/app/logs.txt devopsdockeruh/first_volume_exercise
```

logs.txt 
```
Tue, 26 Jan 2021 15:31:27 GMT
Tue, 26 Jan 2021 15:31:30 GMT
Tue, 26 Jan 2021 15:31:33 GMT
Tue, 26 Jan 2021 15:31:36 GMT
Secret message is:
"Volume bind mount is easy"
Tue, 26 Jan 2021 15:31:42 GMT
Tue, 26 Jan 2021 15:31:45 GMT
Tue, 26 Jan 2021 15:31:48 GMT
Tue, 26 Jan 2021 15:31:51 GMT
Secret message is:
"Volume bind mount is easy"
```