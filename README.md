# hbase standalone conf file
hbase 2.3.6 (2021.08. stable release)
https://www.apache.org/dyn/closer.lua/hbase/2.3.6/hbase-2.3.6-bin.tar.gz

## 1. hbase-env.sh
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64

## 2. hbase-site.xml
<configuration>
  <property>
    <name>hbase.cluster.distributed</name>
    <value>false</value>
  </property>
  <property>
    <name>hbase.tmp.dir</name>
    <value>./tmp</value>
  </property>
  <property>
    <name>hbase.unsafe.stream.capability.enforce</name>
    <value>false</value>
  </property>
  <property>
    <name>hbase.rootdir</name>
    <value>file:///app/hbase-2.3.6/HBASE/hbase</value>
  </property>
  <property>
    <name>hbase.zookeeper.property.dataDir</name>
    <value>/app/hbase-2.3.6/HBASE/zookeeper</value>
  </property>
</configuration>

## 3. openJDK8
**You need to install openJDK8.**

## 4. hbase standalone installation
```
//1. install openjdk
$ apt install openjdk-8*

//2. file download
$ wget https://downloads.apache.org/hbase/2.3.6/hbase-2.3.6-bin.tar.gz

//3. extraction
$ tar xvzf hbase-2.3.6-bin.tar.gz
$ mv hbase-2.3.6 hbase

//4. setting java path
$ vi hbase/conf/hbase-env.sh
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64

//5. setting hbase-site.xml
$ vi hbase/conf/hbase-site.xml
<configuration>
  <property>
    <name>hbase.cluster.distributed</name>
    <value>false</value>
  </property>
  <property>
    <name>hbase.tmp.dir</name>
    <value>./tmp</value>
  </property>
  <property>
    <name>hbase.unsafe.stream.capability.enforce</name>
    <value>false</value>
  </property>
  <property>
    <name>hbase.rootdir</name>
    <value>file:///app/hbase-2.3.6/HBASE/hbase</value>
  </property>
  <property>
    <name>hbase.zookeeper.property.dataDir</name>
    <value>/app/hbase-2.3.6/HBASE/zookeeper</value>
  </property>
</configuration>

//6. start a hbase daemon
$ ./hbase/bin/start-hbase.sh

//7. web UI
http://IP::16030

//8. shell
$ ./hbase/bin/hbase shell

```

## 5. Reference
https://sig03.medium.com/hbase-standalone-설치-후-데몬이-죽는-문제-해결-5007c49159fc
https://sig03.medium.com/hbase-도입-검토-e165fd439f5b
