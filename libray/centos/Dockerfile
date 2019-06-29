# Copyright (C) 2001-2018
# 
# INFO:
# Touch: It is by Kevin li
# Date:  2018-08-17
# QQ:    2658757934
# blog:  https://blog.51cto.com/blief

# Set the base image source.
FROM centos:latest

# Add basic command for system
copy basic-cmd/* /usr/sbin/

# Change mirrors to aliyun mirror and set time zone to shangahi zone  for system.
RUN mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.bak \
  && wget http://mirrors.aliyun.com/repo/Centos-7.repo -P /etc/yum.repos.d/ >/dev/null 2>&1 \
  && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
  && echo "Asia/Shanghai" > /etc/timezone
