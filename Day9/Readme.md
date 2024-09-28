
### Date: 28/09/2024
### Session 9: Applications
-------------------------------------------------
### Topics: 	
	-Hadoop
	-HDFS
	-MapReduce

![image](https://github.com/user-attachments/assets/556705b8-2402-4a0f-b9ed-05fc3d0a4c46)

	Data: collection of Facts and figures.
	-unprocessed information=> raw data
![image](https://github.com/user-attachments/assets/d37262b0-d6d6-4f71-b205-2fb389dc74be)

	Challenege: To handle 100 milion customers and select 10 custermers for 100$ voucher?
![image](https://github.com/user-attachments/assets/e5baae2a-6e55-4796-bff2-b0be0a5fa335)

	Solution: Apache Hadoop
	-Storage: huge amount of data, so HDFS (Hadoop Distributed File System) 
	-Processing: Map Reduce  will be applied to data distributed over network
	-Analysis: Pig, Hive, can be used to analyse the data.
	-Cost: Hadoop is the open source so the cost is no more an issue.


### Hadoop: 
	 -open source framework used for storing and processing Big Data in a distributed manure.
	 -Hadoop is licensed under Apache Software Foundation (ASF)
	 -Hadoop programs can be written in JAva programming language.
	 -Doug Cutting and Mike  Cafarella developed Hadoop.
	 -Google, invented Map Reduce technology, and modeled as GFS (Google File System)
	 
###  Hadoop Architecture:
 ---------------------
	 HDFS: Hadoop Distributed File System:
	 -HDFS runs on the top of the existing file system on each 
	 node in a Hadoop cluster.
	 -HDFS is a block structured file system where each file is divided into blocks of the pre-determined size.
	 
![image](https://github.com/user-attachments/assets/8fe6be56-5c44-475b-8f1f-21421b9be42c)
 
### Hadoop MapReduce:
	 -MapReduce framework consist of single master node (Job Tracker) and n number of slave nodes( Task Tracker) where n can be 1000s. Master manages, maintains and monitors the slaves while slaves are the actual worker node
	 -Parallel processing of large dataset.
	 
	 YARN: Yet Another Resource Negotiator
	 -It is a framework responsible for assigning computational resouces for application excution and cluster management.
	 -YARN consist of 3 componenets:
	 	-Resorce Manager (one per cluster)
		-Application MAster (one per master)
		-Node Managers (one per node)
 
### High LEvel Architecture of HAdoop:
 ----------------------------------

![image](https://github.com/user-attachments/assets/8dbbe438-56fe-45e4-a6ba-e558a23ddc4f)

 ### Hadoop Ecosystem:
 -----------------
	 -It is neither a programming language nor a service.
	 -It is a platform or framwork which solves bif data problems.
	 -It encompases of services (storing, analyzing and maintaining) inside it.
	 It includes official Apache opensource projects and a wide range of commercial tools and solutions:
		-HDFA : Hadoop Distributed File system
		-YARN : Yet Another Resouce Negosiator
		-MapReduce: Data Processing using programming
		-Spark : In memeory Dat Processing
		-PIG, HIVE : Data processing Services using Query (SQL )
		-HBase : NoSQL Databased
		-Mahout, SparkLib : Machine Learning
		-Apache Drill : SQL on Hadoop
		-Zookeeper: Managing clusters
		-Oozie: Job Scheduling
		-Flume, Sqoob : Data Ingesting Services
		-Solr & Lucene : Searching and Indexing
![image](https://github.com/user-attachments/assets/8651133b-efdf-41d8-b530-d3f8aa97192c)
	
### HDFS:
-----
	-java based distributed file system that allows to store large data across multiple nodes in a Hadoop cluster.

### Features of HDFS:
------------------
	-It is suitable for the distributed storage and processing.
	-Hadoop provides a command interface to interact with HDFS.
	-The built-in servers of namenode and datanode help users to easily check the status of cluster.
	-Streaming access to file system data.
	-HDFS provides file permissions and authentication.
	
	Node: a computer: non-enterprise, commodity hardware for nodes that contain data.
	
	Rack: Collection of node. A rack is a collection of 30-40 nodes that are physically stored close together and are all connected to the same network switch.

	Cluster: A Hadoop cluster is a collection of rack.
![image](https://github.com/user-attachments/assets/dc270b7a-121e-427e-a331-9b34af2ba1bf)


### Componenets of HDFS:
---------------------
	-block -structured file system where each file is divided into blocks of a pre-defined size 128MB.
	HDFS architectue follows: MAster/Slave Architecture, where a cluster comprises of a single NameNode (MAster Node) and all the other nodes are Data Node(Slave node)
	
	
	Name Node: Master node in the Apache HDFS Architecture that maintains and manges the blocks present on the Data Nodes(slave nodes)
![image](https://github.com/user-attachments/assets/b37d36d4-b180-4b7e-983e-6714e52a6310)


### Function:
--------
	1. Master daemon that maintains and manges the Data NodesSlave nodes)
	2. Manages the file system namespaces.
	3. It maintains metadata of all files stored int eh cluster.
	4. It regularly receives a HEartbeat and block report from all the Data Nodes in the cluser to ensure that the DataNodes are live.
	5.In case of the DataNode failure, the NameNode chooses new DataNodes for new replicas, balances disl usage and manges the communication traffic to the DataNodes.



	Data Node:
	
	-Data Nodes are the slave nodes in HDFS.
	-They are node harware, i.e., non-expensive system which is not of high quality or high - availbility.
	
	Function:
	1. The actual data is stores in Data Nodes.
	2. They perform read-write operations on the file system as per client request.
	3. They perform the operations like block creation, deletion, and replication according to the instructions of the namenode.
	
	Replication Management:
	-------------------------
	-HDFS performs replication to provide Fault Tolerant and to improve data reliability.
	- Ther could be asituation where the data is lostin many ways-node is dowm, Node lost the netweork connectivity, a node is physically damaged and node is intentionally made unavailable for horizontal scalling.
	-In these situation data will not be availble, if the replication is not made.HDFS maintains 3 copies of each Data bloack in different nodes and differnt racks. By doing this, data is made availble even if one of the system is down.
	-Downtime will be reduces by making data replicants. This improve the reliability and fault tolerance of the system.
	
	
	MapReduce: 
	-A programming model and processing engine used for large scale data processing in HAdoop.
	
	Key concept:
	1. Map Function:
		-Takes input data and produces intermediate key-value pairs.
		
	2. Reduce function:
		-Aggregates the intermediate key-value pairs to generate the final output.
		
	Execution Flow:
	---------------
	1. Input Split
		-The input data a is split into smaller chunks.
	
	2. Map Phase
		-Each split is processed by Mapper, generating ke-value pairs.
	
	3. Shuffle and Sort
		-Intermediate key-value pairs are shuffled and sorted for the reduce phase.
	
	4. Reduce phase
		-Reduces aggregate the key-value pairs and produce the final output.
	
### YARN : Yet Another Resource Negotiator:
 -----------------------------------------
	 -It is a resource management layer of HAdoop, which introduced in HAdoop 2.0.
	 -It allows multiple applications to share the cluster's resources and execute jobs simultaneously.
	 -Decouple resource management from Mapreduce, allowing HAdoop to support other processing modeles.
	
		Key Componenets:
		-------------------
		1. ResourceManager (RM):
		-Global resource manager for the HAdoopcluster.
		-Assign resources (CPU, memory) across all applications.
		-Handles job scheduling and resource allocation.
		
		2.NodeManager: (NM)
		-Runs on each node and monitor resources like CPU, memory and disk usage.
		-Manages containers which are the units of resources for each task.
		-Reports node health and resource utilization to resource Manager.
		
		3. ApplicaitonMaster(AM)
		-Manages the execution of an individual application.
		-Negotiates resources with Resource Manager and coordinates tasks on NodeManager.
		-Can handle MapReduce jobs, Spark jobs aor any other YARN suppoerted applications.
		
		
	Advantages of YARN:
		-Better resource utilization
		-Scalability
		-Flexibiltiy
	
### Hadoop Environment:
------------------
	Software requirement:
		-Java JDK 
		-Hadoop distribution
		-Linux based Operating System
	
	Steps to set up a single -Node Hadoop cluster:
	-----------------------------------------------
	1. Install Java JDK
	2. Download HAdoop
	3. Configure  Environment variable
	4. Format the Namenode
	5. Start HAdoop Services
	6. Access the Wen UI : http:// localhost:50070
	
	Operation Modes:
	----------------
	1. Standlone Mode:
		-DEfault mode where HAdoop runs on a single JVM without HDFS and YARN
		-Useful for testing and development on the local machine.
		-Does not provide distributed storage or processing.
		
	2. Pseudo Mode or Distributed mode:
		-Hadoop uses on a cluster of machines, providing full distributed storage (HDFS) and processing (MapReduce/YARN)
		-Suitable for production environment with high data volumes and multiple nodes.
		
	3. Full Distributed Mode:
		-Hadoop runs on a cluster of machines, providing full distributed storage (HDFS) and processing (MapReduce/YARN).
		-Suitable fpr production environment with high data volumes and multiple nodes.

### Streaming in Hadoop:
-----------------------
	-Hadoop Streaming:
		-A utility that allows user to create and run MapReduce jobs using any programming language (Python, Perl, Ruby, etc.,) instead of Java.
		-Works by using standar input(stdin) and standard output (stdout) to read and write data between the mapper, reduce and Hadoop's distribution system.
		-Suitable for users more comfertable with non-java languages but still wanting to leverage HAdoop's distributed computation capabilities.
![image](https://github.com/user-attachments/assets/f6f29d46-8760-4d0b-be2b-371625ed9837)

### 1. Mapper Phase in HAdoop Streaming:
----------------------------------
	-In the MAp phase of Hadoop Streaming the mapper script receives input data line by line via stdin.
	-It processes the data (typically breaking it into key-value pair) and results the output via stdout.
	
	eg:
	
	import system
	
	for line in sys.stdin:
		line = line.strip()
		words = line.split()
		for word in words:
			print(f'{word}\t1')
	


### 2. Reducer  Phase in HAdoop Streaming:
---------------------------------------
	-In Reduce phase, the reducer script reads the shuffled output from the mapper via stdin.
	-In each key, it aggregates or processes the associated values, then emits the final result.
	
	Eg:
	
	import sys
	curren_word = None
	current_count = 0;
	word = None
	
	for line in sys.stdin:
		line = line.strip()
		words, count  = line.split('\t', 1)
		
		try:
			count = int(count)
		except ValueError:
			continue
			
			
