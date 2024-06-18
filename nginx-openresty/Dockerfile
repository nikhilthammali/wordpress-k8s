# Dockerfile for Nginx with OpenResty
FROM openresty/openresty:alpine

RUN apk update && apk add build-base \
    && ./config --prefix=/opt/openresty \
                   --with-pcre-jit \
                   --with-ipv6 \
                   --without-http_redis2_module \
                   --with-http_iconv_module \
                   --with-http_postgres_module \
                   -j8 \
    && make && make install

COPY nginx.conf /usr/local/openresty/nginx/conf/nginx.conf
