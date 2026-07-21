contains a collection of EC2 instances treated as group for purpose of auto scaling and management

Min: # EC2 instances
Max
Desired Capcity: Ideally

EC2 

Health Check Replacements:
- EC2 Status Checks, if any 2 checks fail autoscaling group will kill ec2 instance
- ELB Health check by pinging an http endpoint on server expecting a response, if ELB determines an instance is unhealthy it will kill instance

Scaling Policies:
- Target Tracking Scaling Policy
	- Maintains a specific metric at a target val (for instance CPU utilization %, Network In/Out)
- Simple Scaling Policy
	- Scales when an alarm is breached (not recommended legacy)
- Scaling policies with steps
	- Scales when an alram is breached, can escalate based on alarm val changing
- Elastic Load Balancers (ELB
	- Classic Load Balancers are associated directly to ASG
	- New way: Application and Net Load Balancers are associated indirectly via Target Groups

Use Case:
- Burst of traffic hits our domain
- Route 53 points traffic to load balancer
- load balancer passes traffic to target groups
- target group associated with our ASG sends traffic to instances reg with ASG
- ASG scaling policies determine scale

Launch Configuration:
- launch config is an instance config template 
- same process as launching an EC2 instance except you are just saving that config to launch an instance for later
- cannot be edited, you either make a new one or clone one
- Launch Templates are Launch configurations with versioning