# Set the base image source.
FROM  registry.cn-hangzhou.aliyuncs.com/oslibrary/alpine-glibc:1.0

# Add jre packages to system. 
ADD jre1.8.tar.gz /usr/local/jre1.8

# Set enviornment variables of java
ENV JAVA_HOME /usr/local/jre1.8
ENV PATH ${PATH}:${JAVA_HOME}/bin 
