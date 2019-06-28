# Copyright (C) 2001-2018
# 
# INFO:
# Touch: It is by Kevin li
# Date:  2018-08-17
# QQ:    2658757934
# blog:  http://home.51cto.com/space?uid=6170059

# Set the base image source.
FROM registry-mirror.mo9.com/java/alpine:jre1.8

# Set maintainer information for the images
LABEL maintainer kevin li 2658757934Qqq.com

# EXPOST service port for application
EXPOSE 8080 8090

# Define configure file path for application
VOLUME /opt/config

# Add java packages of application . 
COPY baton-1.0.0-SNAPSHOT.jar /opt/app.jar

# Set the application startup command
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-Dspring.config.location=/opt/config/","-jar","/opt/app.jar"]
