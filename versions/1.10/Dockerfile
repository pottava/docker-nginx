# Nginx v1.10.1
# docker run --rm -p 80:80 -v $(pwd)/html:/var/lib/nginx/html pottava/nginx:1.10
# docker run --rm -p 80:80 -v $(pwd)/conf:/etc/nginx/conf.d pottava/nginx:1.10

FROM alpine:3.4

RUN apk --no-cache add nginx \
      && mkdir -p /run/nginx \
      && ln -sf /dev/stdout /var/log/nginx/access.log \
      && ln -sf /dev/stderr /var/log/nginx/error.log

CMD ["nginx", "-g", "daemon off;"]
