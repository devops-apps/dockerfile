# Copyright (C) 2001-2018
# 
# INFO:
# Touch: It is by Kevin li
# Date:  2018-08-17
# QQ:    2658757934
# blog:  http://home.51cto.com/space?uid=6170059

# Set the base image source.
FROM registry.cn-hangzhou.aliyuncs.com/oslibrary/java-centos:1.8

# Set maintainer information for the images
LABEL maintainer kevin li 2658757934Qqq.com

# EXPOST service port for application
EXPOSE 8080 8090

# Add java packages of application . 
COPY baton-1.0.0-SNAPSHOT.jar /opt/app.jar
COPY config/ /opt/config

# Set the application startup command
ENTRYPOINT ["sh","-c","java -Djava.security.egd=file:/dev/./urandom -Duser.timezone=GMT+8 -Dfile.encoding=UTF-8 -Dspring.config.location=/opt/config/ -jar /opt/app.jar" ]
