# hbase standalone conf file
hbase 2.3.6 (2021.08. stable release)
https://www.apache.org/dyn/closer.lua/hbase/2.3.6/hbase-2.3.6-bin.tar.gz

## hbase-env.sh
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64

## hbase-site.xml
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

## openJDK8
**You need to install openJDK8.**

## Reference
https://sig03.medium.com/hbase-standalone-설치-후-데몬이-죽는-문제-해결-5007c49159fc
