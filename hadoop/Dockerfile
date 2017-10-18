FROM ymt/zoo
ADD  hadoop-2.6.0.tar.gz /usr/local/
RUN ln -s /usr/local/hadoop-2.6.0 /usr/local/hadoop
ENV HADOOP_HOME /usr/local/hadoop
COPY core-site.xml $HADOOP_HOME/etc/hadoop/
COPY hdfs-site.xml $HADOOP_HOME/etc/hadoop/
COPY hadoop-env.sh $HADOOP_HOME/etc/hadoop/
COPY slaves $HADOOP_HOME/etc/hadoop/
COPY mapred-site.xml $HADOOP_HOME/etc/hadoop/
COPY yarn-site.xml $HADOOP_HOME/etc/hadoop/
RUN mkdir /root/data/journaldata

ENV PATH $HADOOP_HOME/bin:$PATH
RUN echo "export HADOOP_HOME=$HADOOP_HOME" >> /etc/profile
RUN echo "PATH=$PATH" >> /etc/profile

EXPOSE 9000 50070 50020
EXPOSE 8485 2181 8032 8034 8088
