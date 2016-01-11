# Nginx v1.8.0
# docker run --rm -p 80:80 -v $(pwd)/html:/usr/share/nginx/html pottava/nginx:1.8

FROM alpine:3.3

RUN apk --no-cache add nginx \
      && ln -sf /dev/stdout /var/log/nginx/access.log \
      && ln -sf /dev/stderr /var/log/nginx/error.log

CMD ["nginx", "-g", "daemon off;"]
