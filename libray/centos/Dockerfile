# Copyright (C) 2001-2018
# 
# INFO:
# Touch: It is by Kevin li
# Date:  2018-08-17
# QQ:    2658757934
# blog:  https://blog.51cto.com/blief

#  && curl http://mirrors.aliyun.com/repo/Centos-7.repo -o /etc/yum.repos.d/CentOS-Base.repo \
# Set the base image source.
FROM centos:latest

# Change mirrors to aliyun mirror and set time zone to shangahi zone  for system.
RUN  cp /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.bak \
  && curl http://mirrors.aliyun.com/repo/Centos-7.repo -o /etc/yum.repos.d/CentOS-Base.repo \
  && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
  && yum -y install net-tools lsof wget \
  && yum clean all \
  && rm -rf /var/cache/yum
