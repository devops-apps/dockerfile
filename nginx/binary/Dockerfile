# Copyright (C) 2001-2018
# 
# INFO:
# Touch: It is by Kevin li
# Date:  2018-08-17
# QQ:    2658757934
# blog:  http://blog.51cto.com/space?uid=6170059

# Set the base image source.
FROM registry.cn-hangzhou.aliyuncs.com/oslibrary/centos:latest

# Expose services port for images
EXPOSE 80 443

# Add install package and configure file for images
COPY nginx_work /data/apps/nginx

# Install the java applications. 
RUN groupadd -r nginx \
  && useradd -r -g nginx -c "Nginx Service" -d /var/lib/nginx -s /sbin/nologin nginx \
  && mv /data/apps/nginx/etc /etc/nginx \
  && ln -sf /data/apps/nginx/sbin/nginx /usr/bin \
  && yum clean all \
  && rm -rf /var/cache/yum \
  && rm -r /usr/share/man 

# Set the application excute  command
CMD ["nginx", "-g", "daemon off;"]
