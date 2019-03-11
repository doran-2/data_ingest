[training@localhost ~]$ sqoop import \
> --connect jdbc:mysql://localhost/loudacre \
> --username training --password training \
> --table accounts \
> --target-dir /loudacre/accounts/CA \
> --where " state='CA'" \
> --compress
19/03/10 22:51:55 INFO sqoop.Sqoop: Running Sqoop version: 1.4.6-cdh5.7.0
19/03/10 22:51:55 WARN tool.BaseSqoopTool: Setting your password on the command-line is insecure. Consider using -P instead.
19/03/10 22:51:55 INFO manager.MySQLManager: Preparing to use a MySQL streaming resultset.
19/03/10 22:51:55 INFO tool.CodeGenTool: Beginning code generation
19/03/10 22:51:56 INFO manager.SqlManager: Executing SQL statement: SELECT t.* FROM `accounts` AS t LIMIT 1
19/03/10 22:51:56 INFO manager.SqlManager: Executing SQL statement: SELECT t.* FROM `accounts` AS t LIMIT 1
19/03/10 22:51:56 INFO orm.CompilationManager: HADOOP_MAPRED_HOME is /usr/lib/hadoop-mapreduce
Note: /tmp/sqoop-training/compile/987cb54e3d3e3fe6ff761c088eb2da1b/accounts.java uses or overrides a deprecated API.
Note: Recompile with -Xlint:deprecation for details.
19/03/10 22:51:59 INFO orm.CompilationManager: Writing jar file: /tmp/sqoop-training/compile/987cb54e3d3e3fe6ff761c088eb2da1b/accounts.jar
19/03/10 22:51:59 WARN manager.MySQLManager: It looks like you are importing from mysql.
19/03/10 22:51:59 WARN manager.MySQLManager: This transfer can be faster! Use the --direct
19/03/10 22:51:59 WARN manager.MySQLManager: option to exercise a MySQL-specific fast path.
19/03/10 22:51:59 INFO manager.MySQLManager: Setting zero DATETIME behavior to convertToNull (mysql)
19/03/10 22:51:59 INFO mapreduce.ImportJobBase: Beginning import of accounts
19/03/10 22:51:59 INFO Configuration.deprecation: mapred.job.tracker is deprecated. Instead, use mapreduce.jobtracker.address
19/03/10 22:51:59 INFO Configuration.deprecation: mapred.jar is deprecated. Instead, use mapreduce.job.jar
19/03/10 22:52:00 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
19/03/10 22:52:00 INFO client.RMProxy: Connecting to ResourceManager at /0.0.0.0:8032
19/03/10 22:52:03 INFO db.DBInputFormat: Using read commited transaction isolation
19/03/10 22:52:03 INFO db.DataDrivenDBInputFormat: BoundingValsQuery: SELECT MIN(`acct_num`), MAX(`acct_num`) FROM `accounts` WHERE (  state='CA' )
19/03/10 22:52:03 INFO db.IntegerSplitter: Split size: 32439; Num splits: 4 from: 1 to: 129760
19/03/10 22:52:03 INFO mapreduce.JobSubmitter: number of splits:4
19/03/10 22:52:03 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1552275592774_0007
19/03/10 22:52:04 INFO impl.YarnClientImpl: Submitted application application_1552275592774_0007
19/03/10 22:52:04 INFO mapreduce.Job: The url to track the job: http://localhost:8088/proxy/application_1552275592774_0007/
19/03/10 22:52:04 INFO mapreduce.Job: Running job: job_1552275592774_0007
19/03/10 22:52:13 INFO mapreduce.Job: Job job_1552275592774_0007 running in uber mode : false
19/03/10 22:52:13 INFO mapreduce.Job:  map 0% reduce 0%
19/03/10 22:52:21 INFO mapreduce.Job:  map 25% reduce 0%
19/03/10 22:52:28 INFO mapreduce.Job:  map 50% reduce 0%
19/03/10 22:52:34 INFO mapreduce.Job:  map 75% reduce 0%
19/03/10 22:52:41 INFO mapreduce.Job:  map 100% reduce 0%
19/03/10 22:52:41 INFO mapreduce.Job: Job job_1552275592774_0007 completed successfully
19/03/10 22:52:42 INFO mapreduce.Job: Counters: 30
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=561308
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=470
		HDFS: Number of bytes written=3771063
		HDFS: Number of read operations=16
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters 
		Launched map tasks=4
		Other local map tasks=4
		Total time spent by all maps in occupied slots (ms)=0
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=20699
		Total vcore-seconds taken by all map tasks=20699
		Total megabyte-seconds taken by all map tasks=5298944
	Map-Reduce Framework
		Map input records=92416
		Map output records=92416
		Input split bytes=470
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=284
		CPU time spent (ms)=6980
		Physical memory (bytes) snapshot=550457344
		Virtual memory (bytes) snapshot=8271118336
		Total committed heap usage (bytes)=251920384
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=3771063
19/03/10 22:52:42 INFO mapreduce.ImportJobBase: Transferred 3.5964 MB in 41.4154 seconds (88.9206 KB/sec)
19/03/10 22:52:42 INFO mapreduce.ImportJobBase: Retrieved 92416 records.
[training@localhost ~]$ 
