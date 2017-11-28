Create an end-user Linux account named with your GitHub handle
	Make sure this Linux account is added to all cluster nodes
	Create an HDFS directory under /user
Run the following exercises under this user account
Create a 10 GB file using teragen
Set the number of mappers to four
Limit the block size to 32 MB
Land the output in your user's home directory
Use the time command to report the job's duration
Run the terasort command on this file
Use the time command to report the job's duration
Land the result under your user's home directory
Report your work in storage/labs/1_terasort_tests.md, including:
The full teragen and command you used and the job output
The same for terasort
Include the time result of each job

#Teragen
Comando
```sh
time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Ddfs.block.size=1048576 100000000 /user/admin/ahuertaf/test
```

Resultado
```sh
17/11/28 11:30:07 INFO client.RMProxy: Connecting to ResourceManager at elephant/172.31.37.197:8032
17/11/28 11:30:08 INFO terasort.TeraGen: Generating 100000000 using 4
17/11/28 11:30:08 INFO mapreduce.JobSubmitter: number of splits:4
17/11/28 11:30:08 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/11/28 11:30:08 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/11/28 11:30:08 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1511888885090_0004
17/11/28 11:30:08 INFO impl.YarnClientImpl: Submitted application application_1511888885090_0004
17/11/28 11:30:08 INFO mapreduce.Job: The url to track the job: http://elephant:8088/proxy/application_1511888885090_0004/
17/11/28 11:30:08 INFO mapreduce.Job: Running job: job_1511888885090_0004
17/11/28 11:30:13 INFO mapreduce.Job: Job job_1511888885090_0004 running in uber mode : false
17/11/28 11:30:13 INFO mapreduce.Job:  map 0% reduce 0%
17/11/28 11:30:30 INFO mapreduce.Job:  map 5% reduce 0%
17/11/28 11:30:31 INFO mapreduce.Job:  map 19% reduce 0%
17/11/28 11:30:36 INFO mapreduce.Job:  map 22% reduce 0%
17/11/28 11:30:37 INFO mapreduce.Job:  map 28% reduce 0%
17/11/28 11:30:42 INFO mapreduce.Job:  map 31% reduce 0%
17/11/28 11:30:43 INFO mapreduce.Job:  map 37% reduce 0%
17/11/28 11:30:49 INFO mapreduce.Job:  map 39% reduce 0%
17/11/28 11:30:55 INFO mapreduce.Job:  map 43% reduce 0%
17/11/28 11:31:01 INFO mapreduce.Job:  map 50% reduce 0%
17/11/28 11:31:07 INFO mapreduce.Job:  map 54% reduce 0%
17/11/28 11:31:26 INFO mapreduce.Job:  map 56% reduce 0%
17/11/28 11:31:32 INFO mapreduce.Job:  map 66% reduce 0%
17/11/28 11:31:38 INFO mapreduce.Job:  map 69% reduce 0%
17/11/28 11:31:44 INFO mapreduce.Job:  map 74% reduce 0%
17/11/28 11:31:50 INFO mapreduce.Job:  map 83% reduce 0%
17/11/28 11:32:02 INFO mapreduce.Job:  map 90% reduce 0%
17/11/28 11:32:08 INFO mapreduce.Job:  map 98% reduce 0%
17/11/28 11:32:12 INFO mapreduce.Job:  map 100% reduce 0%
17/11/28 11:32:13 INFO mapreduce.Job: Job job_1511888885090_0004 completed successfully
17/11/28 11:32:13 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=579944
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=344
		HDFS: Number of bytes written=10000000000
		HDFS: Number of read operations=16
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters 
		Launched map tasks=4
		Other local map tasks=4
		Total time spent by all maps in occupied slots (ms)=454209
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=454209
		Total vcore-milliseconds taken by all map tasks=454209
		Total megabyte-milliseconds taken by all map tasks=465110016
	Map-Reduce Framework
		Map input records=100000000
		Map output records=100000000
		Input split bytes=344
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1056
		CPU time spent (ms)=170530
		Physical memory (bytes) snapshot=715218944
		Virtual memory (bytes) snapshot=6393319424
		Total committed heap usage (bytes)=1648361472
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=214760662691937609
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=10000000000

real	2m7.832s
user	0m4.659s
sys	0m0.270s
```

#Terasort

Comando
```sh
time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/admin/ahuertaf/test/* /user/admin/ahuertaf/terasort
```

Resultado
```sh
[hdfs@elephant ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/admin/ahuertaf/test/* /user/admin/ahuertaf/terasort
17/11/28 12:46:35 INFO terasort.TeraSort: starting
17/11/28 12:46:37 INFO input.FileInputFormat: Total input paths to process : 4
Spent 1307ms computing base-splits.
Spent 90ms computing TeraScheduler splits.
Computing input splits took 1397ms
Sampling 10 splits of 9540
Making 16 from 100000 sampled records
Computing parititions took 579ms
Spent 1979ms computing partitions.
17/11/28 12:46:39 INFO client.RMProxy: Connecting to ResourceManager at elephant/172.31.37.197:8032
17/11/28 12:46:39 INFO mapreduce.JobSubmitter: number of splits:9540
17/11/28 12:46:39 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1511894169161_0001
17/11/28 12:46:40 INFO impl.YarnClientImpl: Submitted application application_1511894169161_0001
17/11/28 12:46:40 INFO mapreduce.Job: The url to track the job: http://elephant:8088/proxy/application_1511894169161_0001/
17/11/28 12:46:40 INFO mapreduce.Job: Running job: job_1511894169161_0001
17/11/28 12:46:47 INFO mapreduce.Job: Job job_1511894169161_0001 running in uber mode : false
17/11/28 12:46:47 INFO mapreduce.Job:  map 0% reduce 0%
17/11/28 12:47:12 INFO mapreduce.Job:  map 1% reduce 0%
17/11/28 12:47:45 INFO mapreduce.Job:  map 2% reduce 0%
17/11/28 12:48:19 INFO mapreduce.Job:  map 3% reduce 0%
17/11/28 12:48:53 INFO mapreduce.Job:  map 4% reduce 0%
17/11/28 12:49:28 INFO mapreduce.Job:  map 5% reduce 0%
17/11/28 12:50:02 INFO mapreduce.Job:  map 6% reduce 0%
17/11/28 12:50:36 INFO mapreduce.Job:  map 7% reduce 0%
17/11/28 12:51:11 INFO mapreduce.Job:  map 8% reduce 0%
17/11/28 12:51:45 INFO mapreduce.Job:  map 9% reduce 0%
17/11/28 12:52:19 INFO mapreduce.Job:  map 10% reduce 0%
17/11/28 12:52:52 INFO mapreduce.Job:  map 11% reduce 0%
17/11/28 12:53:28 INFO mapreduce.Job:  map 12% reduce 0%
17/11/28 12:54:00 INFO mapreduce.Job:  map 13% reduce 0%
17/11/28 12:54:34 INFO mapreduce.Job:  map 14% reduce 0%
17/11/28 12:55:07 INFO mapreduce.Job:  map 15% reduce 0%
17/11/28 12:55:41 INFO mapreduce.Job:  map 16% reduce 0%
17/11/28 12:56:14 INFO mapreduce.Job:  map 17% reduce 0%
17/11/28 12:56:48 INFO mapreduce.Job:  map 18% reduce 0%
17/11/28 12:57:22 INFO mapreduce.Job:  map 19% reduce 0%
17/11/28 12:57:56 INFO mapreduce.Job:  map 20% reduce 0%
17/11/28 12:58:28 INFO mapreduce.Job:  map 21% reduce 0%
17/11/28 12:59:02 INFO mapreduce.Job:  map 22% reduce 0%
17/11/28 12:59:35 INFO mapreduce.Job:  map 23% reduce 0%
17/11/28 13:00:08 INFO mapreduce.Job:  map 24% reduce 0%
17/11/28 13:00:41 INFO mapreduce.Job:  map 25% reduce 0%
17/11/28 13:01:14 INFO mapreduce.Job:  map 26% reduce 0%
17/11/28 13:01:48 INFO mapreduce.Job:  map 27% reduce 0%
17/11/28 13:02:22 INFO mapreduce.Job:  map 28% reduce 0%
17/11/28 13:02:57 INFO mapreduce.Job:  map 29% reduce 0%
17/11/28 13:03:30 INFO mapreduce.Job:  map 30% reduce 0%
17/11/28 13:04:04 INFO mapreduce.Job:  map 31% reduce 0%
17/11/28 13:04:38 INFO mapreduce.Job:  map 32% reduce 0%
17/11/28 13:05:12 INFO mapreduce.Job:  map 33% reduce 0%
17/11/28 13:05:47 INFO mapreduce.Job:  map 34% reduce 0%
17/11/28 13:06:20 INFO mapreduce.Job:  map 35% reduce 0%
17/11/28 13:06:55 INFO mapreduce.Job:  map 36% reduce 0%
17/11/28 13:07:29 INFO mapreduce.Job:  map 37% reduce 0%
17/11/28 13:08:01 INFO mapreduce.Job:  map 38% reduce 0%
17/11/28 13:08:34 INFO mapreduce.Job:  map 39% reduce 0%
17/11/28 13:09:09 INFO mapreduce.Job:  map 40% reduce 0%
17/11/28 13:09:43 INFO mapreduce.Job:  map 41% reduce 0%
17/11/28 13:10:15 INFO mapreduce.Job:  map 42% reduce 0%
17/11/28 13:10:48 INFO mapreduce.Job:  map 43% reduce 0%
17/11/28 13:11:22 INFO mapreduce.Job:  map 44% reduce 0%
17/11/28 13:11:55 INFO mapreduce.Job:  map 45% reduce 0%
17/11/28 13:12:29 INFO mapreduce.Job:  map 46% reduce 0%
17/11/28 13:13:01 INFO mapreduce.Job:  map 47% reduce 0%
17/11/28 13:13:34 INFO mapreduce.Job:  map 48% reduce 0%
17/11/28 13:14:08 INFO mapreduce.Job:  map 49% reduce 0%
17/11/28 13:14:41 INFO mapreduce.Job:  map 50% reduce 0%
17/11/28 13:15:15 INFO mapreduce.Job:  map 51% reduce 0%
17/11/28 13:15:49 INFO mapreduce.Job:  map 52% reduce 0%
17/11/28 13:16:22 INFO mapreduce.Job:  map 53% reduce 0%
17/11/28 13:16:55 INFO mapreduce.Job:  map 54% reduce 0%
17/11/28 13:17:30 INFO mapreduce.Job:  map 55% reduce 0%
17/11/28 13:18:04 INFO mapreduce.Job:  map 56% reduce 0%
17/11/28 13:18:38 INFO mapreduce.Job:  map 57% reduce 0%
17/11/28 13:19:12 INFO mapreduce.Job:  map 58% reduce 0%
17/11/28 13:19:47 INFO mapreduce.Job:  map 59% reduce 0%
17/11/28 13:20:22 INFO mapreduce.Job:  map 60% reduce 0%
17/11/28 13:20:56 INFO mapreduce.Job:  map 61% reduce 0%
17/11/28 13:21:30 INFO mapreduce.Job:  map 62% reduce 0%
17/11/28 13:22:04 INFO mapreduce.Job:  map 63% reduce 0%
17/11/28 13:22:36 INFO mapreduce.Job:  map 64% reduce 0%
17/11/28 13:23:11 INFO mapreduce.Job:  map 65% reduce 0%
17/11/28 13:23:45 INFO mapreduce.Job:  map 66% reduce 0%
17/11/28 13:24:18 INFO mapreduce.Job:  map 67% reduce 0%
17/11/28 13:24:50 INFO mapreduce.Job:  map 68% reduce 0%
17/11/28 13:25:24 INFO mapreduce.Job:  map 69% reduce 0%
17/11/28 13:25:58 INFO mapreduce.Job:  map 70% reduce 0%
17/11/28 13:26:31 INFO mapreduce.Job:  map 71% reduce 0%
17/11/28 13:27:04 INFO mapreduce.Job:  map 72% reduce 0%
17/11/28 13:27:38 INFO mapreduce.Job:  map 73% reduce 0%
17/11/28 13:28:11 INFO mapreduce.Job:  map 74% reduce 0%
17/11/28 13:28:44 INFO mapreduce.Job:  map 75% reduce 0%
17/11/28 13:29:17 INFO mapreduce.Job:  map 76% reduce 0%
17/11/28 13:29:51 INFO mapreduce.Job:  map 77% reduce 0%
17/11/28 13:30:25 INFO mapreduce.Job:  map 78% reduce 0%
17/11/28 13:30:58 INFO mapreduce.Job:  map 79% reduce 0%
17/11/28 13:31:33 INFO mapreduce.Job:  map 80% reduce 0%
17/11/28 13:32:05 INFO mapreduce.Job:  map 80% reduce 2%
17/11/28 13:32:09 INFO mapreduce.Job:  map 80% reduce 4%
17/11/28 13:32:10 INFO mapreduce.Job:  map 80% reduce 10%
17/11/28 13:32:12 INFO mapreduce.Job:  map 80% reduce 11%
17/11/28 13:32:13 INFO mapreduce.Job:  map 80% reduce 12%
17/11/28 13:32:14 INFO mapreduce.Job:  map 80% reduce 13%
17/11/28 13:32:15 INFO mapreduce.Job:  map 80% reduce 14%
17/11/28 13:32:18 INFO mapreduce.Job:  map 80% reduce 18%
17/11/28 13:32:19 INFO mapreduce.Job:  map 80% reduce 19%
17/11/28 13:32:21 INFO mapreduce.Job:  map 80% reduce 20%
17/11/28 13:32:22 INFO mapreduce.Job:  map 80% reduce 21%
17/11/28 13:32:23 INFO mapreduce.Job:  map 81% reduce 21%
17/11/28 13:32:24 INFO mapreduce.Job:  map 81% reduce 22%
17/11/28 13:32:27 INFO mapreduce.Job:  map 81% reduce 23%
17/11/28 13:32:29 INFO mapreduce.Job:  map 81% reduce 24%
17/11/28 13:32:31 INFO mapreduce.Job:  map 81% reduce 25%
17/11/28 13:33:13 INFO mapreduce.Job:  map 82% reduce 25%
17/11/28 13:33:21 INFO mapreduce.Job:  map 82% reduce 26%
17/11/28 13:34:01 INFO mapreduce.Job:  map 83% reduce 26%
17/11/28 13:34:51 INFO mapreduce.Job:  map 84% reduce 26%
17/11/28 13:35:39 INFO mapreduce.Job:  map 85% reduce 26%
17/11/28 13:35:58 INFO mapreduce.Job:  map 85% reduce 27%
17/11/28 13:36:29 INFO mapreduce.Job:  map 86% reduce 27%
17/11/28 13:37:18 INFO mapreduce.Job:  map 87% reduce 27%
17/11/28 13:38:07 INFO mapreduce.Job:  map 88% reduce 27%
17/11/28 13:38:34 INFO mapreduce.Job:  map 88% reduce 28%
17/11/28 13:38:55 INFO mapreduce.Job:  map 89% reduce 28%
17/11/28 13:39:42 INFO mapreduce.Job:  map 90% reduce 28%
17/11/28 13:40:31 INFO mapreduce.Job:  map 91% reduce 28%
17/11/28 13:41:09 INFO mapreduce.Job:  map 91% reduce 29%
17/11/28 13:41:21 INFO mapreduce.Job:  map 92% reduce 29%
17/11/28 13:42:08 INFO mapreduce.Job:  map 93% reduce 29%
17/11/28 13:42:58 INFO mapreduce.Job:  map 94% reduce 29%
17/11/28 13:43:45 INFO mapreduce.Job:  map 94% reduce 30%
17/11/28 13:43:46 INFO mapreduce.Job:  map 95% reduce 30%
17/11/28 13:44:35 INFO mapreduce.Job:  map 96% reduce 30%
17/11/28 13:45:23 INFO mapreduce.Job:  map 97% reduce 30%
17/11/28 13:46:13 INFO mapreduce.Job:  map 98% reduce 30%
17/11/28 13:46:21 INFO mapreduce.Job:  map 98% reduce 31%
17/11/28 13:47:02 INFO mapreduce.Job:  map 99% reduce 31%
17/11/28 13:47:49 INFO mapreduce.Job:  map 100% reduce 31%
17/11/28 13:48:13 INFO mapreduce.Job:  map 100% reduce 32%
17/11/28 13:48:14 INFO mapreduce.Job:  map 100% reduce 33%
17/11/28 13:48:15 INFO mapreduce.Job:  map 100% reduce 36%
17/11/28 13:48:16 INFO mapreduce.Job:  map 100% reduce 38%
17/11/28 13:48:17 INFO mapreduce.Job:  map 100% reduce 45%
17/11/28 13:48:19 INFO mapreduce.Job:  map 100% reduce 51%
17/11/28 13:48:20 INFO mapreduce.Job:  map 100% reduce 56%
17/11/28 13:48:21 INFO mapreduce.Job:  map 100% reduce 61%
17/11/28 13:48:22 INFO mapreduce.Job:  map 100% reduce 62%
17/11/28 13:48:23 INFO mapreduce.Job:  map 100% reduce 69%
17/11/28 13:48:25 INFO mapreduce.Job:  map 100% reduce 72%
17/11/28 13:48:26 INFO mapreduce.Job:  map 100% reduce 77%
17/11/28 13:48:27 INFO mapreduce.Job:  map 100% reduce 81%
17/11/28 13:48:28 INFO mapreduce.Job:  map 100% reduce 84%
17/11/28 13:48:29 INFO mapreduce.Job:  map 100% reduce 88%
17/11/28 13:48:30 INFO mapreduce.Job:  map 100% reduce 94%
17/11/28 13:48:31 INFO mapreduce.Job:  map 100% reduce 98%
17/11/28 13:48:37 INFO mapreduce.Job:  map 100% reduce 100%
17/11/28 13:48:38 INFO mapreduce.Job: Job job_1511894169161_0001 completed successfully
17/11/28 13:48:38 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=4433851031
		FILE: Number of bytes written=10160422775
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=10001163880
		HDFS: Number of bytes written=10000000000
		HDFS: Number of read operations=28668
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=32
	Job Counters 
		Launched map tasks=9540
		Launched reduce tasks=16
		Data-local map tasks=9540
		Total time spent by all maps in occupied slots (ms)=73940099
		Total time spent by all reduces in occupied slots (ms)=14958033
		Total time spent by all map tasks (ms)=73940099
		Total time spent by all reduce tasks (ms)=14958033
		Total vcore-milliseconds taken by all map tasks=73940099
		Total vcore-milliseconds taken by all reduce tasks=14958033
		Total megabyte-milliseconds taken by all map tasks=75714661376
		Total megabyte-milliseconds taken by all reduce tasks=15317025792
	Map-Reduce Framework
		Map input records=100000000
		Map output records=100000000
		Map output bytes=10200000000
		Map output materialized bytes=4306106164
		Input split bytes=1163880
		Combine input records=0
		Combine output records=0
		Reduce input groups=100000000
		Reduce shuffle bytes=4306106164
		Reduce input records=100000000
		Reduce output records=100000000
		Spilled Records=200000000
		Shuffled Maps =152640
		Failed Shuffles=0
		Merged Map outputs=152640
		GC time elapsed (ms)=744910
		CPU time spent (ms)=29495770
		Physical memory (bytes) snapshot=5037557534720
		Virtual memory (bytes) snapshot=15266828201984
		Total committed heap usage (bytes)=5112569266176
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=10000000000
	File Output Format Counters 
		Bytes Written=10000000000
17/11/28 13:48:38 INFO terasort.TeraSort: done

real	62m3.276s
user	0m16.818s
sys	0m0.968s
```
