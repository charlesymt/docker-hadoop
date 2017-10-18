FROM centos:6
MAINTAINER Charles Yu

RUN cat /usr/share/zoneinfo/Asia/Shanghai > /etc/localtime 

RUN yum install -y openssh-server
RUN yum install -y openssh-clients
RUN yum clean all

RUN sed -i 's/UsePAM yes/UsePAM no/g' /etc/ssh/sshd_config
RUN ssh-keygen -t dsa -N "" -f /etc/ssh/ssh_host_dsa_key
RUN ssh-keygen -t rsa -N "" -f /etc/ssh/ssh_host_rsa_key
RUN echo "root:root"|chpasswd
COPY ssh_config /root/.ssh/config
COPY id_rsa /root/.ssh/id_rsa
COPY id_rsa.pub /root/.ssh/authorized_keys
RUN chmod 600 /root/.ssh/*
RUN chown root:root /root/.ssh/config

RUN mkdir /var/run/sshd
EXPOSE 22
CMD ["/usr/sbin/sshd","-D"]
