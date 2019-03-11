[training@localhost ~]$ sqoop import \
> --connect jdbc:mysql://localhost/loudacre \
> --username training --password training \
> --table accounts \
> --target-dir /loudacre/accounts/CA \
> --where " state='CA'"
19/03/10 22:30:46 INFO sqoop.Sqoop: Running Sqoop version: 1.4.6-cdh5.7.0
19/03/10 22:30:46 WARN tool.BaseSqoopTool: Setting your password on the command-line is insecure. Consider using -P instead.
19/03/10 22:30:47 INFO manager.MySQLManager: Preparing to use a MySQL streaming resultset.
19/03/10 22:30:47 INFO tool.CodeGenTool: Beginning code generation
19/03/10 22:30:47 INFO manager.SqlManager: Executing SQL statement: SELECT t.* FROM `accounts` AS t LIMIT 1
19/03/10 22:30:47 INFO manager.SqlManager: Executing SQL statement: SELECT t.* FROM `accounts` AS t LIMIT 1
19/03/10 22:30:47 INFO orm.CompilationManager: HADOOP_MAPRED_HOME is /usr/lib/hadoop-mapreduce
Note: /tmp/sqoop-training/compile/78d62f08c0e5f7961adc77575f9aaf5a/accounts.java uses or overrides a deprecated API.
Note: Recompile with -Xlint:deprecation for details.
19/03/10 22:30:50 INFO orm.CompilationManager: Writing jar file: /tmp/sqoop-training/compile/78d62f08c0e5f7961adc77575f9aaf5a/accounts.jar
19/03/10 22:30:50 WARN manager.MySQLManager: It looks like you are importing from mysql.
19/03/10 22:30:50 WARN manager.MySQLManager: This transfer can be faster! Use the --direct
19/03/10 22:30:50 WARN manager.MySQLManager: option to exercise a MySQL-specific fast path.
19/03/10 22:30:50 INFO manager.MySQLManager: Setting zero DATETIME behavior to convertToNull (mysql)
19/03/10 22:30:50 INFO mapreduce.ImportJobBase: Beginning import of accounts
19/03/10 22:30:50 INFO Configuration.deprecation: mapred.job.tracker is deprecated. Instead, use mapreduce.jobtracker.address
19/03/10 22:30:50 INFO Configuration.deprecation: mapred.jar is deprecated. Instead, use mapreduce.job.jar
19/03/10 22:30:51 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
19/03/10 22:30:51 INFO client.RMProxy: Connecting to ResourceManager at /0.0.0.0:8032
19/03/10 22:30:54 INFO db.DBInputFormat: Using read commited transaction isolation
19/03/10 22:30:54 INFO db.DataDrivenDBInputFormat: BoundingValsQuery: SELECT MIN(`acct_num`), MAX(`acct_num`) FROM `accounts` WHERE (  state='CA' )
19/03/10 22:30:54 INFO db.IntegerSplitter: Split size: 32439; Num splits: 4 from: 1 to: 129760
19/03/10 22:30:54 INFO mapreduce.JobSubmitter: number of splits:4
19/03/10 22:30:54 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1552275592774_0005
19/03/10 22:30:55 INFO impl.YarnClientImpl: Submitted application application_1552275592774_0005
19/03/10 22:30:55 INFO mapreduce.Job: The url to track the job: http://localhost:8088/proxy/application_1552275592774_0005/
19/03/10 22:30:55 INFO mapreduce.Job: Running job: job_1552275592774_0005
19/03/10 22:31:03 INFO mapreduce.Job: Job job_1552275592774_0005 running in uber mode : false
19/03/10 22:31:03 INFO mapreduce.Job:  map 0% reduce 0%
19/03/10 22:31:11 INFO mapreduce.Job:  map 25% reduce 0%
19/03/10 22:31:17 INFO mapreduce.Job:  map 50% reduce 0%
19/03/10 22:31:23 INFO mapreduce.Job:  map 75% reduce 0%
19/03/10 22:31:30 INFO mapreduce.Job:  map 100% reduce 0%
19/03/10 22:31:30 INFO mapreduce.Job: Job job_1552275592774_0005 completed successfully
19/03/10 22:31:31 INFO mapreduce.Job: Counters: 30
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=561352
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=470
		HDFS: Number of bytes written=13524081
		HDFS: Number of read operations=16
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters 
		Launched map tasks=4
		Other local map tasks=4
		Total time spent by all maps in occupied slots (ms)=0
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=20268
		Total vcore-seconds taken by all map tasks=20268
		Total megabyte-seconds taken by all map tasks=5188608
	Map-Reduce Framework
		Map input records=92416
		Map output records=92416
		Input split bytes=470
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=283
		CPU time spent (ms)=6240
		Physical memory (bytes) snapshot=538095616
		Virtual memory (bytes) snapshot=8262397952
		Total committed heap usage (bytes)=251920384
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=13524081
19/03/10 22:31:31 INFO mapreduce.ImportJobBase: Transferred 12.8976 MB in 39.5388 seconds (334.0293 KB/sec)
19/03/10 22:31:31 INFO mapreduce.ImportJobBase: Retrieved 92416 records.
[training@localhost ~]$ --compress
