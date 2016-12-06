FROM centos

RUN yum update -y && \
    yum install -y wget java-1.8.0-openjdk-devel krb5-workstation krb5-libs

ENV JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk/

COPY etc/yum.repos.d/*.repo /etc/yum.repos.d/

RUN yum update -y && \
    yum install -y spark_2_4_0_0_169-1.6.0.2.4.0.0-169.el6.noarch

COPY etc/hadoop/*.xml /etc/hadoop/conf/

COPY etc/spark/* /etc/spark/conf/

COPY etc/krb5.conf /etc/krb5.conf

WORKDIR /root
