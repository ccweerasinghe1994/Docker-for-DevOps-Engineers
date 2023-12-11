# Docker-for-DevOps-Engineers

- [Docker-for-DevOps-Engineers](#docker-for-devops-engineers)
  - [1.What is Docker](#1what-is-docker)
  - [2.Docker vs VM](#2docker-vs-vm)
  - [3.Installing Docker](#3installing-docker)
  - [4.Exploring Docker Dashboard](#4exploring-docker-dashboard)
  - [5.Tools](#5tools)
  - [6.Getting started with Docker](#6getting-started-with-docker)
  - [7.Undestanding Containers](#7undestanding-containers)
  - [8.Docker Images and Containers](#8docker-images-and-containers)
  - [9.Managing Containers](#9managing-containers)
  - [10.Docker ps format](#10docker-ps-format)
  - [11.Exposing Ports](#11exposing-ports)
  - [12.Exposing Multiple Ports](#12exposing-multiple-ports)
  - [13.Naming Containers](#13naming-containers)
  - [14.Running Container in the background](#14running-container-in-the-background)
  - [15.Docker Images](#15docker-images)
  - [16.Managing Docker Images](#16managing-docker-images)
  - [17.Docker Pull](#17docker-pull)
  - [18.Inspecting Images](#18inspecting-images)
  - [19.Docker Architecture](#19docker-architecture)
  - [20.Docker Daemon](#20docker-daemon)
  - [21.Volumes](#21volumes)
  - [22.Bind Mount Volumes](#22bind-mount-volumes)
  - [23.Bind Mount Volumes in Action](#23bind-mount-volumes-in-action)
  - [24.Using Vomules for Local Dev](#24using-vomules-for-local-dev)
  - [25.Docker Volumes](#25docker-volumes)
  - [26.TMPFS Mount](#26tmpfs-mount)
  - [27.Dockerfile](#27dockerfile)
  - [28.Creating Dockerfile](#28creating-dockerfile)
  - [29.Building DockerImages](#29building-dockerimages)
  - [30.Running a container from Custom Image](#30running-a-container-from-custom-image)
  - [31.Investigate Container file system](#31investigate-container-file-system)
  - [32.Buliding ExpressJS API](#32buliding-expressjs-api)
  - [33.Dockerfile and Building image for user-api](#33dockerfile-and-building-image-for-user-api)
  - [34.Running Container for user-api image](#34running-container-for-user-api-image)
  - [35.Exploring Dockerfiles](#35exploring-dockerfiles)
  - [36.Dockerfile reference](#36dockerfile-reference)
  - [37.Pulling Images using a Specifc Tag](#37pulling-images-using-a-specifc-tag)
  - [38.Creating tags](#38creating-tags)
  - [39.Creating Version 2 of the Dashboard](#39creating-version-2-of-the-dashboard)
  - [40.Never Run Latest In Production](#40never-run-latest-in-production)
  - [41.Image Variants](#41image-variants)
  - [42.Docker Registries](#42docker-registries)
  - [43.Docker Login](#43docker-login)
  - [44.Docker push](#44docker-push)
  - [45.Docker Inpect](#45docker-inpect)
  - [46.Logs](#46logs)
  - [47.Running commands in Containers](#47running-commands-in-containers)
  - [48.How to comunicate between containers](#48how-to-comunicate-between-containers)
  - [49.Docker Network](#49docker-network)
  - [50.MongoDB Container](#50mongodb-container)
  - [51.MongoExpress](#51mongoexpress)
  - [52.Understanding Container Communication](#52understanding-container-communication)
  - [53.Another example](#53another-example)
  - [54.What is Docker Compose](#54what-is-docker-compose)
  - [55.Docker Compose cmd](#55docker-compose-cmd)
  - [56.Services](#56services)
  - [57.Docker Network](#57docker-network)
  - [58.Docker Compose Up](#58docker-compose-up)
  - [59.Exploring docker compose commands](#59exploring-docker-compose-commands)
  - [60.Docker Volume](#60docker-volume)
  - [61.Docker Compose Documentation](#61docker-compose-documentation)
  - [62.Docker scan](#62docker-scan)
  - [63.Trivy](#63trivy)
  - [64.Distroless Images](#64distroless-images)
  - [65.Security Best Practices](#65security-best-practices)


## 1.What is Docker
![Alt text](image.png)

what is docker ?

Docker is a tool designed to make it easier to create, deploy, and run applications by using containers. Containers allow a developer to package up an application with all of the parts it needs, such as libraries and other dependencies, and deploy it as one package.

## 2.Docker vs VM

![Alt text](image-1.png)

![Alt text](image-2.png)

![Alt text](image-3.png)

![Alt text](image-4.png)



## 3.Installing Docker

docker desktop for windows link : https://docs.docker.com/docker-for-windows/install/

## 4.Exploring Docker Dashboard

![Alt text](image-5.png)

## 5.Tools

we need to install git bash and visual studio code

## 6.Getting started with Docker

```bash
docker -v

```

![Alt text](image-6.png)

to see all the available commands

![Alt text](image-7.png)

![Alt text](image-9.png)

![Alt text](image-8.png)

http://localhost/tutorial/

![Alt text](image-10.png)

```bash
# This code is used to stop and remove a docker container. The docker container is identified by its container ID, which is passed in through the args array. The container is stopped first, then removed.

➜  ~ docker container stop 8aeae32b0e0a
8aeae32b0e0a
➜  ~ docker rm 8aeae32b0e0a
8aeae32b0e0a

```

```bash
# Pull the latest image from Docker Hub
sudo docker pull amigoscode/2048

# Run the image on port 80
# -d means run in detached mode
# -p means map port 80 on the host to port 80 on the container
sudo docker run -d -p 80:80 amigoscode/2048
```
http://localhost:80

![Alt text](image-11.png)


now we can see the running containers

![Alt text](image-12.png)


## 7.Undestanding Containers

![Alt text](image-13.png)

![Alt text](image-14.png)

```bash
➜  ~ docker container ls --help

Usage:  docker container ls [OPTIONS]

List containers

Aliases:
  docker container ls, docker container list, docker container ps, docker ps

Options:
  -a, --all             Show all containers (default shows just running)
  -f, --filter filter   Filter output based on conditions provided
      --format string   Format output using a custom template:
                        'table':            Print output in table format with column headers (default)
                        'table TEMPLATE':   Print output in table format using the given Go template
                        'json':             Print in JSON format
                        'TEMPLATE':         Print output using the given Go template.
                        Refer to https://docs.docker.com/go/formatting/ for more information about formatting output with templates
  -n, --last int        Show n last created containers (includes all states) (default -1)
  -l, --latest          Show the latest created container (includes all states)
      --no-trunc        Don't truncate output
  -q, --quiet           Only display container IDs
  -s, --size            Display total file sizes
```

![Alt text](image-15.png)

```bash
➜  ~ docker container ls
CONTAINER ID   IMAGE             COMMAND                  CREATED             STATUS          PORTS                NAMES
f4783336d1d3   amigoscode/2048   "/docker-entrypoint.…"   About an hour ago   Up 25 seconds   0.0.0.0:80->80/tcp   zealous_vaughan
```
```bash
➜  ~ docker exec --help

Usage:  docker exec [OPTIONS] CONTAINER COMMAND [ARG...]

Execute a command in a running container

Aliases:
  docker container exec, docker exec

Options:
  -d, --detach               Detached mode: run command in the background
      --detach-keys string   Override the key sequence for detaching a container
  -e, --env list             Set environment variables
      --env-file list        Read in a file of environment variables
  -i, --interactive          Keep STDIN open even if not attached
      --privileged           Give extended privileges to the command
  -t, --tty                  Allocate a pseudo-TTY
  -u, --user string          Username or UID (format: "<name|uid>[:<group|gid>]")
  -w, --workdir string       Working directory inside the container
➜  ~
``` 

```bash
docker exec -i -t f4783336d1d3 sh
# ls
bin  boot  dev  docker-entrypoint.d  docker-entrypoint.sh  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
#
```
as you can see we are inside the container

and this is a linux file structure.

so if we go to the binary folder we can see all the binaries that are installed in the container

```bash
# cd bin
# ls
bash   cp    dir            egrep    gunzip    login  mktemp      nisdomainname  rm         sleep  tempfile  uncompress    zcat    zforce
cat    dash  dmesg          false    gzexe     ls     more        pidof          rmdir      stty   touch     vdir          zcmp    zgrep
chgrp  date  dnsdomainname  fgrep    gzip      lsblk  mount       pwd            run-parts  su     true      wdctl         zdiff   zless
chmod  dd    domainname     findmnt  hostname  mkdir  mountpoint  rbash          sed        sync   umount    which         zegrep  zmore
chown  df    echo           grep     ln        mknod  mv          readlink       sh         tar    uname     ypdomainname  zfgrep  znew
#
```
app files
```bash
# cd /usr/share/nginx/html
# ls
50x.html  CONTRIBUTING.md  Dockerfile  LICENSE.txt  README.md  Rakefile  favicon.ico  index.html  js  meta  style
#
```

![Alt text](image-16.png)

## 8.Docker Images and Containers

![Alt text](image-17.png)

from one docker image we can create multiple containers.

```bash
docker container run -d -p 8080:80 amigoscode/2048
```
`amigoscode/2048` this is the image name

`-d` run in detached mode

`-p` map port 8080 on the host to port 80 on the container

`8080:80` this is the port mapping


```bash
➜  ~ docker container run -d -p 8080:80 nginx
Unable to find image 'nginx:latest' locally
latest: Pulling from library/nginx
9a59d19f9c5b: Download complete
9ea27b074f71: Download complete
c6edf33e2524: Download complete
84b1ff10387b: Download complete
9b16c94bb686: Download complete
517357831967: Download complete
Digest: sha256:10d1f5b58f74683ad34eb29287e07dab1e90f10af243f151bb50aa5dbb4d62ee
Status: Downloaded newer image for nginx:latest
4cead163c96459f132b0a735781b4df5fd445568c69052aa6171ab37c1316273
➜  ~ docker container ls
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS                  NAMES
4cead163c964   nginx     "/docker-entrypoint.…"   13 seconds ago   Up 11 seconds   0.0.0.0:8080->80/tcp   objective_mirzakhani
```

http://localhost:8080/

![Alt text](image-18.png)

https://hub.docker.com/

![Alt text](image-19.png)

## 9.Managing Containers
```bash
# to see all the containers
docker container ls -a

CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                      PORTS     NAMES
4cead163c964   nginx     "/docker-entrypoint.…"   24 minutes ago   Exited (0) 10 minutes ago             objective_mirzakhani

# to see all the containers with their ids
# -q is for quiet mode
docker container ls -aq

4cead163c964

# to stop a container
docker container stop 4cead163c964

# to remove a stopped container
docker container rm 4cead163c964

# to remove a running container
# -f is for force
docker container rm -f 4cead163c964

# to remove all the containers
docker container rm $(docker container ls -aq)

# to start a container
docker container start 4cead163c964
```

## 10.Docker ps format
```bash
➜  Docker-for-DevOps-Engineers git:(main) ✗ docker ps --help 

Usage:  docker ps [OPTIONS]

List containers

Aliases:
  docker container ls, docker container list, docker container ps, docker ps

Options:
  -a, --all             Show all containers (default shows just running)
  -f, --filter filter   Filter output based on conditions provided
      --format string   Format output using a custom template:
                        'table':            Print output in table format with column headers (default)
                        'table TEMPLATE':   Print output in table format using the given Go template
                        'json':             Print in JSON format
                        'TEMPLATE':         Print output using the given Go template.
                        Refer to https://docs.docker.com/go/formatting/ for more information about formatting output with templates
  -n, --last int        Show n last created containers (includes all states) (default -1)
  -l, --latest          Show the latest created container (includes all states)
      --no-trunc        Don't truncate output
  -q, --quiet           Only display container IDs
  -s, --size            Display total file sizes
```
![Alt text](image-20.png)

![Alt text](image-21.png)

![Alt text](image-22.png)

## 11.Exposing Ports

![Alt text](image-23.png)



```bash
➜  ~ docker container ls -a
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
➜  ~ docker container run -d -p 8080:80 nginx
f9113d5596825550a954814f9a1853b0249fe7bf5ebb8adf34ec7e2e2a340156
➜  ~ docker container run -d -p 8081:80 nginx
8b680f1418cf7257e44cf9b29e252801d60c4807b51efecf76ce1403a84d6442
➜  ~ docker container ls
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS              PORTS                  NAMES
8b680f1418cf   nginx     "/docker-entrypoint.…"   About a minute ago   Up About a minute   0.0.0.0:8081->80/tcp   crazy_moore
f9113d559682   nginx     "/docker-entrypoint.…"   About a minute ago   Up About a minute   0.0.0.0:8080->80/tcp   nervous_burnell
➜  ~ docker container run --help

Usage:  docker container run [OPTIONS] IMAGE [COMMAND] [ARG...]

Create and run a new container from an image

Aliases:
  docker container run, docker run

Options:
 -p, --publish list                   Publish a container's port(s) to the host
  -P, --publish-all                    Publish all exposed ports to random ports
      --pull string                    Pull image before running ("always", "missing", "never") (default "missing")
```

## 12.Exposing Multiple Ports
```bash
➜  ~ docker container run -d -p 8081:80 -p 8080:80 -p 2000:80 nginx
62d098bc136f07aeb264e39fa91ff4b2c1ba18e302b7abd7819956727685ead9
➜  ~ docker container ls
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS                                                              NAMES
62d098bc136f   nginx     "/docker-entrypoint.…"   5 seconds ago   Up 5 seconds   0.0.0.0:2000->80/tcp, 0.0.0.0:8080->80/tcp, 0.0.0.0:8081->80/tcp   jolly_panini
```
![Alt text](image-24.png)

if the port is already allocated we will get this error.

```bash
➜  ~ docker container run -d -p 8081:80 -p 8080:80 -p 2000:80 nginx
a2847fa225f8da322f5d615d4901f896b1f6e0d6f0dbbefec614c16f967fbf74
docker: Error response from daemon: driver failed programming external connectivity on endpoint eager_faraday (5874a3000d0436a916b9c53b8f0b4ab7565b1aa257327d51a2bedf7f619b26b0): Bind for 0.0.0.0:2000 failed: port is already allocated.
➜  ~
```

![Alt text](image-25.png)

## 13.Naming Containers
```bash
➜  ~ docker container run -d -p 8080:80 --name website nginx
8cabb0886ff161ee3e341b90ae4e06f1996797f32c4d0c8c8e1ed09edae56693
➜  ~ docker container run -d -p 8081:80 --name website nginx
docker: Error response from daemon: Conflict. The container name "/website" is already in use by container "8cabb0886ff161ee3e341b90ae4e06f1996797f32c4d0c8c8e1ed09edae56693". You have to remove (or rename) that container to be able to reuse that name.
See 'docker run --help'.
➜  ~ docker container ls
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS              PORTS                  NAMES
8cabb0886ff1   nginx     "/docker-entrypoint.…"   About a minute ago   Up About a minute   0.0.0.0:8080->80/tcp   website
```

![Alt text](image-26.png)

## 14.Running Container in the background
```bash
➜  ~ docker container run -p 8080:80 --name website nginx
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2023/12/10 05:26:25 [notice] 1#1: using the "epoll" event method
2023/12/10 05:26:25 [notice] 1#1: nginx/1.25.3
2023/12/10 05:26:25 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14)
2023/12/10 05:26:25 [notice] 1#1: OS: Linux 5.15.133.1-microsoft-standard-WSL2
2023/12/10 05:26:25 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2023/12/10 05:26:25 [notice] 1#1: start worker processes
2023/12/10 05:26:25 [notice] 1#1: start worker process 29
2023/12/10 05:26:25 [notice] 1#1: start worker process 30
2023/12/10 05:26:25 [notice] 1#1: start worker process 31
2023/12/10 05:26:25 [notice] 1#1: start worker process 32
2023/12/10 05:26:25 [notice] 1#1: start worker process 33
2023/12/10 05:26:25 [notice] 1#1: start worker process 34
2023/12/10 05:26:25 [notice] 1#1: start worker process 35
2023/12/10 05:26:25 [notice] 1#1: start worker process 36
2023/12/10 05:26:25 [notice] 1#1: start worker process 37
2023/12/10 05:26:25 [notice] 1#1: start worker process 38
2023/12/10 05:26:25 [notice] 1#1: start worker process 39
2023/12/10 05:26:25 [notice] 1#1: start worker process 40
2023/12/10 05:26:25 [notice] 1#1: start worker process 41
2023/12/10 05:26:25 [notice] 1#1: start worker process 42
2023/12/10 05:26:25 [notice] 1#1: start worker process 43
2023/12/10 05:26:25 [notice] 1#1: start worker process 44
172.17.0.1 - - [10/Dec/2023:05:26:39 +0000] "GET /favicon.ico HTTP/1.1" 404 555 "http://localhost:8080/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/119.0.0.0 Safari/537.36" "-"
2023/12/10 05:26:39 [error] 29#29: *2 open() "/usr/share/nginx/html/favicon.ico" failed (2: No such file or directory), client: 172.17.0.1, server: localhost, request: "GET /favicon.ico HTTP/1.1", host: "localhost:8080", referrer: "http://localhost:8080/"
```

```bash
➜  ~ docker container run -p 8081:80 --detach --name website2 nginx
0472c24cdfb910780eaf0fb0339b040fc7954739071cbf7d506fa6c5a9d99db3
```
## 15.Docker Images

![Alt text](image-27.png)

nginx https://hub.docker.com/_/nginx

## 16.Managing Docker Images
```bash
➜  ~ docker image ls
REPOSITORY               TAG         IMAGE ID       CREATED        SIZE
nginx                    latest      10d1f5b58f74   13 hours ago   272MB
amigoscode/2048          latest      9d83e47f0b97   21 hours ago   203MB
docker/getting-started   latest      d79336f4812b   22 hours ago   73.9MB
maven                    latest      2bbd188fef23   22 hours ago   769MB
rust                     1.74.1      32d220ca8c77   22 hours ago   2.05GB
node                     current     db2672e3c200   22 hours ago   1.58GB
python                   latest      6d7fa2d5653e   22 hours ago   1.47GB
openjdk                  22-oracle   6b74a5003ca5   22 hours ago   787MB
mongo                    7.0.4       b679b96ec8a2   22 hours ago   1.04GB
postgres                 16.1        d74fa761bad4   22 hours ago   603MB
```

```bash
➜  ~ docker image

Usage:  docker image COMMAND

Manage images

Commands:
  build       Build an image from a Dockerfile
  history     Show the history of an image
  import      Import the contents from a tarball to create a filesystem image
  inspect     Display detailed information on one or more images
  load        Load an image from a tar archive or STDIN
  ls          List images
  prune       Remove unused images
  pull        Download an image from a registry
  push        Upload an image to a registry
  rm          Remove one or more images
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE

Run 'docker image COMMAND --help' for more information on a command.
```
## 17.Docker Pull
```bash
# to pull an image
docker pull nginx
```

## 18.Inspecting Images
```bash
➜  ~ docker image inspect nginx
[
    {
        "Id": "sha256:10d1f5b58f74683ad34eb29287e07dab1e90f10af243f151bb50aa5dbb4d62ee",
        "RepoTags": [
            "nginx:latest"
        ],
        "RepoDigests": [
            "nginx@sha256:10d1f5b58f74683ad34eb29287e07dab1e90f10af243f151bb50aa5dbb4d62ee"
        ],
        "Parent": "",
        "Comment": "",
        "Created": "2023-11-21T09:05:32.482668371Z",
        "Container": "",
        "ContainerConfig": {
            "Hostname": "",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": null,
            "Cmd": null,
            "Image": "",
            "Volumes": null,
            "WorkingDir": "",
            "Entrypoint": null,
            "OnBuild": null,
            "Labels": null
        },
        "DockerVersion": "master",
        "Author": "",
        "Config": {
            "Hostname": "",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "ExposedPorts": {
                "80/tcp": {}
            },
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
                "NGINX_VERSION=1.25.3",
                "NJS_VERSION=0.8.2",
                "PKG_RELEASE=1~bookworm"
            ],
            "Cmd": [
                "nginx",
                "-g",
                "daemon off;"
            ],
            "Image": "",
            "Volumes": null,
            "WorkingDir": "",
            "Entrypoint": [
                "/docker-entrypoint.sh"
            ],
            "OnBuild": null,
            "Labels": {
                "maintainer": "NGINX Docker Maintainers <docker-maint@nginx.com>"
            },
            "StopSignal": "SIGQUIT"
        },
        "Architecture": "amd64",
        "Os": "linux",
        "Size": 70544635,
        "VirtualSize": 70544635,
        "GraphDriver": {
            "Data": null,
            "Name": "stargz"
        },
        "RootFS": {
            "Type": "layers",
            "Layers": [
                "sha256:92770f546e065c4942829b1f0d7d1f02c2eb1e6acf0d1bc08ef0bf6be4972839",
                "sha256:8ae474e0cc8f5a81405b04143604f78bfac4756c523e276a36921a8c4da36567",
                "sha256:f5525891d9e9b43a95b4aa1f79405087922489eb300864a2683262aae0fa5b3a",
                "sha256:66283570f41bca3619443d121a79e810b8a72849b5329319993e538d563b3e2f",
                "sha256:c2d3ab485d1b375fdd309458d69d93f8eb9aba8472e928efa32d9e5eda631440",
                "sha256:cddc309885a283a35ef142af78bc6f2e9c9db10e1981c4ea9cfb2c00b83e68ff",
                "sha256:0d0e9c83b6f775d68c7517aabf39ec9123ffca29672e3c3f83c5af7fc6aa242b"
            ]
        },
        "Metadata": {
            "LastTagTime": "2023-12-09T16:41:56.408160048Z"
        }
    }
]
```

## 19.Docker Architecture

![Alt text](image-28.png)

## 20.Docker Daemon

![Alt text](image-29.png)

![Alt text](image-30.png)

![Alt text](image-31.png)


```bash
➜  ~ cd ~/.docker
➜  .docker ls
config.json  contexts  desktop  features.json  run  scan
➜  .docker cat config.json
{
  "credsStore": "desktop.exe"
}
➜  .docker cat features.json
cat: features.json: No such file or directory
➜  .docker cd run
➜  run ls
docker-cli-api.sock
```

## 21.Volumes

![Alt text](image-32.png)

![Alt text](image-33.png)



```bash
➜  ~ docker run bash bash -c "echo foo > bar.txt && cat bar.txt"
Unable to find image 'bash:latest' locally
latest: Pulling from library/bash
5b09e29b769c: Download complete
661ff4d9561e: Download complete
a670d36e65dd: Download complete
Digest: sha256:9e21bb4e3753afe899f2fcff86ffe18e82843d8cbee0647635f3cb01715aca5b
Status: Downloaded newer image for bash:latest
foo
➜  ~ docker run bash bash -c "cat bar.txt"
cat: can't open 'bar.txt': No such file or directory
➜  ~
```

![Alt text](image-34.png)

## 22.Bind Mount Volumes

![Alt text](image-35.png)

## 23.Bind Mount Volumes in Action

```bash
➜  ~ mkdir bind-mount
➜  ~ cd bind-mount
➜  bind-mount pwd
/home/chamara/bind-mount
➜  bind-mount echo $PWD
/home/chamara/bind-mount
➜  bind-mount docker run -v $PWD:/tmp bash \
> bash -c "echo foo > /tmp/bar.txt && cat /tmp/bar.txt"
foo
➜  bind-mount ls
bar.txt
➜  bind-mount docker run -v $PWD:/tmp bash \
bash -c "cat /tmp/bar.txt"
foo
```

## 24.Using Vomules for Local Dev
```bash

```

```bash

```
## 25.Docker Volumes
```bash

```

```bash

```
## 26.TMPFS Mount
```bash

```

```bash

```
## 27.Dockerfile
```bash

```

```bash

```
## 28.Creating Dockerfile
```bash

```

```bash

```
## 29.Building DockerImages
```bash

```

```bash

```
## 30.Running a container from Custom Image
```bash

```

```bash

```
## 31.Investigate Container file system
```bash

```

```bash

```
## 32.Buliding ExpressJS API
```bash

```

```bash

```
## 33.Dockerfile and Building image for user-api
```bash

```

```bash

```
## 34.Running Container for user-api image
```bash

```

```bash

```
## 35.Exploring Dockerfiles
```bash

```

```bash

```
## 36.Dockerfile reference
```bash

```

```bash

```
## 37.Pulling Images using a Specifc Tag
```bash

```

```bash

```
## 38.Creating tags
```bash

```

```bash

```
## 39.Creating Version 2 of the Dashboard
```bash

```

```bash

```
## 40.Never Run Latest In Production
```bash

```

```bash

```
## 41.Image Variants
```bash

```

```bash

```
## 42.Docker Registries
```bash

```

```bash

```
## 43.Docker Login
```bash

```

```bash

```
## 44.Docker push
```bash

```

```bash

```
## 45.Docker Inpect
```bash

```

```bash

```
## 46.Logs
```bash

```

```bash

```
## 47.Running commands in Containers
```bash

```

```bash

```
## 48.How to comunicate between containers
```bash

```

```bash

```
## 49.Docker Network
```bash

```

```bash

```
## 50.MongoDB Container
```bash

```

```bash

```
## 51.MongoExpress
```bash

```

```bash

```
## 52.Understanding Container Communication
```bash

```

```bash

```
## 53.Another example
```bash

```

```bash

```
## 54.What is Docker Compose
```bash

```

```bash

```
## 55.Docker Compose cmd
```bash

```

```bash

```
## 56.Services
```bash

```

```bash

```
## 57.Docker Network
```bash

```

```bash

```
## 58.Docker Compose Up
```bash

```

```bash

```
## 59.Exploring docker compose commands
```bash

```

```bash

```
## 60.Docker Volume
```bash

```

```bash

```
## 61.Docker Compose Documentation
```bash

```

```bash

```
## 62.Docker scan
```bash

```

```bash

```
## 63.Trivy
```bash

```

```bash

```
## 64.Distroless Images
```bash

```

```bash

```
## 65.Security Best Practices
```bash

```

```bash

```



