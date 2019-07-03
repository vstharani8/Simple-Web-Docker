# Simple Web App Deployment

## Install guide


## 1. Deploy the registry with AWS S3 as container and Defie the Config file for AWS S3

```bash
$ cd registry
$ docker-compose up -d
```

## 2. Pull the simple-web app image from docker hub and push it to own registry

```bash
$ docker pull yeasy/simple-web
$ docker tag simple-web localhost:5000/simple-web
$ docker push localhost:5000/simple-web
```

## 3. Pull the nginx image from docker hub and push it to own registry

```bash
$ docker pull nginx
$ docker tag simple-web localhost:5000/nginx
$ docker push localhost:5000/nginx
```

## 4. Setup load balancer and Reverse Proxy. Deploy the Simple Web infront of the proxy.

```bash
$ cd web-proxy-loadbalancer-app
$ docker-compose up -d
```

## So it will deploy the nginx and 2 Web container. 


## 5. Test the Web App

```bash
$ curl localhost:8080
```
## When browse the page, it will forward the request to proxy and then it will go to conainer based on load balancer. 