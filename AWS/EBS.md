IOPS - Input/Output per second speed at which non-contiguous read and writes can be perf on a storage medium

Throughput data transfer rate to storage

bandwidth meaurement of total posible speed of data movement along network

EBS 
- highly available for persistent block storage volumes to an EC2 instance. Volumes automatically replicated within AZ to protect compo fail


Volume Types:
- General Purpose (SSD)
	- general usage
	- 1GIB - 16 TiB
- Provisioned IOPS
	- fast input/output
	- 4GB-16TiB
- Throughput Optimized HDD
	- magnetic drive optimized for quick throughput'
	- 500GIB-15TiB
- Cold HDD
	- low cost infrequently access
	- 500GiB-15TiB
- EBS Magnetic 
	- previous gen HDD
	- 500GiB-15TiB   

Magnetic Tape
- Durable for decades
- cheap to produce

Moving Volumes
- From one AZ to another
	- take snapshot creae an AMI from snapshot
	- launch EC2 instance in desired AZ
- From Region to another
	- same as above but copy AMI to another region

Encrypted ROot Volume
- you can encrypt on creation
- Otherwise snapshot 
- copy snapshot
- encrypt copied snapshot
- create ami of that snapshot launch ec2 instance from ami


Following two are for being backups of volumes
EBS Volumes
- durable block-level storage device that you can attach to a single EC2 instance
- created from EBS snapshot
- persistent data

Instance Store Volumes
- temporary storage type located on disks physically attached to host machine
- created from template stored in s3
- app cache logs/other data