# Hive

Apache Hive is an open-source data warehouse infrastructure built on top of Apache Hadoop. It provides a query language called HiveQL, which is similar to SQL (Structured Query Language), and allows users to perform ad-hoc queries and analysis on large datasets stored in distributed file systems, such as Hadoop Distributed File System (HDFS).

Hive was developed to provide a high-level abstraction layer for querying and analyzing structured and semi-structured data stored in Hadoop. It allows users to write SQL-like queries, known as HiveQL, which are then converted into MapReduce, Tez, or Spark jobs, depending on the configuration, and executed on the underlying Hadoop infrastructure.

One of the key features of Hive is its ability to handle large-scale datasets efficiently by parallelizing the data processing across multiple nodes in a Hadoop cluster. It also supports schema evolution, allowing users to add, modify, or delete columns from existing tables without the need for extensive data movement.


![image](https://github.com/Anshumaan031/Hive_Data_Eng/assets/67821036/34e32500-b696-43ea-8538-79d235c884db)

Download Hive from here: https://downloads.apache.org/hive/hive-3.1.2/

Download mysql jar connector maven: https://mvnrepository.com/artifact/mysql/mysql-connector-java

and copy the file to apache_hive/lib/

extract and install
```bash
sudo apt-get install mysql-server
sudo mysql

ALTER USER 9root@localhost' IDENTIFIED WITH mysql_native_password BY 'root';

mysql -u root -p
```
This command changes the password for the user root and sets the authentication method to 'root'.

 open bachrc file to source the hive files 
```bash
vi .bashrc (Set the java Path in your Home Path)

export HIVE_HOME=/home/username/hive
export PATH=HOME/bin:HIVE_HOME/bin:PATH

 source .bashrc 
 echo HIVE_HOME 
```

2. changes to make in hive/conf/hive-site.mxl
```bash
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<?xml-stylesheet type="text/xsl" href="configuration.xsl"?>
<configuration>

<property>
  <name>javax.jdo.option.ConnectionURL</name>
  <value>jdbc:mysql://localhost/metastore?createDatabaseIfNotExist=true</value>
</property>


<property>
  <name>javax.jdo.option.ConnectionDriverName</name>
  <value>com.mysql.jdbc.Driver</value>
</property>

<property>
  <name>javax.jdo.option.ConnectionUserName</name>
  <value>root</value>
</property>

<property>
  <name>javax.jdo.option.ConnectionPassword</name>
  <value>root</value>
</property>
<property>
<name>hive.metastore.schema.verification</name>
<value>false</value>
</property>
</configuration>
```



To start hive

```bash
bin/hive

```

## Documentations

[hive](https://cwiki.apache.org/confluence/display/Hive/) 

[Mysql](https://dev.mysql.com/doc/)

[hadoop](https://hadoop.apache.org/docs/stable/)

## Authors

- [@Anshumaan - <anshumaan.phukan@uavtech.ai>](https://github.com/Anshumaan031)
