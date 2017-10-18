FROM ymt/java

ADD zookeeper-3.4.6.tar.gz /usr/local
RUN ln -s /usr/local/zookeeper-3.4.6 /usr/local/zookeeper
COPY zoo.cfg /usr/local/zookeeper/conf/
COPY tools/* /usr/local/tools/
RUN chmod a+x /usr/local/tools/*
RUN mkdir -p /root/data/zookeeper/zkdata
RUN mkdir -p /root/data/zookeeper/zkdatalog
ENV ZOOKEEPER_HOME /usr/local/zookeeper
ENV PATH /usr/local/tools:$ZOOKEEPER_HOME/bin:$PATH
RUN echo "export ZOOKEEPER_HOME=$ZOOKEEPER_HOME" >> /etc/profile
RUN echo "export PATH=$PATH" >> /etc/profile
EXPOSE 2181 2888 3888
