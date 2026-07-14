Managed Relational database service

6 relational database options currently available on AWS

Aurora
MySQL
MariaDB
PostgreSQL
Oracle
SQL Server

encryption at-rest for all RDS engines works you may not be able to turn on for older

encryption handled by AWS KMS

2 backup solutions

Automated Backups
- transaction logs
- s3 data
- no additional charge for backups
- def backup window
- io may be suspended during backup

Manual Snapshots
- Taken manually by user 
- Backups persist even if you delete the original RDS instance

Restoring Backup
- backup data is never restored over existing instance 
- new instance is created from restored database
- these will have a new dns endpoint

Multi-AZ
- makes copy of db in another AZ
- AWS auto syncs

Automatic Failover protection 
- if one AZ goes down failover will occur and the standby slave will be promoted to master

Read Replicas
- multiple copies of db
- only allows reads
- async replication between primary rds instance and replicas 
- you can have 5 replicas 
- each has its own dns endpoint

Redshift
- Data Warehouse
	- store large quantities of historiacal data enable fast complex queries across all data
- Columnar Storage
	- is a factor in optimizing analytic query perfo drastically reduces disk load
	- stores data as columns instead of rows
	- Single Node size of 160Gb
	- MultiNode
		- Leader Node - manage client connections
		- Compute Node - stores data (up to 128)
	- two types of nodes
		- dense compute
		- dense storage
		- distribs data and query loads across nodes
		- easily add new nodes 
		- backup enabled by default 1 day retention
		- up to 35 days
		- maintains 3 copies
			- og
			- replica on compute
			- backup in s3
		- billed 1 unit per node, per hour
		- not charged for leader node hours
		- single-az