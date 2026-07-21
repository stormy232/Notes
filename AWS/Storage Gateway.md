connects on premise software apps with cloud based storage


scalable
supports vmware esxi and hyper-v
you can use AWS console to create your gateway

3 Types of Gateways
- File Gateway (NFS)
- Volume Gateway (iSCSI)
- Tape Gateway

File Gateway
- NFS or SMB 
- metadata stored within S3 metadata of obs associated with file
- can be managed as native s3 obj
- bucket policies, versioning, lifecycle management basically all s3 features apply

Volume Gateway
- use iSCSI 
- data written to volumes aync backed as point in time snapshots and stored as AWS EBS snapshots
- snapshots incremental backup only changed block
- all is also compressed
- Stored Volumes
	- Primary data stored locally
	- while backing up data to AWS
	- written to on-premise hardware
	- ebs snapshots backed to s3
	- 1GB-16TB
- Cached Volumes
	- AWS S3 as primary data storage
	- while cache can be retained locally
	- up to 32TB attach iSCSI
	- gateway stores data to s3 and recently read data in on premise storage
	- 1GB - 32GB (cached)
- Tape Gateway
	- Store data on virt tape cartridges
	- pre config with media changer and tape drives available iSCSI
	- add tape cartrid as you need
	- NetBackup, Backup Exec and Veeam