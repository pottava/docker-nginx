Nginx Dockerfiles based on Alpine Linux 3.3.
---

## Images

https://hub.docker.com/r/pottava/nginx/

## Usage

If you have html contents, run with following commands  
`docker run --rm -p 80:80 -v $(pwd)/html:/etc/nginx/html pottava/nginx`

If you want to change configurations (e.g. reverse-proxy mode), run with following commands  
`docker run --rm -p 80:80 -v $(pwd)/conf/nginx.conf:/etc/nginx/conf/nginx.conf pottava/nginx`

## Available Tags

https://hub.docker.com/r/pottava/nginx/tags/
