Amazon Machine Images provide info to launch an instance
- you can turn ec2 instance into amis to create copies of a server

AMI holds:
- template of root volume for instance (Snapshot)
- Launch perms that control which AWS accounts can use AMI to launch instances
- block dev mapping specifies volumes to attact to instance when launched
- region specific

Use Case:
- help you keep incremental changes to OS, app code and sys packages
- Generally used with Systems Manager Automation
- used with LaunchConfigurations when you want to roll out updates to mult instances

AMI Marketplace
- lets you purchase subscription to vendor maintianed AMIs
- security harden AMIs are very popular

Creating an AMI
- yo can create an AMI from existing EC2 instance that is stopped

AMI ID vary by region