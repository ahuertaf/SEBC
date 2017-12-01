```sh
[haley@ip-172-31-20-143 ec2-user]$ hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar pi 10 100
Number of Maps  = 10
Samples per Map = 100
Wrote input for Map #0
Wrote input for Map #1
Wrote input for Map #2
Wrote input for Map #3
Wrote input for Map #4
Wrote input for Map #5
Wrote input for Map #6
Wrote input for Map #7
Wrote input for Map #8
Wrote input for Map #9
Starting Job
17/12/01 13:30:29 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-24-48.ec2.internal/172.31.24.48:8032
17/12/01 13:30:29 INFO hdfs.DFSClient: Created token for haley: HDFS_DELEGATION_TOKEN owner=haley@AHUERTAF.COM, renewer=yarn, realUser=, issueDate=1512156629409, maxDate=1512761429409, sequenceNumber=7, masterKeyId=2 on 172.31.17.0:8020
17/12/01 13:30:29 INFO security.TokenCache: Got dt for hdfs://ip-172-31-17-0.ec2.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.17.0:8020, Ident: (token for haley: HDFS_DELEGATION_TOKEN owner=haley@AHUERTAF.COM, renewer=yarn, realUser=, issueDate=1512156629409, maxDate=1512761429409, sequenceNumber=7, masterKeyId=2)
17/12/01 13:30:29 INFO input.FileInputFormat: Total input paths to process : 10
17/12/01 13:30:29 INFO mapreduce.JobSubmitter: number of splits:10
17/12/01 13:30:29 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1512154687484_0002
17/12/01 13:30:29 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.17.0:8020, Ident: (token for haley: HDFS_DELEGATION_TOKEN owner=haley@AHUERTAF.COM, renewer=yarn, realUser=, issueDate=1512156629409, maxDate=1512761429409, sequenceNumber=7, masterKeyId=2)
17/12/01 13:30:30 INFO impl.YarnClientImpl: Submitted application application_1512154687484_0002
17/12/01 13:30:30 INFO mapreduce.Job: The url to track the job: http://ip-172-31-24-48.ec2.internal:8088/proxy/application_1512154687484_0002/
17/12/01 13:30:30 INFO mapreduce.Job: Running job: job_1512154687484_0002
17/12/01 13:30:38 INFO mapreduce.Job: Job job_1512154687484_0002 running in uber mode : false
17/12/01 13:30:38 INFO mapreduce.Job:  map 0% reduce 0%
17/12/01 13:30:44 INFO mapreduce.Job:  map 20% reduce 0%
17/12/01 13:30:48 INFO mapreduce.Job:  map 60% reduce 0%
17/12/01 13:30:49 INFO mapreduce.Job:  map 100% reduce 0%
17/12/01 13:30:54 INFO mapreduce.Job:  map 100% reduce 100%
17/12/01 13:30:54 INFO mapreduce.Job: Job job_1512154687484_0002 completed successfully
17/12/01 13:30:54 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=93
		FILE: Number of bytes written=1365115
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=2830
		HDFS: Number of bytes written=215
		HDFS: Number of read operations=43
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=3
	Job Counters 
		Launched map tasks=10
		Launched reduce tasks=1
		Data-local map tasks=10
		Total time spent by all maps in occupied slots (ms)=72345
		Total time spent by all reduces in occupied slots (ms)=3058
		Total time spent by all map tasks (ms)=72345
		Total time spent by all reduce tasks (ms)=3058
		Total vcore-seconds taken by all map tasks=72345
		Total vcore-seconds taken by all reduce tasks=3058
		Total megabyte-seconds taken by all map tasks=74081280
		Total megabyte-seconds taken by all reduce tasks=3131392
	Map-Reduce Framework
		Map input records=10
		Map output records=20
		Map output bytes=180
		Map output materialized bytes=340
		Input split bytes=1650
		Combine input records=0
		Combine output records=0
		Reduce input groups=2
		Reduce shuffle bytes=340
		Reduce input records=20
		Reduce output records=0
		Spilled Records=40
		Shuffled Maps =10
		Failed Shuffles=0
		Merged Map outputs=10
		GC time elapsed (ms)=285
		CPU time spent (ms)=6960
		Physical memory (bytes) snapshot=5296295936
		Virtual memory (bytes) snapshot=17557725184
		Total committed heap usage (bytes)=5536481280
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=1180
	File Output Format Counters 
		Bytes Written=97
Job Finished in 25.502 seconds
Estimated value of Pi is 3.14800000000000000000
```
