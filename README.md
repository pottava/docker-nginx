Nginx Dockerfiles based on Alpine Linux 3.3.
---

## Images

https://hub.docker.com/r/pottava/nginx/

## Available Tags

https://hub.docker.com/r/pottava/nginx/tags/

### Supported tags and respective `Dockerfile` links

・latest ([versions/1.9/Dockerfile](https://github.com/pottava/docker-nginx/blob/master/versions/1.9/Dockerfile))
・1.9 ([versions/1.9/Dockerfile](https://github.com/pottava/docker-nginx/blob/master/versions/1.9/Dockerfile))
・1.8 ([versions/1.8/Dockerfile](https://github.com/pottava/docker-nginx/blob/master/versions/1.8/Dockerfile))
・1.8-lua ([versions/1.8-lua/Dockerfile](https://github.com/pottava/docker-nginx/blob/master/versions/1.8-lua/Dockerfile))

## Usage

If you have html contents, run with following commands  
`docker run --rm -p 80:80 -v $(pwd)/html:/etc/nginx/html pottava/nginx:`

If you want to change configurations (e.g. reverse-proxy mode), run with following commands  
`docker run --rm -p 80:80 -v $(pwd)/conf/nginx.conf:/etc/nginx/conf/nginx.conf pottava/nginx`
