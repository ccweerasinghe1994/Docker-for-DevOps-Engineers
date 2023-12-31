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

host files

![Alt text](image-36.png)

```bash
➜  ~ docker container run -p 8080:80 -d -v $PWD:/usr/share/nginx/html --name dashbord nginx
```

![Alt text](image-37.png)


## 25.Docker Volumes

![Alt text](image-39.png)

```bash
➜  ~ docker volume --help

Usage:  docker volume COMMAND

Manage volumes

Commands:
  create      Create a volume
  inspect     Display detailed information on one or more volumes
  ls          List volumes
  prune       Remove unused local volumes
  rm          Remove one or more volumes

Run 'docker volume COMMAND --help' for more information on a command.
➜  ~ docker volume create vol1
vol1
➜  ~ docker volume ls
DRIVER    VOLUME NAME
local     vol1
➜  ~ docker volume inspect vol1
[
    {
        "CreatedAt": "2023-12-11T04:57:15Z",
        "Driver": "local",
        "Labels": null,
        "Mountpoint": "/var/lib/docker/volumes/vol1/_data",
        "Name": "vol1",
        "Options": null,
        "Scope": "local"
    }
]
```
## 26.TMPFS Mount

![Alt text](image-40.png)

## 27.Dockerfile

![Alt text](image-41.png)

![Alt text](image-42.png)

## 28.Creating Dockerfile

```Dockerfile
FROM nginx

COPY . /usr/share/nginx/html

```

## 29.Building DockerImages
```bash
➜ docker image build . -t dashbord
[+] Building 16.6s (8/8) FINISHED                                                                                                                                docker:default
 => [internal] load build definition from Dockerfile                                                                                                                       0.1s
 => => transferring dockerfile: 87B                                                                                                                                        0.0s
 => [internal] load metadata for docker.io/library/nginx:latest                                                                                                            1.9s
 => [auth] library/nginx:pull token for registry-1.docker.io                                                                                                               0.0s
 => [internal] load .dockerignore                                                                                                                                          0.1s
 => => transferring context: 2B                                                                                                                                            0.0s
 => [internal] load build context                                                                                                                                         12.1s
 => => transferring context: 18.30MB                                                                                                                                      12.0s
 => [1/2] FROM docker.io/library/nginx:latest@sha256:10d1f5b58f74683ad34eb29287e07dab1e90f10af243f151bb50aa5dbb4d62ee                                                      0.3s
 => => resolve docker.io/library/nginx:latest@sha256:10d1f5b58f74683ad34eb29287e07dab1e90f10af243f151bb50aa5dbb4d62ee                                                      0.0s
 => [2/2] COPY . /usr/share/nginx/html                                                                                                                                     0.5s
 => exporting to image                                                                                                                                                     1.6s
 => => exporting layers                                                                                                                                                    1.0s
 => => exporting manifest sha256:3beed1508e6d20a781ab11da73caf8823a574b3594229718087b9d0817c9c2fb                                                                          0.0s
 => => exporting config sha256:5e11e96eee6841d8ed9e7d1e2e08e131c63fdd939b3f1af7cdfeaae5d86f79aa                                                                            0.0s
 => => exporting attestation manifest sha256:e6a51ed6efc75b779864a9158aacdfa1ebb6aa42cd97dd8b38c6b121c77245e2                                                              0.0s
 => => exporting manifest list sha256:cd810e3693f49e157b13d0065771fdf85d6be1a0043fdc7d3a1339ca2cf7f1eb                                                                     0.0s
 => => naming to docker.io/library/dashbord:latest                                                                                                                         0.0s
 => => unpacking to docker.io/library/dashbord:latest
```

![Alt text](image-43.png)

## 30.Running a container from Custom Image
```bash
➜ docker container run -d -p 8080:80 dashbord            
66c72c261918846439b8dc9f146e484befc18585c94d11bb7133b3cd5f53f626
```
![Alt text](image-44.png)


## 31.Investigate Container file system
```bash
➜  b1ed4d3ce61fdd78e8a3513dbb4a9dcb91a6302a5caea0f3373cf1451dd810ec docker container exec -it flamboyant_noyce sh
# ls
bin  boot  dev  docker-entrypoint.d  docker-entrypoint.sh  etc  home  lib  lib32  lib64  libx32  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
# cd us
sh: 2: cd: can't cd to us
# cd usr/share/nginx/html && ls
404.html    LICENSE          blank.html    charts.html           gulpfile.js  js                 package.json   tables.html               utilities-color.html
50x.html    PRO_UPGRADE.txt  buttons.html  css                   img          login.html         register.html  utilities-animation.html  utilities-other.html
Dockerfile  README.md        cards.html    forgot-password.html  index.html   package-lock.json  scss           utilities-border.html     vendor
# ls -a   
.                .travis.yml  LICENSE          buttons.html  forgot-password.html  js                 register.html             utilities-border.html
..               404.html     PRO_UPGRADE.txt  cards.html    gulpfile.js           login.html         scss                      utilities-color.html
.browserslistrc  50x.html     README.md        charts.html   img                   package-lock.json  tables.html               utilities-other.html
.gitignore       Dockerfile   blank.html       css           index.html            package.json       utilities-animation.html  vendor
# cat Dockerfile
FROM nginx

COPY . /usr/share/nginx/html



# 
```

## 32.Buliding ExpressJS API

![Alt text](image-45.png)

```js
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
    res.send('Hello, world!');
});

app.get('/api/v1/users', (req, res) => {
    // Logic to fetch users from the database or any other data source
    const users = [
        { id: 1, name: 'John Doe' },
        { id: 2, name: 'Jane Smith' },
        { id: 3, name: 'Bob Johnson' }
    ];
    
    res.json(users);
});


app.listen(port, () => {
    console.log(`Server is running on port ${port}`);
});

```

```bash
# initialize node project

➜  user-api docker run -w /src -v $PWD:/src --rm node:current npm init -y
Wrote to /src/package.json:

{
  "name": "src",
  "version": "1.0.0",
  "description": "",
  "main": "server.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node server.js"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}

# let's install express

➜  user-api docker run -w /src -v $PWD:/src --rm node:current npm i express

added 62 packages, and audited 63 packages in 3s

11 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
npm notice
npm notice New patch version of npm available! 10.2.4 -> 10.2.5
npm notice Changelog: <https://github.com/npm/cli/releases/tag/v10.2.5>
npm notice Run `npm install -g npm@10.2.5` to update!
npm notice
```

## 33.Dockerfile and Building image for user-api

![Alt text](image-48.png)

```bash
➜  user-api docker image build -f ./Dockerfile.test -t user-api-manual .
[+] Building 6.1s (10/10) FINISHED                                                                                                                               docker:default
 => [internal] load build definition from Dockerfile.test                                                                                                                  0.0s
 => => transferring dockerfile: 136B                                                                                                                                       0.0s 
 => [internal] load metadata for docker.io/library/node:current                                                                                                            2.2s
 => [auth] library/node:pull token for registry-1.docker.io                                                                                                                0.0s
 => [internal] load .dockerignore                                                                                                                                          0.0s
 => => transferring context: 672B                                                                                                                                          0.0s 
 => [1/4] FROM docker.io/library/node:current@sha256:db2672e3c200b85e0b813cdb294fac16764711d7a66b41315e6261f2231f2331                                                      0.3s 
 => => resolve docker.io/library/node:current@sha256:db2672e3c200b85e0b813cdb294fac16764711d7a66b41315e6261f2231f2331                                                      0.0s 
 => [internal] load build context                                                                                                                                          0.1s 
 => => transferring context: 101B                                                                                                                                          0.0s 
 => [2/4] WORKDIR /src                                                                                                                                                     0.1s
 => [3/4] ADD . .                                                                                                                                                          0.1s
 => [4/4] RUN npm install                                                                                                                                                  2.1s
 => exporting to image                                                                                                                                                     0.9s
 => => exporting layers                                                                                                                                                    0.4s 
 => => exporting manifest sha256:f3af8f0487eff1dd719b18f74dde478d33ccbea7d14b6af414ebdc9e2ccfaddc                                                                          0.0s
 => => exporting config sha256:e98bcececce977e22a83bb7d7003a739bde8be7c294c489178d11e5caf599d39                                                                            0.0s
 => => exporting attestation manifest sha256:c6de45cf0855937580025088c01da68adefae0aeb814db701c269ad95b63e116                                                              0.0s
 => => exporting manifest list sha256:d0c00cb8ef78693f21c2bfecfaac66911dd9819c643b287f7c2cf4ac68fa6c4a                                                                     0.0s 
 => => naming to docker.io/library/user-api-manual:latest                                                                                                                  0.0s
 => => unpacking to docker.io/library/user-api-manual:latest
```

![Alt text](image-46.png)

## 34.Running Container for user-api image
```bash
➜ docker container run -d -p 3000:8080 --name=user-api-manual user-api-manual  
8a3dac240a06f3818782b8028254c03406110602a74903d2e8b253cdf7cd505d
```

![Alt text](image-47.png)

## 35.Exploring Dockerfiles

node https://github.com/nodejs/docker-node/blob/6e6de6d890fce6946236cf403b0d5d5b33178e61/21/alpine3.18/Dockerfile


## 36.Dockerfile reference

https://docs.docker.com/engine/reference/builder/

## 37.Pulling Images using a Specifc Tag
```bash

➜ docker pull nginx:1.25.3

```

## 38.Creating tags
```bash
➜  ~ docker image tag dashbord:latest dashbord:1
➜  ~ docker images
REPOSITORY               TAG         IMAGE ID       CREATED        SIZE
user-api-manual          latest      d0c00cb8ef78   20 hours ago   1.59GB
user-api-server          latest      7236b52ec136   21 hours ago   204MB
dashbord                 1           cd810e3693f4   24 hours ago   302MB
dashbord                 latest      cd810e3693f4   24 hours ago   302MB
bash                     latest      9e21bb4e3753   27 hours ago   21.3MB
nginx                    latest      10d1f5b58f74   2 days ago     272MB
amigoscode/2048          latest      9d83e47f0b97   2 days ago     203MB
docker/getting-started   latest      d79336f4812b   2 days ago     73.9MB
maven                    latest      2bbd188fef23   2 days ago     769MB
rust                     1.74.1      32d220ca8c77   2 days ago     2.05GB
node                     current     db2672e3c200   2 days ago     1.58GB
python                   latest      6d7fa2d5653e   2 days ago     1.47GB
openjdk                  22-oracle   6b74a5003ca5   2 days ago     787MB
mongo                    7.0.4       b679b96ec8a2   2 days ago     1.04GB
postgres                 16.1        d74fa761bad4   2 days ago     603MB
```
## 39.Creating Version 2 of the Dashboard

```bash
➜ docker image build -t dashbord:2 -t dashbord:latest .
[+] Building 37.5s (8/8) FINISHED                                                                                                                docker:default
 => [internal] load build definition from Dockerfile                                                                                                       0.1s
 => => transferring dockerfile: 85B                                                                                                                        0.0s
 => [internal] load metadata for docker.io/library/nginx:latest                                                                                           17.9s
 => [auth] library/nginx:pull token for registry-1.docker.io                                                                                               0.0s
 => [internal] load .dockerignore                                                                                                                          0.0s
 => => transferring context: 2B                                                                                                                            0.0s
 => [internal] load build context                                                                                                                         16.2s
 => => transferring context: 158.91kB                                                                                                                     16.2s
 => CACHED [1/2] FROM docker.io/library/nginx:latest@sha256:10d1f5b58f74683ad34eb29287e07dab1e90f10af243f151bb50aa5dbb4d62ee                               0.1s
 => => resolve docker.io/library/nginx:latest@sha256:10d1f5b58f74683ad34eb29287e07dab1e90f10af243f151bb50aa5dbb4d62ee                                      0.0s
 => [2/2] COPY . /usr/share/nginx/html                                                                                                                     1.2s
 => exporting to image                                                                                                                                     1.8s
 => => exporting layers                                                                                                                                    1.0s
 => => exporting manifest sha256:bf2aee8f19be121cd0fcb2c66a9b3d511214891352d2da5672c5ba3bee0c6ffd                                                          0.0s
 => => exporting config sha256:6a363986f025f5fc5285add777b87a89bcb5ca1a10772efbeb5ccb013bcd05ed                                                            0.0s
 => => exporting attestation manifest sha256:3566ed6c772dc4a4bb183dae6acb25ce4839faab107e5045d0bbfa2b13fe01ad                                              0.0s
 => => exporting manifest list sha256:34407820e5fa0d40034e7470ba20be1ef88476e236b5849e60c8bd0bc80d2205                                                     0.0s
 => => naming to docker.io/library/dashbord:2                                                                                                              0.0s
 => => unpacking to docker.io/library/dashbord:2                                                                                                           0.5s 
 => => naming to docker.io/library/dashbord:latest                                                                                                         0.0s 
 => => unpacking to docker.io/library/dashbord:latest                                                                                                      0.0s 
➜ docker images
REPOSITORY               TAG         IMAGE ID       CREATED         SIZE
dashbord                 1           cd810e3693f4   9 minutes ago   302MB
user-api-manual          latest      d0c00cb8ef78   21 hours ago    1.59GB
user-api-server          latest      7236b52ec136   21 hours ago    204MB
dashbord                 2           34407820e5fa   24 hours ago    302MB
dashbord                 latest      34407820e5fa   24 hours ago    302MB
bash                     latest      9e21bb4e3753   27 hours ago    21.3MB
nginx                    latest      10d1f5b58f74   2 days ago      272MB
amigoscode/2048          latest      9d83e47f0b97   2 days ago      203MB
docker/getting-started   latest      d79336f4812b   2 days ago      73.9MB
maven                    latest      2bbd188fef23   2 days ago      769MB
rust                     1.74.1      32d220ca8c77   2 days ago      2.05GB
node                     current     db2672e3c200   2 days ago      1.58GB
python                   latest      6d7fa2d5653e   2 days ago      1.47GB
openjdk                  22-oracle   6b74a5003ca5   2 days ago      787MB
mongo                    7.0.4       b679b96ec8a2   2 days ago      1.04GB
postgres                 16.1        d74fa761bad4   2 days ago      603MB
➜ docker container run -d -p 8080:80 dashbord:1
4587da514017b3e52d75b4ef91906f2c63c61eb8140de2d0483beb66937902f9
➜ docker container run -d -p 8080:80 dashbord:2
3bff7093bf0006b8724035b4ec76396df48956c9199bdb0546c378a1ceffe043
docker: Error response from daemon: driver failed programming external connectivity on endpoint agitated_chatelet (b5476f60ceaaed7e924359c58dedc3d122d2e24ada06c31eb2f6cee569e4443c): Bind for 0.0.0.0:8080 failed: port is already allocated.
➜ docker container run -d -p 8081:80 dashbord:2
5b93dadd14cadd8d56292db8a51e3f7ba59c73a2361fd947bedab4453fd87995
➜ docker container run -d -p 8082:80 dashbord:latest
63bbf93eba68cc25d1a0cc64a99936a5266e22026461cf72b29e34d1bad6b037
```

![Alt text](image-49.png)

![Alt text](image-50.png)


## 40.Never Run Latest In Production

when you run latest in production you are not in control of the changes that are going to be made to your application.
always use specific version of your application.

## 41.Image Variants

let's take node docker image as an example
- slim means it has less features
- alpine means it has less features and it's smaller in size
- buster means it is based on debian buster
- stretch means it is based on debian stretch
- jessie means it is based on debian jessie
- windowsservercore means it is based on windows server core
- nanoserver means it is based on windows nano server
- lts means it is based on long term support version of node
- current means it is based on current version of node


## 42.Docker Registries
![Alt text](image-51.png)

we have to kind of registries

- public/private registries
  - e.g docker hub
  - e.g github packages
  - e.g amazon ecr
  - e.g google cloud registry
  - e.g azure container registry


## 43.Docker Login
```bash
➜  ~ docker login --help
Log in to a Docker registry or cloud backend.
If no registry server is specified, the default is defined by the daemon.

Usage:
  docker login [OPTIONS] [SERVER] [flags]
  docker login [command]

Available Commands:
  azure       Log in to azure

Flags:
  -h, --help              Help for login
  -p, --password string   password
      --password-stdin    Take the password from stdin
  -u, --username string   username

Use "docker login [command] --help" for more information about a command.
```

## 44.Docker push
```bash
➜  test docker image build -t wchamara/test .
[+] Building 14.1s (6/6) FINISHED                                                                                                                docker:default
 => [internal] load build definition from Dockerfile                                                                                                       0.1s
 => => transferring dockerfile: 54B                                                                                                                        0.0s 
 => [internal] load metadata for docker.io/library/alpine:3                                                                                               13.4s 
 => [auth] library/alpine:pull token for registry-1.docker.io                                                                                              0.0s
 => [internal] load .dockerignore                                                                                                                          0.1s
 => => transferring context: 2B                                                                                                                            0.0s 
 => [1/1] FROM docker.io/library/alpine:3@sha256:51b67269f354137895d43f3b3d810bfacd3945438e94dc5ac55fdac340352f48                                          0.1s
 => => resolve docker.io/library/alpine:3@sha256:51b67269f354137895d43f3b3d810bfacd3945438e94dc5ac55fdac340352f48                                          0.1s 
 => exporting to image                                                                                                                                     0.2s
 => => exporting layers                                                                                                                                    0.0s 
 => => exporting manifest sha256:87580ecea06956c13c0c831e1b3744c48e16eee48a32537829713968d9e7bf22                                                          0.0s 
 => => exporting config sha256:26fc80ffe8cc273858f455668aed8676cd9593966be3dee4d53f0647e054e923                                                            0.0s 
 => => exporting attestation manifest sha256:bd0d0d1946a32cf890de38730b96e9301eeac7d0c7b9ce706b8eeaf7097658c4                                              0.0s
 => => exporting manifest list sha256:099bec397e602e9dbc749666b7079df3596b8ae74712bd5307ee7a3587ab2ca9                                                     0.0s 
 => => naming to docker.io/wchamara/test:latest                                                                                                            0.0s 
 => => unpacking to docker.io/wchamara/test:latest                                                                                                         0.0s
➜  test docker push wchamara/test:latest 
The push refers to repository [docker.io/wchamara/test]
661ff4d9561e: Mounted from library/bash
479dc01cbc9e: Pushed
latest: digest: sha256:099bec397e602e9dbc749666b7079df3596b8ae74712bd5307ee7a3587ab2ca9 size: 855
```

![Alt text](image-53.png)

![Alt text](image-52.png)

## 45.Docker Inpect
```bash
➜  test docker inspect dashbord   
[
    {
        "Id": "sha256:34407820e5fa0d40034e7470ba20be1ef88476e236b5849e60c8bd0bc80d2205",
        "RepoTags": [
            "dashbord:2",
            "dashbord:latest"
        ],
        "RepoDigests": [
            "dashbord@sha256:34407820e5fa0d40034e7470ba20be1ef88476e236b5849e60c8bd0bc80d2205",
            "dashbord@sha256:34407820e5fa0d40034e7470ba20be1ef88476e236b5849e60c8bd0bc80d2205"
        ],
        "Parent": "",
        "Comment": "buildkit.dockerfile.v0",
        "Created": "2023-12-12T05:57:27.960787737Z",
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
        "Size": 76282518,
        "VirtualSize": 76282518,
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
                "sha256:0d0e9c83b6f775d68c7517aabf39ec9123ffca29672e3c3f83c5af7fc6aa242b",
                "sha256:23791485d1aec0abd12d013f7b1ed62b8fe7a4eaf69c697e413419db67195b6b"
            ]
        },
        "Metadata": {
            "LastTagTime": "2023-12-12T05:57:29.67756694Z"
        }
    }
]
```

for debugging purposes we can use docker inspect to see what is inside the image or container

## 46.Logs
```bash
➜  test docker container run -d -p 8080:80 dashbord:2
20e21714eda3e511a33aea7ba3dd55d9d277b427c1489d3ae23f2e25a3b83a53
➜  test docker container ls
CONTAINER ID   IMAGE        COMMAND                  CREATED          STATUS          PORTS                  NAMES
20e21714eda3   dashbord:2   "/docker-entrypoint.…"   33 seconds ago   Up 32 seconds   0.0.0.0:8080->80/tcp   wizardly_carver
➜  test docker container logs wizardly_carver 
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2023/12/12 08:12:49 [notice] 1#1: using the "epoll" event method
2023/12/12 08:12:49 [notice] 1#1: nginx/1.25.3
2023/12/12 08:12:49 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14) 
2023/12/12 08:12:49 [notice] 1#1: OS: Linux 5.15.133.1-microsoft-standard-WSL2
2023/12/12 08:12:49 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2023/12/12 08:12:49 [notice] 1#1: start worker processes
2023/12/12 08:12:49 [notice] 1#1: start worker process 29
2023/12/12 08:12:49 [notice] 1#1: start worker process 30
2023/12/12 08:12:49 [notice] 1#1: start worker process 31
2023/12/12 08:12:49 [notice] 1#1: start worker process 32
2023/12/12 08:12:49 [notice] 1#1: start worker process 33
2023/12/12 08:12:49 [notice] 1#1: start worker process 34
2023/12/12 08:12:49 [notice] 1#1: start worker process 35
2023/12/12 08:12:49 [notice] 1#1: start worker process 36
2023/12/12 08:12:49 [notice] 1#1: start worker process 37
2023/12/12 08:12:49 [notice] 1#1: start worker process 38
2023/12/12 08:12:49 [notice] 1#1: start worker process 39
2023/12/12 08:12:49 [notice] 1#1: start worker process 40
2023/12/12 08:12:49 [notice] 1#1: start worker process 41
2023/12/12 08:12:49 [notice] 1#1: start worker process 42
2023/12/12 08:12:49 [notice] 1#1: start worker process 43
2023/12/12 08:12:49 [notice] 1#1: start worker process 44
➜  test docker container logs wizardly_carver -f
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2023/12/12 08:12:49 [notice] 1#1: using the "epoll" event method
2023/12/12 08:12:49 [notice] 1#1: nginx/1.25.3
2023/12/12 08:12:49 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14)
2023/12/12 08:12:49 [notice] 1#1: OS: Linux 5.15.133.1-microsoft-standard-WSL2
2023/12/12 08:12:49 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2023/12/12 08:12:49 [notice] 1#1: start worker processes
2023/12/12 08:12:49 [notice] 1#1: start worker process 29
2023/12/12 08:12:49 [notice] 1#1: start worker process 30
2023/12/12 08:12:49 [notice] 1#1: start worker process 31
2023/12/12 08:12:49 [notice] 1#1: start worker process 32
2023/12/12 08:12:49 [notice] 1#1: start worker process 33
2023/12/12 08:12:49 [notice] 1#1: start worker process 34
2023/12/12 08:12:49 [notice] 1#1: start worker process 35
2023/12/12 08:12:49 [notice] 1#1: start worker process 36
2023/12/12 08:12:49 [notice] 1#1: start worker process 37
2023/12/12 08:12:49 [notice] 1#1: start worker process 38
2023/12/12 08:12:49 [notice] 1#1: start worker process 39
2023/12/12 08:12:49 [notice] 1#1: start worker process 40
2023/12/12 08:12:49 [notice] 1#1: start worker process 41
2023/12/12 08:12:49 [notice] 1#1: start worker process 42
2023/12/12 08:12:49 [notice] 1#1: start worker process 43
2023/12/12 08:12:49 [notice] 1#1: start worker process 44
172.17.0.1 - - [12/Dec/2023:08:14:07 +0000] "GET / HTTP/1.1" 200 31451 "-" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36 Edg/120.0.0.0" "-"
```

## 47.Running commands in Containers
```bash
➜  test docker container exec --help 

Usage:  docker container exec [OPTIONS] CONTAINER COMMAND [ARG...]

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
```

```bash
➜  test docker container exec wizardly_carver env  
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
HOSTNAME=20e21714eda3
NGINX_VERSION=1.25.3
NJS_VERSION=0.8.2
PKG_RELEASE=1~bookworm
HOME=/root
➜  test docker container exec wizardly_carver pwd
/
➜  test docker container exec wizardly_carver ls /
bin
boot
dev
docker-entrypoint.d
docker-entrypoint.sh
etc
home
lib
lib32
lib64
libx32
media
mnt
opt
proc
root
run
sbin
srv
sys
tmp
usr
var
➜  test docker container exec -it wizardly_carver sh
# ls
bin  boot  dev  docker-entrypoint.d  docker-entrypoint.sh  etc  home  lib  lib32  lib64  libx32  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
# top
sh: 2: top: not found
# df
Filesystem      1K-blocks    Used Available Use% Mounted on
overlay        1055762868 7554460 994504936   1% /
tmpfs               65536       0     65536   0% /dev
tmpfs             3911840       0   3911840   0% /sys/fs/cgroup
shm                 65536       0     65536   0% /dev/shm
/dev/sde       1055762868 7554460 994504936   1% /etc/hosts
tmpfs             3911840       0   3911840   0% /proc/acpi
tmpfs             3911840       0   3911840   0% /sys/firmware
# ^C
# ^C
# exit
➜  test docker container exec -it wizardly_carver bash
root@20e21714eda3:/# ls
bin  boot  dev  docker-entrypoint.d  docker-entrypoint.sh  etc  home  lib  lib32  lib64  libx32  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@20e21714eda3:/#
```
## 48.How to comunicate between containers
![Alt text](image-54.png)

![Alt text](image-55.png)

## 49.Docker Network
```bash
➜  test docker network --help 

Usage:  docker network COMMAND

Manage networks

Commands:
  connect     Connect a container to a network
  create      Create a network
  disconnect  Disconnect a container from a network
  inspect     Display detailed information on one or more networks
  ls          List networks
  prune       Remove all unused networks
  rm          Remove one or more networks

Run 'docker network COMMAND --help' for more information on a command.
```

```bash
➜  test docker network create mongo
4097ebd8c91b22ee4eb8449fff8dec572c5695380eab01ed803dbcb434d82119
➜  test docker network ls 
NETWORK ID     NAME      DRIVER    SCOPE
aaaeaa8ba9f6   bridge    bridge    local
b732a89383fb   host      host      local
4097ebd8c91b   mongo     bridge    local
fdf2c02af788   none      null      local
➜  test docker network inspect mongo 
[
    {
        "Name": "mongo",
        "Id": "4097ebd8c91b22ee4eb8449fff8dec572c5695380eab01ed803dbcb434d82119",
        "Created": "2023-12-12T09:47:58.087509386Z",
        "Scope": "local",
        "Driver": "bridge",
        "EnableIPv6": false,
        "IPAM": {
            "Driver": "default",
            "Options": {},
            "Config": [
                {
                    "Subnet": "172.20.0.0/16",
                    "Gateway": "172.20.0.1"
                }
            ]
        },
        "Internal": false,
        "Attachable": false,
        "Ingress": false,
        "ConfigFrom": {
            "Network": ""
        },
        "ConfigOnly": false,
        "Containers": {},
        "Options": {},
        "Labels": {}
    }
]
```

https://docs.docker.com/network/drivers/

## 50.MongoDB Container
```bash
➜  test docker container run -p 2707:2707 -d --network mongo --name mongo \
        -e MONGO_INITDB_ROOT_USERNAME=username \
        -e MONGO_INITDB_ROOT_PASSWORD=123 \
        mongo:7.0.4
389cd52157b59ff8aa5fb1f448a95fadfcc4488e41a35964a8cb89f19be91e4e
➜  test docker container logs mongo 
about to fork child process, waiting until server is ready for connections.
```

```bash
➜  test docker container logs mongo 
about to fork child process, waiting until server is ready for connections.
forked process: 28

{"t":{"$date":"2023-12-12T09:59:22.568+00:00"},"s":"I",  "c":"CONTROL",  "id":20698,   "ctx":"main","msg":"***** SERVER RESTARTED *****"}
{"t":{"$date":"2023-12-12T09:59:22.570+00:00"},"s":"I",  "c":"CONTROL",  "id":23285,   "ctx":"main","msg":"Automatically disabling TLS 1.0, to force-enable TLS 1.0 specify --sslDisabledProtocols 'none'"}
{"t":{"$date":"2023-12-12T09:59:22.570+00:00"},"s":"I",  "c":"NETWORK",  "id":4915701, "ctx":"main","msg":"Initialized wire specification","attr":{"spec":{"incomingExternalClient":{"minWireVersion":0,"maxWireVersion":21},"incomingInternalClient":{"minWireVersion":0,"maxWireVersion":21},"outgoing":{"minWireVersion":6,"maxWireVersion":21},"isInternalClient":true}}}
{"t":{"$date":"2023-12-12T09:59:22.571+00:00"},"s":"I",  "c":"NETWORK",  "id":4648601, "ctx":"main","msg":"Implicit TCP FastOpen unavailable. If TCP FastOpen is required, set tcpFastOpenServer, tcpFastOpenClient, and tcpFastOpenQueueSize."}
{"t":{"$date":"2023-12-12T09:59:22.573+00:00"},"s":"I",  "c":"REPL",     "id":5123008, "ctx":"main","msg":"Successfully registered PrimaryOnlyService","attr":{"service":"TenantMigrationDonorService","namespace":"config.tenantMigrationDonors"}}
{"t":{"$date":"2023-12-12T09:59:22.573+00:00"},"s":"I",  "c":"REPL",     "id":5123008, "ctx":"main","msg":"Successfully registered PrimaryOnlyService","attr":{"service":"TenantMigrationRecipientService","namespace":"config.tenantMigrationRecipients"}}
{"t":{"$date":"2023-12-12T09:59:22.573+00:00"},"s":"I",  "c":"CONTROL",  "id":5945603, "ctx":"main","msg":"Multi threading initialized"}
{"t":{"$date":"2023-12-12T09:59:22.573+00:00"},"s":"I",  "c":"TENANT_M", "id":7091600, "ctx":"main","msg":"Starting TenantMigrationAccessBlockerRegistry"}
{"t":{"$date":"2023-12-12T09:59:22.573+00:00"},"s":"I",  "c":"CONTROL",  "id":4615611, "ctx":"initandlisten","msg":"MongoDB starting","attr":{"pid":28,"port":27017,"dbPath":"/data/db","architecture":"64-bit","host":"389cd52157b5"}}
{"t":{"$date":"2023-12-12T09:59:22.573+00:00"},"s":"I",  "c":"CONTROL",  "id":23403,   "ctx":"initandlisten","msg":"Build Info","attr":{"buildInfo":{"version":"7.0.4","gitVersion":"38f3e37057a43d2e9f41a39142681a76062d582e","openSSLVersion":"OpenSSL 3.0.2 15 Mar 2022","modules":[],"allocator":"tcmalloc","environment":sock"}}
{"t":{"$date":"2023-12-12T09:59:27.740+00:00"},"s":"I",  "c":"NETWORK",  "id":23015,   "ctx":"listener","msg":"Listening on","attr":{"address":"0.0.0.0"}}
{"t":{"$date":"2023-12-12T09:59:27.740+00:00"},"s":"I",  "c":"NETWORK",  "id":23016,   "ctx":"listener","msg":"Waiting for connections","attr":{"port":27017,"ssl":"off"}}
```
## 51.MongoExpress
```bash
docker container run --name mongo-server --network mongo -d -p 8081:8081 \
-e ME_CONFIG_MONGODB_AUTH_USERNAME=username \
-e ME_CONFIG_MONGODB_AUTH_PASSWORD=123 \
-e ME_CONFIG_MONGODB_SERVER=mongo \
-e ME_CONFIG_BASICAUTH_USERNAME=admin \
-e ME_CONFIG_BASICAUTH_PASSWORD=123 \
mongo-express:1.0.0-18
```
http://localhost:8081/

![Alt text](image-56.png)

![Alt text](image-57.png)

## 52.Understanding Container Communication

![Alt text](image-58.png)

![Alt text](image-59.png)

```bash
➜  test docker container run --rm -it --network mongo mongo:7.0.4 sh
# mongosh
Current Mongosh Log ID: 657860fc27e384596d73ded0
Connecting to:          mongodb://127.0.0.1:27017/?directConnection=true&serverSelectionTimeoutMS=2000&appName=mongosh+2.1.0
MongoNetworkError: connect ECONNREFUSED 127.0.0.1:27017
# mongosh --host mongo -u username -p 123
Current Mongosh Log ID: 657861306c70fb464599a69a
Connecting to:          mongodb://<credentials>@mongo:27017/?directConnection=true&appName=mongosh+2.1.0
Using MongoDB:          7.0.4
Using Mongosh:          2.1.0

For mongosh info see: https://docs.mongodb.com/mongodb-shell/


To help improve our products, anonymous usage data is collected and sent to MongoDB periodically (https://www.mongodb.com/legal/privacy-policy).
You can opt-out by running the disableTelemetry() command.

------
   The server generated these startup warnings when booting
   2023-12-12T09:59:26.900+00:00: Using the XFS filesystem is strongly recommended with the WiredTiger storage engine. See http://dochub.mongodb.org/core/prodnotes-filesystem
   2023-12-12T09:59:27.732+00:00: /sys/kernel/mm/transparent_hugepage/enabled is 'always'. We suggest setting it to 'never'
   2023-12-12T09:59:27.732+00:00: vm.max_map_count is too low
------

test> show dbs
admin   100.00 KiB
config  108.00 KiB
local    72.00 KiB
test     48.00 KiB
test>
```

## 53.Another example
create a network called test and connect two containers to it
```bash
➜  test docker network ls 
NETWORK ID     NAME      DRIVER    SCOPE
aaaeaa8ba9f6   bridge    bridge    local
b732a89383fb   host      host      local
4097ebd8c91b   mongo     bridge    local
fdf2c02af788   none      null      local
➜  test docker network create test
7e3ba519f9e5382bfb8ed007912f6d4560ffbee4b74939da91ecf5bdce8bc821
➜  test docker network ls
NETWORK ID     NAME      DRIVER    SCOPE
aaaeaa8ba9f6   bridge    bridge    local
b732a89383fb   host      host      local
4097ebd8c91b   mongo     bridge    local
fdf2c02af788   none      null      local
7e3ba519f9e5   test      bridge    local
➜  test docker network connect test charming_allen 
➜  test docker network connect test ecstatic_chaum 
➜  test docker exec -it charming_allen sh
```
or create new containers with the new network
```bash
➜  test docker container run --name dashbord -d -p 8080:80 --network=test dashbord:2
8ecc2502bb6b9bb881ff24135273c899370e420d43f4fac83ee3fdc3a85864dc
➜  test docker container run --name=user-api -d -p 3000:8080 --network=test user-api-manual
e18e94c7910d24d43ec547c5474767833301e6489815273838a71efcdfca0ba1
➜  test docker exec -it dashbord sh
# curl http://user-api:8080/api/v1/users
[{"id":1,"name":"John Doe"},{"id":2,"name":"Jane Smith"},{"id":3,"name":"Bob Johnson"}]# 
#
```

try to execute curl command from the dashbord container

```bash
➜  test docker exec -it dashbord sh
# curl http://user-api:8080/api/v1/users
[{"id":1,"name":"John Doe"},{"id":2,"name":"Jane Smith"},{"id":3,"name":"Bob Johnson"}]# 
#
```

## 54.What is Docker Compose

![Alt text](image-60.png)

![Alt text](image-61.png)

## 55.Docker Compose cmd

https://docs.docker.com/compose/

```bash
➜  ~ docker compose --help

Usage:  docker compose [OPTIONS] COMMAND

Define and run multi-container applications with Docker.

Options:
      --ansi string                Control when to print ANSI control characters ("never"|"always"|"auto")
                                   (default "auto")
      --compatibility              Run compose in backward compatibility mode
      --dry-run                    Execute command in dry run mode
      --env-file stringArray       Specify an alternate environment file.
  -f, --file stringArray           Compose configuration files
      --parallel int               Control max parallelism, -1 for unlimited (default -1)
      --profile stringArray        Specify a profile to enable
      --progress string            Set type of progress output (auto, tty, plain, quiet) (default "auto")
      --project-directory string   Specify an alternate working directory
                                   (default: the path of the, first specified, Compose file)
  -p, --project-name string        Project name

Commands:
  build       Build or rebuild services
  config      Parse, resolve and render compose file in canonical format
  cp          Copy files/folders between a service container and the local filesystem
  create      Creates containers for a service.
  down        Stop and remove containers, networks
  events      Receive real time events from containers.
  exec        Execute a command in a running container.
  images      List images used by the created containers
  kill        Force stop service containers.
  logs        View output from containers
  ls          List running compose projects
  pause       Pause services
  port        Print the public port for a port binding.
  ps          List containers
  pull        Pull service images
  push        Push service images
  restart     Restart service containers
  rm          Removes stopped service containers
  run         Run a one-off command on a service.
  scale       Scale services
  start       Start services
  stop        Stop services
  top         Display the running processes
  unpause     Unpause services
  up          Create and start containers
  version     Show the Docker Compose version information
  wait        Block until the first service container stops
  watch       Watch build context for service and rebuild/refresh containers when files are updated

Run 'docker compose COMMAND --help' for more information on a command.
```

## 56.Services

```yml
services:
  mongo:
    image: mongo:7.0.4
    container_name: mongo
    ports:
      - 27017:27017
    environment:
      - MONGO_INITDB_ROOT_USERNAME=username
      - MONGO_INITDB_ROOT_PASSWORD=123
  mongo-express:
    image: mongo-express:1.0.0-18
    container_name: mongo-express
    ports:
      - 8081:8081
    environment:
      - ME_CONFIG_MONGODB_AUTH_USERNAME=username
      - ME_CONFIG_MONGODB_AUTH_PASSWORD=123
      - ME_CONFIG_MONGODB_SERVER=mongo
      - ME_CONFIG_BASICAUTH_USERNAME=admin
      - ME_CONFIG_BASICAUTH_PASSWORD=123
    depends_on:
      - mongo
    restart: always

```

## 57.Docker Network
```bash
services:
  mongo:
    image: mongo:7.0.4
    container_name: mongo
    ports:
      - 27017:27017
    environment:
      - MONGO_INITDB_ROOT_USERNAME=username
      - MONGO_INITDB_ROOT_PASSWORD=123
    networks:
      - mongo
  mongo-express:
    image: mongo-express:1.0.0-18
    container_name: mongo-express
    ports:
      - 8081:8081
    environment:
      - ME_CONFIG_MONGODB_AUTH_USERNAME=username
      - ME_CONFIG_MONGODB_AUTH_PASSWORD=123
      - ME_CONFIG_MONGODB_SERVER=mongo
      - ME_CONFIG_BASICAUTH_USERNAME=admin
      - ME_CONFIG_BASICAUTH_PASSWORD=123
    depends_on:
      - mongo
    restart: always
    networks:
      - mongo

networks:
  mongo:
    name: mongo

```
## 58.Docker Compose Up
```bash
➜ ls
docker-compose.yml
➜ docker compose up
[+] Building 0.0s (0/0)                                                                                                                                     docker:default
[+] Running 3/3
 ✔ Network mongo            Created                                                                                                                                   0.1s 
 ✔ Container mongo          Created                                                                                                                                   0.2s 
 ✔ Container mongo-express  Created                                                                                                                                   0.2s 
Attaching to mongo, mongo-express
mongo          | about to fork child process, waiting until server is ready for connections.
mongo          | forked process: 28
```

![Alt text](image-62.png)


## 59.Exploring docker compose commands
```bash
➜  compose docker compose ps
NAME            IMAGE                    COMMAND                  SERVICE         CREATED          STATUS          PORTS
mongo           mongo:7.0.4              "docker-entrypoint.s…"   mongo           15 minutes ago   Up 15 minutes   0.0.0.0:27017->27017/tcp
mongo-express   mongo-express:1.0.0-18   "/sbin/tini -- /dock…"   mongo-express   15 minutes ago   Up 15 minutes   0.0.0.0:8081->8081/tcp
➜  compose docker compose stop
[+] Stopping 2/2
 ✔ Container mongo-express  Stopped                                                                                                                0.4s 
 ✔ Container mongo          Stopped                                                                                                                0.5s 
➜  compose docker compose start
[+] Running 2/2
 ✔ Container mongo          Started                                                                                                                0.4s 
 ✔ Container mongo-express  Started                                                                                                                0.3s 
➜  compose docker compose down 
[+] Running 3/3
 ✔ Container mongo-express  Removed                                                                                                                0.4s 
 ✔ Container mongo          Removed                                                                                                                0.7s 
 ✔ Network mongo            Removed                                                                                                                0.4s 
➜  compose docker compose ls  
NAME                                                STATUS              CONFIG FILES
docker_volumes-backup-extension-desktop-extension   running(1)          C:\Users\ccwee\AppData\Roaming\Docker\extensions\docker_volumes-backup-extension\vm\docker-compose.yaml
➜  compose docker compose ps
NAME      IMAGE     COMMAND   SERVICE   CREATED   STATUS    PORTS
➜  compose docker compose up -d
[+] Building 0.0s (0/0)                                                                                                                  docker:default
[+] Running 3/3
 ✔ Network mongo            Created                                                                                                                0.1s 
 ✔ Container mongo          Started                                                                                                                0.2s 
 ✔ Container mongo-express  Started
```

```bash
➜  compose docker compose logs mongo-express -f
mongo-express  | No custom config.js found, loading config.default.js
mongo-express  | Welcome to mongo-express
mongo-express  | ------------------------
mongo-express  | 
mongo-express  | 
mongo-express  | Mongo Express server listening at http://0.0.0.0:8081
mongo-express  | Server is open to allow connections from anyone (0.0.0.0) 
```
## 60.Docker Volume
```bash
services:
  mongo:
    image: mongo:7.0.4
    container_name: mongo
    ports:
      - 27017:27017
    environment:
      - MONGO_INITDB_ROOT_USERNAME=username
      - MONGO_INITDB_ROOT_PASSWORD=123
    networks:
      - mongo
    volumes:
      - data:/data/db
  mongo-express:
    image: mongo-express:1.0.0-18
    container_name: mongo-express
    ports:
      - 8081:8081
    environment:
      - ME_CONFIG_MONGODB_AUTH_USERNAME=username
      - ME_CONFIG_MONGODB_AUTH_PASSWORD=123
      - ME_CONFIG_MONGODB_SERVER=mongo
      - ME_CONFIG_BASICAUTH_USERNAME=admin
      - ME_CONFIG_BASICAUTH_PASSWORD=123
    depends_on:
      - mongo
    restart: always
    networks:
      - mongo

volumes:
  data: {}

networks:
  mongo:
    name: mongo

```

```bash
➜ docker compose up -d
[+] Building 0.0s (0/0)                                                                                                                  docker:default
[+] Running 4/4
 ✔ Network mongo            Created                                                                                                                0.1s 
 ✔ Volume "compose_data"    Created                                                                                                                0.0s 
 ✔ Container mongo          Started                                                                                                                0.2s 
 ✔ Container mongo-express  Started 
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



