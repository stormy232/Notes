its a server bro

resizable compute capacity, takes minutes to launch new instances

Instance Types:
 - General Purpose -> good for web servers and code reps
	 - T3
	 - T2
- Compute Optimized -> Compoute bound appselling gaming servers
	- scientific mod

- Memory Optimized
	- fast perf for workloads that process large data sets in memory
	- memory cache/db

- Accelerated Optimized
	- hardware accelertors
	- ML, comp finance, seismic analysis

- Storage Optimzied
	- high, sequential read and write access to large data sets on local storage
	- NOSQL, transact db

Instacne Sizes:
- generally double in steps small to med

Instance Profile
- Instance Profile holds a reference to a IAM role to. (container for one)
- always avoid embedding AWS creds when possible

Placement groups:
- let you chose logical placement of instance to optimize, they are free
- Cluster
	- packs close together in an az
	- low latency net perf
	- well suited for High-perf computing apps
	- Clusers not mult az
- Partition
	- Spreads instances across logical partitions
	- well suited for distributed workload (hadoop)
- Spread
	- instance is placed on a diff rack
	- critical instances seperate from another 
	- max 7, can be multi az

UserData - script that will auto run when launching an EC2 instance

MetaData - additional info about EC2 instance you can get if your run curl ip/latest/meta-data you will get metadata

Pricing:
- On-Demand
	- charged by hour or by minute
- Reserved Instances
	- steady state, predictable usage or req reserved capcity
	- reduced pricing based on tem x class offering x payment option
	- standard can't change RI attribute (size)
	- convertible 54% (size can only go up)
	- Scheduled - reserve instances for specific time periods
	- Terms: 1-3 year
	- Payment Options: No Upfront end of month, All upfront, Partial Upfront

- Spot Instances
	-  90% discount
	-  Instances can be terminated by AWS at anytime
	- if terminated you don't get charged for partial hour 
	- if you terminate you will be charged
	- apps at very low compute costs
- Dedicated Host Instances
	- most expensive
	-  basically you don't want to be using hardware with other aws users
