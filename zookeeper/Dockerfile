FROM openjdk:19-jdk-slim
WORKDIR /app
# RUN echo "#阿里云\ndeb http://mirrors.aliyun.com/kali kali-rolling main non-free contrib\n deb-src http://mirrors.aliyun.com/kali kali-rolling main non-free contrib\n #清华大学\n deb http://mirrors.tuna.tsinghua.edu.cn/kali kali-rolling main contrib non-free\ndeb-src https://mirrors.tuna.tsinghua.edu.cn/kali kali-rolling main contrib non-free\n #浙江大学\n deb http://mirrors.zju.edu.cn/kali kali-rolling main contrib non-free\n deb-src http://mirrors.zju.edu.cn/kali kali-rolling main contrib non-free " > /etc/apt/sources.list \
RUN apt-get update && apt-get install -y wget \
&& wget http://archive.apache.org/dist/zookeeper/zookeeper-3.4.14/zookeeper-3.4.14.tar.gz \
&& tar -xvf zookeeper-3.4.14.tar.gz 
RUN cd zookeeper-3.4.14/conf && mv zoo_sample.cfg zoo.cfg 
ENTRYPOINT [ "/app/zookeeper-3.4.14/bin/zkServer.sh","start-foreground" ]
