# Nginx v1.8.0
# docker run --rm -p 80:80 -v $(pwd)/html:/usr/share/nginx/html pottava/nginx

FROM alpine:3.3

RUN apk --no-cache add nginx

CMD ["nginx", "-g", "daemon off;"]
