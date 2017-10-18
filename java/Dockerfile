FROM ymt/base
ADD jdk-7u80-linux-x64.tar.gz /usr/local
RUN ln -s /usr/local/jdk1.7.0_80 /usr/local/jdk;
ENV JAVA_HOME /usr/local/jdk
ENV CLASSPATH .:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV PATH $JAVA_HOME/bin:$PATH
RUN echo "export JAVA_HOM=$JAVA_HOME" >> /etc/profile
RUN echo "export CLASSPATH=$CLASSPATH" >> /etc/profile
RUN echo "export PATH=$PATH" >> /etc/profile
