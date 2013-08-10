###Born on the Fourth of July

accord  高性能的分布式协调服务，尤其适用于写密集场景。原作者已放弃对项目的维护，2013年7月4日我接管了该项目。
当今分布式协调服务以zookeeper最为有名，奇怪的是居然没有棋逢对手的同类项目，这在当今分布式极其活跃火爆的大环境下显得特别另类。分布式文件系统有HDFS、Riak、QFS，分布式数据库有HBASE、Voldemort，缓存有memcached 、redis，文档数据库有mongodb、couchdb。
分布式协调服务应当有更多的选择，不应当zookeeper一枝独秀。

** Accord project **

NOTE: Now, this project is marked as deprecated, because we've observed that write-intensive
workload is much less important than read-intensive workload for coordination service. 
Please use ZooKeeper.

* Overview
----------
- Accord is a coordination service(like ZooKeeper). It features :

1. Accord focuses on write-intensive workloads unlike ZooKeeper. ZooKeeper forwards all write requests to a master server. It can be bottleneck in write-intensive workloads. The below benchmark demonstrates that the write-operation throughput of Accord is much higher than one of ZooKeeper (up to 20 times better throughput at persistent mode, and up to 18 times better throughput at in-memory mode).
2. More flexible transaction support. Not only write, del operations, but also cmp, copy, read operations are supported in transaction operations.
3. In-memory mode and persistent mode support.
4. Message size is unbounded, and partial update is supported.


* Project Page
----------
- Getting started / Performance benchmark is avalable from our project page. Please visit http://www.osrg.net/accord

* Directory structure
----------
- conductor	: Server-side daemon
- libacrd 	: Client-side library
- test		: Test and benchmark programs. Files in this directory are useful as sample programs of Accord.
- include	: Header files
- lib	 	: Utility library

* API Documentation
----------
- Please see include/accord.h or http://www.osrg.net/accord/api.txt
- Programs in ACRD_ROOT/test are very useful to understand how to use accord API.

