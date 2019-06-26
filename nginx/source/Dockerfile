# Copyright (C) 2001-2018
# 
# INFO:
# Touch: It is by Kevin li
# Date:  2018-08-17
# QQ:    2658757934
# blog:  http://home.51cto.com/space?uid=6170059

# Set the base image source.
FROM registry.cn-hangzhou.aliyuncs.com/oslibrary/centos:7.6

# Define variables for tengine. 
ENV DOWN_URL="http://tengine.taobao.org/download/tengine-2.1.2.tar.gz" \
ARGS="\
--prefix=/data/apps/nginx \
--sbin-path=/data/apps/nginx/sbin/nginx \
--conf-path=/etc/nginx/nginx.conf  \
--error-log-path=/data/apps/nginx/logs/error.log \
--http-log-path=/data/apps/nginx/logs/access.log  \
--pid-path=/var/run/nginx.pid  \
--lock-path=/var/lock/nginx.lock \
--user=nginx \
--group=nginx \
--with-http_ssl_module \
--with-http_v2_module \
--with-http_stub_status_module \
--with-http_gunzip_module      \
--with-http_gzip_static_module \
--with-http_realip_module \
--http-client-body-temp-path=/data/apps/nginx/temp/client \
--http-proxy-temp-path=/data/apps/nginx/temp/proxy \
--http-fastcgi-temp-path=/data/apps/nginx/temp/fastcgi \
--http-uwsgi-temp-path=/data/apps/nginx/temp/uwsgi \
--http-scgi-temp-path=/data/apps/nginx/temp/scgi \
--with-pcre"

# Expose services port for images
EXPOSE 80 443

# Install the java applications. 
RUN groupadd -r nginx \
  && useradd -r -g nginx -c "Nginx Service" -d /var/lib/nginx -s /sbin/nologin  nginx \
  && yum install gcc make openssl-devel pcre-devel zlib-devel -y \
  && wget $DOWN_URL -P /usr/local/src >>/dev/null 2>&1 \
  && cd /usr/local/src && tar zxf tengine-2.1.2.tar.gz \
  && cd /usr/local/src/tengine-2.1.2 \
  && ./configure $ARGS \
  && make && make install \
  && ln -sf /data/apps/nginx/sbin/nginx /usr/bin \
  && rm -rf /usr/local/src/tengine-2.1.2 \
  && yum clean all \
  && rm -r /usr/share/man \
  && rm -rf /var/cache/yum && rm -r /usr/share/man \
  && mkdir /data/apps/nginx/temp

# Set the application excute  command
CMD ["nginx", "-g", "daemon off;"]
