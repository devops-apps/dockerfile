# Copyright (C) 2001-2018
#
# INFO:
# Touch: It is by Kevin li
# Date:  2018-08-17
# QQ:    2658757934
# blog:  http://blog.51cto.com/space?uid=6170059

# Set base image for java
FROM  registry.cn-hangzhou.aliyuncs.com/oslibrary/centos:latest

# Add jre packages to system. 
ADD jre_1.8.tar.gz /usr/local/jre1.8

# Set enviornment variables of java
ENV JAVA_HOME /usr/local/jre1.8
ENV PATH $PATH:$JAVA_HOME/bin 
