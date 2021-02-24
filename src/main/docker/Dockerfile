#基础镜像
FROM adoptopenjdk/openjdk8:centos
#作者
LABEL maintainer="14268414+Thousandcherry@users.noreply.github.com"
#创建目录
RUN mkdir /opt/app
#编译镜像时复制maven package打包生成的jar到镜像对应的目录下
COPY config-server-0.0.1-SNAPSHOT.jar /opt/app
#创建容器的匿名卷
#如果运行一个容器但是不绑定目录到容器的匿名卷
#这时候再/var/lib/docker/volumes（不同版本目录不一样）中就会创建一个目录绑定匿名卷
VOLUME ["/opt/docker/conf"]
#开放端口
EXPOSE 3020
#启动时执行的命令，这里还可以添加jar启动环境变量参数
ENTRYPOINT ["java","-jar","/opt/app/config-server-0.0.1-SNAPSHOT.jar"]