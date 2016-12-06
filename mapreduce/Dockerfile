FROM centos

RUN yum update -y && \
    yum install -y wget java-1.8.0-openjdk-devel krb5-workstation krb5-libs

ENV JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk/

COPY etc/yum.repos.d/*.repo /etc/yum.repos.d/

RUN yum update -y && \
    yum install -y hadoop_2_4_0_0_169-yarn-2.7.1.2.4.0.0-169.el6.x86_64 \
    yum install -y hadoop_2_4_0_0_169-mapreduce-2.7.1.2.4.0.0-169.el6.x86_64 \
    yum install -y hadoop_2_4_0_0_169-client-2.7.1.2.4.0.0-169.el6.x86_64

COPY etc/krb5.conf /etc/krb5.conf

COPY etc/hadoop/*.xml /etc/hadoop/conf/

WORKDIR /root
