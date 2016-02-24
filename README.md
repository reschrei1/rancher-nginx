# Rancher Nginx Proxy

Template for custom SSL termination in front of Rancher Server

## Build

```
docker build -t marcqualie/rancher-nginx .
```

## Run

```
docker run -d --restart=always -p 8080:8080 --name rancher-server rancher/server:v0.59.1
docker run -d --restart=alwats -p 80:80 -p 443:443 --link rancher-server --name rancher-nginx marcqualie/rancher-nginx
```

## Debug

```
docker run -ti -a STDIN -a STDOUT -a STDERR -p 8080:80 marcqualie/rancher-nginx bash
```
