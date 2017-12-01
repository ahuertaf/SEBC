## Terasort

```sh
[saturn@ip-172-31-24-48 ec2-user]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Ddfs.block.size=33554432 1000000000 /user/saturn/tsort
17/12/01 13:28:03 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-24-48.ec2.internal/172.31.24.48:8032
17/12/01 13:28:03 INFO hdfs.DFSClient: Created token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@AHUERTAF.COM, renewer=yarn, realUser=, issueDate=1512156483536, maxDate=1512761283536, sequenceNumber=6, masterKeyId=2 on 172.31.17.0:8020
17/12/01 13:28:03 INFO security.TokenCache: Got dt for hdfs://ip-172-31-17-0.ec2.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.17.0:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@AHUERTAF.COM, renewer=yarn, realUser=, issueDate=1512156483536, maxDate=1512761283536, sequenceNumber=6, masterKeyId=2)
17/12/01 13:28:03 INFO terasort.TeraSort: Generating 1000000000 using 4
17/12/01 13:28:03 INFO mapreduce.JobSubmitter: number of splits:4
17/12/01 13:28:03 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/12/01 13:28:03 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/12/01 13:28:04 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1512154687484_0001
17/12/01 13:28:04 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.17.0:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@AHUERTAF.COM, renewer=yarn, realUser=, issueDate=1512156483536, maxDate=1512761283536, sequenceNumber=6, masterKeyId=2)
17/12/01 13:28:04 INFO impl.YarnClientImpl: Submitted application application_1512154687484_0001
17/12/01 13:28:05 INFO mapreduce.Job: The url to track the job: http://ip-172-31-24-48.ec2.internal:8088/proxy/application_1512154687484_0001/
17/12/01 13:28:05 INFO mapreduce.Job: Running job: job_1512154687484_0001
17/12/01 13:28:13 INFO mapreduce.Job: Job job_1512154687484_0001 running in uber mode : false
17/12/01 13:28:13 INFO mapreduce.Job:  map 0% reduce 0%
17/12/01 13:28:29 INFO mapreduce.Job:  map 1% reduce 0%
17/12/01 13:28:35 INFO mapreduce.Job:  map 2% reduce 0%
17/12/01 13:28:44 INFO mapreduce.Job:  map 3% reduce 0%
17/12/01 13:28:53 INFO mapreduce.Job:  map 4% reduce 0%
17/12/01 13:28:59 INFO mapreduce.Job:  map 5% reduce 0%
17/12/01 13:29:08 INFO mapreduce.Job:  map 6% reduce 0%
17/12/01 13:29:17 INFO mapreduce.Job:  map 7% reduce 0%
17/12/01 13:29:26 INFO mapreduce.Job:  map 8% reduce 0%
17/12/01 13:29:32 INFO mapreduce.Job:  map 9% reduce 0%
17/12/01 13:29:41 INFO mapreduce.Job:  map 10% reduce 0%
17/12/01 13:29:50 INFO mapreduce.Job:  map 11% reduce 0%
17/12/01 13:29:56 INFO mapreduce.Job:  map 12% reduce 0%
17/12/01 13:30:05 INFO mapreduce.Job:  map 13% reduce 0%
17/12/01 13:30:14 INFO mapreduce.Job:  map 14% reduce 0%
17/12/01 13:30:20 INFO mapreduce.Job:  map 15% reduce 0%
17/12/01 13:30:29 INFO mapreduce.Job:  map 16% reduce 0%
17/12/01 13:30:38 INFO mapreduce.Job:  map 17% reduce 0%
17/12/01 13:30:44 INFO mapreduce.Job:  map 18% reduce 0%
17/12/01 13:30:53 INFO mapreduce.Job:  map 19% reduce 0%
17/12/01 13:31:02 INFO mapreduce.Job:  map 20% reduce 0%
17/12/01 13:31:08 INFO mapreduce.Job:  map 21% reduce 0%
17/12/01 13:31:17 INFO mapreduce.Job:  map 22% reduce 0%
17/12/01 13:31:27 INFO mapreduce.Job:  map 23% reduce 0%
17/12/01 13:31:36 INFO mapreduce.Job:  map 24% reduce 0%
17/12/01 13:31:42 INFO mapreduce.Job:  map 25% reduce 0%
17/12/01 13:31:51 INFO mapreduce.Job:  map 26% reduce 0%
17/12/01 13:32:00 INFO mapreduce.Job:  map 27% reduce 0%
17/12/01 13:32:06 INFO mapreduce.Job:  map 28% reduce 0%
17/12/01 13:32:15 INFO mapreduce.Job:  map 29% reduce 0%
17/12/01 13:32:24 INFO mapreduce.Job:  map 30% reduce 0%
17/12/01 13:32:30 INFO mapreduce.Job:  map 31% reduce 0%
17/12/01 13:32:39 INFO mapreduce.Job:  map 32% reduce 0%
17/12/01 13:32:48 INFO mapreduce.Job:  map 33% reduce 0%
17/12/01 13:32:54 INFO mapreduce.Job:  map 34% reduce 0%
17/12/01 13:33:03 INFO mapreduce.Job:  map 35% reduce 0%
17/12/01 13:33:12 INFO mapreduce.Job:  map 36% reduce 0%
17/12/01 13:33:21 INFO mapreduce.Job:  map 37% reduce 0%
17/12/01 13:33:27 INFO mapreduce.Job:  map 38% reduce 0%
17/12/01 13:33:36 INFO mapreduce.Job:  map 39% reduce 0%
17/12/01 13:33:45 INFO mapreduce.Job:  map 40% reduce 0%
17/12/01 13:33:52 INFO mapreduce.Job:  map 41% reduce 0%
17/12/01 13:34:01 INFO mapreduce.Job:  map 42% reduce 0%
17/12/01 13:34:10 INFO mapreduce.Job:  map 43% reduce 0%
17/12/01 13:34:16 INFO mapreduce.Job:  map 44% reduce 0%
17/12/01 13:34:25 INFO mapreduce.Job:  map 45% reduce 0%
17/12/01 13:34:34 INFO mapreduce.Job:  map 46% reduce 0%
17/12/01 13:34:40 INFO mapreduce.Job:  map 47% reduce 0%
17/12/01 13:34:49 INFO mapreduce.Job:  map 48% reduce 0%
17/12/01 13:34:58 INFO mapreduce.Job:  map 49% reduce 0%
17/12/01 13:35:07 INFO mapreduce.Job:  map 50% reduce 0%
17/12/01 13:35:13 INFO mapreduce.Job:  map 51% reduce 0%
17/12/01 13:35:22 INFO mapreduce.Job:  map 52% reduce 0%
17/12/01 13:35:31 INFO mapreduce.Job:  map 53% reduce 0%
17/12/01 13:35:40 INFO mapreduce.Job:  map 54% reduce 0%
17/12/01 13:35:47 INFO mapreduce.Job:  map 55% reduce 0%
17/12/01 13:35:56 INFO mapreduce.Job:  map 56% reduce 0%
17/12/01 13:36:05 INFO mapreduce.Job:  map 57% reduce 0%
17/12/01 13:36:11 INFO mapreduce.Job:  map 58% reduce 0%
17/12/01 13:36:20 INFO mapreduce.Job:  map 59% reduce 0%
17/12/01 13:36:29 INFO mapreduce.Job:  map 60% reduce 0%
17/12/01 13:36:38 INFO mapreduce.Job:  map 61% reduce 0%
17/12/01 13:36:44 INFO mapreduce.Job:  map 62% reduce 0%
17/12/01 13:36:53 INFO mapreduce.Job:  map 63% reduce 0%
17/12/01 13:37:02 INFO mapreduce.Job:  map 64% reduce 0%
17/12/01 13:37:08 INFO mapreduce.Job:  map 65% reduce 0%
17/12/01 13:37:17 INFO mapreduce.Job:  map 66% reduce 0%
17/12/01 13:37:26 INFO mapreduce.Job:  map 67% reduce 0%
17/12/01 13:37:32 INFO mapreduce.Job:  map 68% reduce 0%
17/12/01 13:37:41 INFO mapreduce.Job:  map 69% reduce 0%
17/12/01 13:37:50 INFO mapreduce.Job:  map 70% reduce 0%
17/12/01 13:37:56 INFO mapreduce.Job:  map 71% reduce 0%
17/12/01 13:38:05 INFO mapreduce.Job:  map 72% reduce 0%
17/12/01 13:38:14 INFO mapreduce.Job:  map 73% reduce 0%
17/12/01 13:38:23 INFO mapreduce.Job:  map 74% reduce 0%
17/12/01 13:38:29 INFO mapreduce.Job:  map 75% reduce 0%
17/12/01 13:38:38 INFO mapreduce.Job:  map 76% reduce 0%
17/12/01 13:38:47 INFO mapreduce.Job:  map 77% reduce 0%
17/12/01 13:38:53 INFO mapreduce.Job:  map 78% reduce 0%
17/12/01 13:39:02 INFO mapreduce.Job:  map 79% reduce 0%
17/12/01 13:39:11 INFO mapreduce.Job:  map 80% reduce 0%
17/12/01 13:39:17 INFO mapreduce.Job:  map 81% reduce 0%
17/12/01 13:39:26 INFO mapreduce.Job:  map 82% reduce 0%
17/12/01 13:39:35 INFO mapreduce.Job:  map 83% reduce 0%
17/12/01 13:39:41 INFO mapreduce.Job:  map 84% reduce 0%
17/12/01 13:39:50 INFO mapreduce.Job:  map 85% reduce 0%
17/12/01 13:39:59 INFO mapreduce.Job:  map 86% reduce 0%
17/12/01 13:40:08 INFO mapreduce.Job:  map 87% reduce 0%
17/12/01 13:40:15 INFO mapreduce.Job:  map 88% reduce 0%
17/12/01 13:40:23 INFO mapreduce.Job:  map 89% reduce 0%
17/12/01 13:40:32 INFO mapreduce.Job:  map 90% reduce 0%
17/12/01 13:40:40 INFO mapreduce.Job:  map 91% reduce 0%
17/12/01 13:40:48 INFO mapreduce.Job:  map 92% reduce 0%
17/12/01 13:40:57 INFO mapreduce.Job:  map 93% reduce 0%
17/12/01 13:41:04 INFO mapreduce.Job:  map 94% reduce 0%
17/12/01 13:41:13 INFO mapreduce.Job:  map 95% reduce 0%
17/12/01 13:41:22 INFO mapreduce.Job:  map 96% reduce 0%
17/12/01 13:41:31 INFO mapreduce.Job:  map 97% reduce 0%
17/12/01 13:41:37 INFO mapreduce.Job:  map 98% reduce 0%
17/12/01 13:41:46 INFO mapreduce.Job:  map 99% reduce 0%
17/12/01 13:41:55 INFO mapreduce.Job:  map 100% reduce 0%
17/12/01 13:41:56 INFO mapreduce.Job: Job job_1512154687484_0001 completed successfully
17/12/01 13:41:56 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=493580
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=344
		HDFS: Number of bytes written=100000000000
		HDFS: Number of read operations=16
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters 
		Launched map tasks=4
		Other local map tasks=4
		Total time spent by all maps in occupied slots (ms)=3269843
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=3269843
		Total vcore-seconds taken by all map tasks=3269843
		Total megabyte-seconds taken by all map tasks=3348319232
	Map-Reduce Framework
		Map input records=1000000000
		Map output records=1000000000
		Input split bytes=344
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=16960
		CPU time spent (ms)=1350850
		Physical memory (bytes) snapshot=1014341632
		Virtual memory (bytes) snapshot=6387679232
		Total committed heap usage (bytes)=1611661312
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=2147523228284173905
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=100000000000

real	13m55.190s
user	0m7.066s
sys	0m0.493s
```



