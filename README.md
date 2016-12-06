# How to build OCDP client images

Dockerfiles for build OCDP client images, only support mapreduce and spark for now:

## Build MapReduce client docker image

- Clone code from github
  ```
  git clone https://github.com/asiainfoLDP/datafoundry_ocdp_client_images.git
  ```
- Copy OCDP yum repo files
  ```
  cp /etc/yum.repos.d/HDP*.repo datafoundry_ocdp_client_images/mapreduce/etc/yum.repos.d/
  ```
- Copy kerberos config file
  ```
  cp /etc/krb5.conf datafoundry_ocdp_client_images/mapreduce/etc/krb5.conf
  ```
- Copy hadoop configuration files
  ```
  cp /etc/hadoop/conf/core-site.xml datafoundry_ocdp_client_images/mapreduce/etc/hadoop/
  cp /etc/hadoop/conf/hdfs-site.xml datafoundry_ocdp_client_images/mapreduce/etc/hadoop/
  cp /etc/hadoop/conf/yarn-site.xml datafoundry_ocdp_client_images/mapreduce/etc/hadoop/
  cp /etc/hadoop/conf/mapred-site.xml datafoundry_ocdp_client_images/mapreduce/etc/hadoop/
  ```
- Build mapreduce client docker image
  ```
  cd datafoundry_ocdp_client_images/mapreduce/
  docker build -t ocdpbroker/yarn-client .
  ```

## Build Spark client docker image

- Clone code from github
  ```
  git clone https://github.com/asiainfoLDP/datafoundry_ocdp_client_images.git
  ```
- Copy OCDP yum repo files
  ```
  cp /etc/yum.repos.d/HDP*.repo datafoundry_ocdp_client_images/spark/etc/yum.repos.d/
  ```
- Copy kerberos config file
  ```
  cp /etc/krb5.conf datafoundry_ocdp_client_images/spark/etc/krb5.conf
  ```
- Copy hadoop configuration files
  ```
  cp /etc/hadoop/conf/core-site.xml datafoundry_ocdp_client_images/spark/etc/hadoop/
  cp /etc/hadoop/conf/hdfs-site.xml datafoundry_ocdp_client_images/spark/etc/hadoop/
  cp /etc/hadoop/conf/yarn-site.xml datafoundry_ocdp_client_images/spark/etc/hadoop/
  cp /etc/hadoop/conf/mapred-site.xml datafoundry_ocdp_client_images/spark/etc/hadoop/
  ```
- Copy spark configuration files
  ```
  cp /etc/spark/conf/spark-defaults.conf datafoundry_ocdp_client_images/spark/etc/spark/
  cp /etc/spark/conf/hive-site.xml datafoundry_ocdp_client_images/spark/etc/spark/
  ```
- Build spark client docker image
  ```
  cd datafoundry_ocdp_client_images/spark/
  docker build -t ocdpbroker/spark-client .
  ```