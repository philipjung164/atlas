Remote Debug using Intellij

[ec2-user@ip-10-21-1-21 bin]$ ps -ef |grep java
ec2-user  3716  3702  0 Jun01 ?        01:26:39 /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.252.b09-2.amzn2.0.1.x86_64/jre/bin/java -Dproc_master -XX:OnOutOfMemoryError=kill -9 %p -XX:+UseConcMarkSweepGC -Dhbase.log.dir=/home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/hbase/bin/../logs -Dhbase.log.file=hbase-ec2-user-master-ip-10-21-1-21.ap-northeast-2.compute.internal.log -Dhbase.home.dir=/home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/hbase/bin/.. -Dhbase.id.str=ec2-user -Dhbase.root.logger=INFO,RFA -Dhbase.security.logger=INFO,RFAS org.apache.hadoop.hbase.master.HMaster start
ec2-user 15319     1  8 03:59 pts/1    00:00:16 /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.252.b09-2.amzn2.0.1.x86_64/bin/java -server -Xms512m -Xmx512m -XX:NewRatio=3 -XX:SurvivorRatio=4 -XX:TargetSurvivorRatio=90 -XX:MaxTenuringThreshold=8 -XX:+UseConcMarkSweepGC -XX:ConcGCThreads=4 -XX:ParallelGCThreads=4 -XX:+CMSScavengeBeforeRemark -XX:PretenureSizeThreshold=64m -XX:+UseCMSInitiatingOccupancyOnly -XX:CMSInitiatingOccupancyFraction=50 -XX:CMSMaxAbortablePrecleanTime=6000 -XX:+CMSParallelRemarkEnabled -XX:+ParallelRefProcEnabled -XX:-OmitStackTraceInFastThrow -verbose:gc -XX:+PrintHeapAtGC -XX:+PrintGCDetails -XX:+PrintGCDateStamps -XX:+PrintGCTimeStamps -XX:+PrintTenuringDistribution -XX:+PrintGCApplicationStoppedTime -Xloggc:/home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/solr/server/logs/solr_gc.log -XX:+UseGCLogFileRotation -XX:NumberOfGCLogFiles=9 -XX:GCLogFileSize=20M -DzkClientTimeout=15000 -DzkHost=localhost:2181 -Dsolr.log.dir=/home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/solr/server/logs -Djetty.port=9838 -DSTOP.PORT=8838 -DSTOP.KEY=solrrocks -Duser.timezone=UTC -Djetty.home=/home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/solr/server -Dsolr.solr.home=/home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/solr/server/solr -Dsolr.data.home= -Dsolr.install.dir=/home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/solr -Dsolr.default.confdir=/home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/solr/server/solr/configsets/_default/conf -Xss256k -Dsolr.jetty.https.port=9838 -Dsolr.log.muteconsole -XX:OnOutOfMemoryError=/home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/solr/bin/oom_solr.sh 9838 /home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/solr/server/logs -jar start.jar --module=http
ec2-user 15652     1 20 03:59 pts/1    00:00:37 /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.252.b09-2.amzn2.0.1.x86_64/bin/java -Datlas.log.dir=/home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/logs -Datlas.log.file=application.log -Datlas.home=/home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0 -Datlas.conf=/home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/conf -Xmx1024m -Xdebug -agentlib:jdwp=transport=dt_socket,address=9999,server=y,suspend=n -Dlog4j.configuration=atlas-log4j.xml -Djava.net.preferIPv4Stack=true -server -classpath /home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/conf:/home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/server/webapp/atlas/WEB-INF/classes:/home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/server/webapp/atlas/WEB-INF/lib/*:/home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/libext/*:/home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/hbase/conf org.apache.atlas.Atlas -app /home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/server/webapp/atlas

15319 가 Jetty 프로세스임

[ec2-user@ip-10-21-1-21 bin]$ python atlas_stop.py
stopping atlas....
Apache Atlas Server stopped!!!

Sending stop command to Solr running on port 9838 ... waiting up to 180 seconds to allow Jetty process 15319 to stop gracefully.
running master, logging to /home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/hbase/bin/../logs/hbase-ec2-user-master-ip-10-21-1-21.ap-northeast-2.compute.internal.out
no master to stop because no pid file /tmp/hbase-ec2-user-master.pid

 /home/ec2-user/apache-atlas-sources-2.0.0/distro/target/apache-atlas-2.0.0-server/apache-atlas-2.0.0/bin/

추가해 준 옵션
DEFAULT_JVM_OPTS="-Xdebug -agentlib:jdwp=transport=dt_socket,address=9999,server=y,suspend=n -Dlog4j.configuration=atlas-log4j.xml -Djava.net.preferIPv4Stack=true -server"

-agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=9999

# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements.  See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership.  The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License.  You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

Apache Atlas Overview
=====================

Apache Atlas framework is an extensible set of core
foundational governance services – enabling enterprises to effectively and
efficiently meet their compliance requirements within Hadoop and allows
integration with the whole enterprise data ecosystem.

This will provide true visibility in Hadoop by using both a prescriptive
and forensic model, along with technical and operational audit as well as
lineage enriched by business taxonomical metadata.  It also enables any
metadata consumer to work inter-operably without discrete interfaces to
each other -- the metadata store is common.

The metadata veracity is maintained by leveraging Apache Ranger to prevent
non-authorized access paths to data at runtime.
Security is both role based (RBAC) and attribute based (ABAC).


Build Process
=============

1. Get Atlas sources to your local directory, for example with following commands
   $ cd <your-local-directory>
   $ git clone https://github.com/apache/atlas.git
   $ cd atlas

   # Checkout the branch or tag you would like to build
   #
   # to checkout a branch
     $ git checkout <branch>

   # to checkout a tag
     $ git checkout tags/<tag>

2. Execute the following commands to build Apache Atlas

   $ export MAVEN_OPTS="-Xms2g -Xmx2g"
   $ mvn clean install
   $ mvn clean package -Pdist

3. After above build commands successfully complete, you should see the following files

   distro/target/apache-atlas-<version>-bin.tar.gz
   distro/target/apache-atlas-<version>-hbase-hook.tar.gz
   distro/target/apache-atlas-<version>-hive-hook.tar.gz
   distro/target/apache-atlas-<version>-impala-hook.tar.gz
   distro/target/apache-atlas-<version>-kafka-hook.tar.gz
   distro/target/apache-atlas-<version>-server.tar.gz
   distro/target/apache-atlas-<version>-sources.tar.gz
   distro/target/apache-atlas-<version>-sqoop-hook.tar.gz
   distro/target/apache-atlas-<version>-storm-hook.tar.gz
   distro/target/apache-atlas-<version>-falcon-hook.tar.gz

4. For more details on installing and running Apache Atlas, please refer to https://atlas.apache.org/#/Installation
