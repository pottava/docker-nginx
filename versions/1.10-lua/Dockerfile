# Nginx v1.10.1
# docker run --rm -p 80:80 -v $(pwd)/html:/var/lib/nginx/html pottava/nginx:1.10-lua
# docker run --rm -p 80:80 -v $(pwd)/conf:/etc/nginx/conf.d pottava/nginx:1.10-lua

FROM alpine:3.4

RUN apk --no-cache add nginx-lua \
      && mkdir -p /run/nginx \
      && ln -sf /dev/stdout /var/log/nginx/access.log \
      && ln -sf /dev/stderr /var/log/nginx/error.log

CMD ["nginx", "-g", "daemon off;"]
