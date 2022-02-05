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
```
