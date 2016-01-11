# Nginx v1.9.9
# docker run --rm -p 80:80 -v $(pwd)/html:/etc/nginx/html pottava/nginx:1.9

FROM alpine:3.3

ENV NGINX_VERSION=1.9.9 LUA_VERSION=0.9.20 NDK_VERSION=0.2.19

RUN apk --no-cache add --virtual build-dependencies build-base curl \
      && apk --no-cache add luajit-dev pcre-dev openssl-dev libatomic_ops-dev \
      && mkdir -p /tmp/src /var/lib/nginx /var/log/nginx \
      && cd /tmp/src \
      && curl --location --silent https://github.com/simpl/ngx_devel_kit/archive/v${NDK_VERSION}.tar.gz | tar xzf - \
      && curl --location --silent https://github.com/openresty/lua-nginx-module/archive/v${LUA_VERSION}.tar.gz | tar xzf - \
      && curl --location --silent http://nginx.org/download/nginx-${NGINX_VERSION}.tar.gz | tar xzf - \
      && cd /tmp/src/nginx-${NGINX_VERSION} \
      && ./configure \
          --with-cc-opt="-Wno-maybe-uninitialized -Wno-pointer-sign" \
          --prefix=/etc/nginx \
          --sbin-path=/usr/local/sbin/nginx \
          --pid-path=/run/nginx.pid \
          --lock-path=/run/nginx.lock \
          --with-ipv6 \
          --with-libatomic \
          --with-pcre \
          --with-pcre-jit \
          --http-client-body-temp-path=/var/lib/nginx/client_body_temp \
          --http-proxy-temp-path=/var/lib/nginx/proxy_temp \
          --http-fastcgi-temp-path=/var/lib/nginx/fastcgi_temp \
          --http-uwsgi-temp-path=/var/lib/nginx/uwsgi_temp \
          --http-scgi-temp-path=/var/lib/nginx/scgi_temp \
          --http-log-path=/var/log/nginx/access.log \
          --error-log-path=/var/log/nginx/error.log \
          --with-http_v2_module \
          --with-http_ssl_module \
          --with-http_stub_status_module \
          --with-http_gzip_static_module \
          --with-http_realip_module \
          --with-http_sub_module \
          --with-http_secure_link_module \
          --add-module=/tmp/src/ngx_devel_kit-${NDK_VERSION} \
          --add-module=/tmp/src/lua-nginx-module-${LUA_VERSION} \
      && make \
      && make install \
      && cd /root \
      && rm -rf /tmp/src /var/www/html \
      && mv /var/www /etc/nginx/html \
      && ln -sf /dev/stdout /var/log/nginx/access.log \
      && ln -sf /dev/stderr /var/log/nginx/error.log \
      && apk del build-dependencies

CMD ["nginx", "-g", "daemon off;"]
