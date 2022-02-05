## Exercise 1.1

(base) anniinasainio@Anniinas-MacBook-Air ~ % docker ps -a
```
CONTAINER ID   IMAGE        COMMAND                  CREATED             STATUS                      PORTS                    NAMES
e9cbe53f5b84   nginx        "/docker-entrypoint.…"   4 minutes ago       Up 4 minutes                80/tcp                   agitated_curran
4459a4c1fad2   nginx        "/docker-entrypoint.…"   4 minutes ago       Exited (0) 4 seconds ago                             hungry_ramanujan
fd03478272e7   nginx        "/docker-entrypoint.…"   4 minutes ago       Exited (0) 14 seconds ago                            vibrant_burnell                     
```

##  Exercise 1.2

(base) anniinasainio@Anniinas-MacBook-Air ~ % docker ps -a
```
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
```
(base) anniinasainio@Anniinas-MacBook-Air ~ % docker images  
```
REPOSITORY    TAG        IMAGE ID       CREATED         SIZE
```


## Exercise 1.3
root@aa630c5029cf:/usr/src/app# tail -f ./text.log
```
2022-02-05 15:01:07 +0000 UTC
2022-02-05 15:01:09 +0000 UTC
2022-02-05 15:01:11 +0000 UTC
2022-02-05 15:01:13 +0000 UTC
2022-02-05 15:01:15 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
2022-02-05 15:01:17 +0000 UTC
2022-02-05 15:01:19 +0000 UTC
2022-02-05 15:01:21 +0000 UTC
2022-02-05 15:01:23 +0000 UTC
2022-02-05 15:01:25 +0000 UTC```
```

## Exercise 1.4
```
(base) anniinasainio@Anniinas-MacBook-Air ~ % docker run ubuntu 
(base) anniinasainio@Anniinas-MacBook-Air ~ % docker ps -a    

CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS               PORTS     NAMES
04723f1c5812   ubuntu         "bash"                   27 minutes ago   Up 27 minutes                  nifty_jennings

(base) anniinasainio@Anniinas-MacBook-Air ~ % docker exec -it nifty_jennings bash

root@04723f1c5812:/# apt-get update; apt-get install curl
root@04723f1c5812:/# curl helsinki.fi

<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="https://www.helsinki.fi/">here</a>.</p>
</body></html>
```

## Exercise 1.5
```

(base) anniinasainio@Anniinas-MacBook-Air ~ % docker images
REPOSITORY                           TAG        IMAGE ID       CREATED         SIZE
devopsdockeruh/simple-web-service    ubuntu     4e3362e907d5   10 months ago   83MB
devopsdockeruh/simple-web-service    alpine     fd312adc88e0   10 months ago   15.7MB

(base) anniinasainio@Anniinas-MacBook-Air ~ % docker ps -a
CONTAINER ID   IMAGE                                      COMMAND                  CREATED          STATUS                           PORTS     NAMES
d285ece45a40   devopsdockeruh/simple-web-service:alpine   "/usr/src/app/server"    20 seconds ago   Up 19 seconds                              compassionate_benz
(base) anniinasainio@Anniinas-MacBook-Air ~ % docker exec -it compassionate_benz sh
/usr/src/app # tail -f ./text.log
2022-02-05 17:50:19 +0000 UTC
2022-02-05 17:50:21 +0000 UTC
2022-02-05 17:50:23 +0000 UTC
2022-02-05 17:50:25 +0000 UTC
2022-02-05 17:50:27 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
2022-02-05 17:50:29 +0000 UTC
2022-02-05 17:50:31 +0000 UTC
2022-02-05 17:50:33 +0000 UTC
2022-02-05 17:50:35 +0000 UTC
2022-02-05 17:50:37 +0000 UTC
```
## 1.6
```
(base) anniinasainio@Anniinas-MacBook-Air ~ % docker run -it devopsdockeruh/pull_exercise 
Unable to find image 'devopsdockeruh/pull_exercise:latest' locally
latest: Pulling from devopsdockeruh/pull_exercise
8e402f1a9c57: Pull complete 
5e2195587d10: Pull complete 
6f595b2fc66d: Pull complete 
165f32bf4e94: Pull complete 
67c4f504c224: Pull complete 
Digest: sha256:7c0635934049afb9ca0481fb6a58b16100f990a0d62c8665b9cfb5c9ada8a99f
Status: Downloaded newer image for devopsdockeruh/pull_exercise:latest
WARNING: The requested image's platform (linux/amd64) does not match the detected host platform (linux/arm64/v8) and no specific platform was requested
Give me the password: basics
You found the correct password. Secret message is:
"This is the secret message"
```
## 1.7 

```
Dockerfile:

FROM devopsdockeruh/simple-web-service:alpine
CMD server


(base) anniinasainio@Anniinas-MacBook-Air ~ % docker build . -t web-server
[+] Building 2.9s (6/6) FINISHED                                                                                                                                                                                                              
 => [internal] load build definition from Dockerfile                                                                                                                                                                                     0.1s
 => => transferring dockerfile: 165B                                                                                                                                                                                                     0.1s
 => [internal] load .dockerignore                                                                                                                                                                                                        0.1s
 => => transferring context: 2B                                                                                                                                                                                                          0.0s
 => [internal] load metadata for docker.io/devopsdockeruh/simple-web-service:alpine                                                                                                                                                      2.6s
 => [auth] devopsdockeruh/simple-web-service:pull token for registry-1.docker.io                                                                                                                                                         0.0s
 => [1/1] FROM docker.io/devopsdockeruh/simple-web-service:alpine@sha256:dd4d367476f86b7d7579d3379fe446ae5dfce25480903fb0966fc2e5257e0543                                                                                                0.0s
 => => resolve docker.io/devopsdockeruh/simple-web-service:alpine@sha256:dd4d367476f86b7d7579d3379fe446ae5dfce25480903fb0966fc2e5257e0543                                                                                                0.0s
 => exporting to image                                                                                                                                                                                                                   0.0s
 => => exporting layers                                                                                                                                                                                                                  0.0s
 => => writing image sha256:978fbf315695ef5a3ec2e77ee411c4dcd9aa9b867fbc7ea3d26962545fda0585                                                                                                                                             0.0s
 => => naming to docker.io/library/web-server                                                                                                                                                                                            0.0s

Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them
(base) anniinasainio@Anniinas-MacBook-Air ~ % docker run web-server
WARNING: The requested image's platform (linux/amd64) does not match the detected host platform (linux/arm64/v8) and no specific platform was requested
[GIN-debug] [WARNING] Creating an Engine instance with the Logger and Recovery middleware already attached.

[GIN-debug] [WARNING] Running in "debug" mode. Switch to "release" mode in production.
 - using env:	export GIN_MODE=release
 - using code:	gin.SetMode(gin.ReleaseMode)

[GIN-debug] GET    /*path                    --> server.Start.func1 (3 handlers)
[GIN-debug] Listening and serving HTTP on :8080

```

## 1.8 

```
Dockerfile

FROM  ubuntu:20.04
RUN apt-get update; apt-get install -y curl;
CMD echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;


docker build . -t curler
docker run -it curler
    
```
