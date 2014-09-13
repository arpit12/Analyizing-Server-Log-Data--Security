
######################## How to Run #############################

Summary
It describes how to refine raw server log data using the Hortonworks Data Platform, and how to analyze and visualize this refined log data. 

hadoop fs -mkdir /flume 
hadoop fs -put  eventlog-demo.log /flume

To start the JDBC server, run the following in the Spark
directory:

./sbin/start-thriftserver.sh	
	
The default port the server listens on is 10000. Now you can
use beeline to test the Thrift JDBC server:
./bin/beeline	
  

Connect to the JDBC server in beeline with:
beeline>	

!connect jdbc:hive2://localhost:10000/default

Spark-sql Create Table :  


CREATE TABLE LOGS(time STRING, ip STRING, country STRING, status STRING) ROW FORMAT DELIMITED FIELDS TERMINATED BY '|' LOCATION 'hdfs://localhost:54310/flume';


Now can connect it to Tableau/Power-excel/D3 ..
