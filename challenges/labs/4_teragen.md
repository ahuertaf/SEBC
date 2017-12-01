# Put the following in challenges/labs/4_teragen.md
## The full teragen command and output

```sh
[saturn@ip-172-31-20-143 ec2-user]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=12 -Ddfs.block.size=33554432 -Dmapreduce.map.memory.mb=512 65536000 /user/saturn/tgen
17/12/01 12:22:26 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-24-48.ec2.internal/172.31.24.48:8032
17/12/01 12:22:27 INFO terasort.TeraSort: Generating 65536000 using 12
17/12/01 12:22:27 INFO mapreduce.JobSubmitter: number of splits:12
17/12/01 12:22:27 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/12/01 12:22:27 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/12/01 12:22:27 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1512149807381_0001
17/12/01 12:22:27 INFO impl.YarnClientImpl: Submitted application application_1512149807381_0001
17/12/01 12:22:27 INFO mapreduce.Job: The url to track the job: http://ip-172-31-24-48.ec2.internal:8088/proxy/application_1512149807381_0001/
17/12/01 12:22:27 INFO mapreduce.Job: Running job: job_1512149807381_0001
17/12/01 12:22:33 INFO mapreduce.Job: Job job_1512149807381_0001 running in uber mode : false
17/12/01 12:22:33 INFO mapreduce.Job:  map 0% reduce 0%
17/12/01 12:22:45 INFO mapreduce.Job:  map 15% reduce 0%
17/12/01 12:22:47 INFO mapreduce.Job:  map 23% reduce 0%
17/12/01 12:22:48 INFO mapreduce.Job:  map 29% reduce 0%
17/12/01 12:22:50 INFO mapreduce.Job:  map 34% reduce 0%
17/12/01 12:22:51 INFO mapreduce.Job:  map 38% reduce 0%
17/12/01 12:22:53 INFO mapreduce.Job:  map 42% reduce 0%
17/12/01 12:22:54 INFO mapreduce.Job:  map 46% reduce 0%
17/12/01 12:22:56 INFO mapreduce.Job:  map 50% reduce 0%
17/12/01 12:22:57 INFO mapreduce.Job:  map 57% reduce 0%
17/12/01 12:22:59 INFO mapreduce.Job:  map 60% reduce 0%
17/12/01 12:23:00 INFO mapreduce.Job:  map 67% reduce 0%
17/12/01 12:23:02 INFO mapreduce.Job:  map 71% reduce 0%
17/12/01 12:23:03 INFO mapreduce.Job:  map 75% reduce 0%
17/12/01 12:23:05 INFO mapreduce.Job:  map 79% reduce 0%
17/12/01 12:23:06 INFO mapreduce.Job:  map 82% reduce 0%
17/12/01 12:23:08 INFO mapreduce.Job:  map 84% reduce 0%
17/12/01 12:23:09 INFO mapreduce.Job:  map 85% reduce 0%
17/12/01 12:23:11 INFO mapreduce.Job:  map 86% reduce 0%
17/12/01 12:23:14 INFO mapreduce.Job:  map 90% reduce 0%
17/12/01 12:23:15 INFO mapreduce.Job:  map 93% reduce 0%
17/12/01 12:23:16 INFO mapreduce.Job:  map 94% reduce 0%
17/12/01 12:23:17 INFO mapreduce.Job:  map 96% reduce 0%
17/12/01 12:23:18 INFO mapreduce.Job:  map 100% reduce 0%
17/12/01 12:23:19 INFO mapreduce.Job: Job job_1512149807381_0001 completed successfully
17/12/01 12:23:19 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=1471538
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		saturn: Number of bytes read=1025
		saturn: Number of bytes written=6553600000
		saturn: Number of read operations=48
		saturn: Number of large read operations=0
		saturn: Number of write operations=24
	Job Counters 
		Launched map tasks=12
		Other local map tasks=12
		Total time spent by all maps in occupied slots (ms)=459493
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=459493
		Total vcore-seconds taken by all map tasks=459493
		Total megabyte-seconds taken by all map tasks=470520832
	Map-Reduce Framework
		Map input records=65536000
		Map output records=65536000
		Input split bytes=1025
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=2047
		CPU time spent (ms)=140050
		Physical memory (bytes) snapshot=2435112960
		Virtual memory (bytes) snapshot=13730336768
		Total committed heap usage (bytes)=4471128064
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=140750829423462787
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=6553600000
```

## The result of the time command

```sh
real	0m55.012s
user	0m4.437s
sys	0m0.278s
```

## The command and output of saturn dfs -ls /user/saturn/tgen

```sh
[saturn@ip-172-31-20-143 ec2-user]$ saturn dfs -ls /user/saturn/tgen
Found 13 items
-rw-r--r--   3 saturn supergroup          0 2017-12-01 12:23 /user/saturn/tgen/_SUCCESS
-rw-r--r--   3 saturn supergroup  546133400 2017-12-01 12:23 /user/saturn/tgen/part-m-00000
-rw-r--r--   3 saturn supergroup  546133300 2017-12-01 12:23 /user/saturn/tgen/part-m-00001
-rw-r--r--   3 saturn supergroup  546133300 2017-12-01 12:23 /user/saturn/tgen/part-m-00002
-rw-r--r--   3 saturn supergroup  546133400 2017-12-01 12:23 /user/saturn/tgen/part-m-00003
-rw-r--r--   3 saturn supergroup  546133300 2017-12-01 12:23 /user/saturn/tgen/part-m-00004
-rw-r--r--   3 saturn supergroup  546133300 2017-12-01 12:23 /user/saturn/tgen/part-m-00005
-rw-r--r--   3 saturn supergroup  546133400 2017-12-01 12:23 /user/saturn/tgen/part-m-00006
-rw-r--r--   3 saturn supergroup  546133300 2017-12-01 12:23 /user/saturn/tgen/part-m-00007
-rw-r--r--   3 saturn supergroup  546133300 2017-12-01 12:23 /user/saturn/tgen/part-m-00008
-rw-r--r--   3 saturn supergroup  546133400 2017-12-01 12:23 /user/saturn/tgen/part-m-00009
-rw-r--r--   3 saturn supergroup  546133300 2017-12-01 12:23 /user/saturn/tgen/part-m-00010
-rw-r--r--   3 saturn supergroup  546133300 2017-12-01 12:23 /user/saturn/tgen/part-m-00011
```

## The command and output of hadoop fsck -blocks /user/saturn

```sh
[saturn@ip-172-31-20-143 ec2-user]$ hadoop fsck -blocks /user/saturn
DEPRECATED: Use of this script to execute saturn command is deprecated.
Instead use the saturn command for it.

Connecting to namenode via http://ip-172-31-17-0.ec2.internal:50070
FSCK started by saturn (auth:SIMPLE) from /172.31.20.143 for path /user/saturn at Fri Dec 01 18:24:38 UTC 2017
.............Status: HEALTHY
 Total size:	6553600000 B
 Total dirs:	2
 Total files:	13
 Total symlinks:		0
 Total blocks (validated):	204 (avg. block size 32125490 B)
 Minimally replicated blocks:	204 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		4
 Number of racks:		1
FSCK ended at Fri Dec 01 18:24:38 UTC 2017 in 7 milliseconds


The filesystem under path '/user/saturn' is HEALTHY
```

