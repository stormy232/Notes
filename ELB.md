Distributes traffic to multiple targets

ELB is the AWS solution - 3 solutions
- Application Load Balancer
- Network Load Balancer
- Classic Load Balancer

ELB Rules of Traffic
- Listeners
	- listen for incoming traffic at a specific port
- Rules
	- what to do with traffic
- Target Groups
	- all ec2 instances you want to route traffic to

Application Load Balancer/Network Load Balncer traffic sent to listener when port matches it checks the rules 

Ex: Redirect to Port 443 -> Redirect to Target 1 -> Target 1 (is the target group with EC2 instances)

Rules are only for ALB's

Classic Load Balancer
- no target groups but ec2 instances that may be attached to individual listeners
- CLB will direct to a listener which will direct to a target

ALB
- designed to balance http/Https taffic
- operate at layer 7 of OSI model (application)
- Request Routing allows you to add routing rules to listeners based on http protocol
- good for web apps

NLB
- designed to balance TCP/UDP
- Layer 4 (transport)
- millions of requests per second
- when net performance is most critical

CLB
- Layer 7 specific features sticky situation
- also layer 4
- cross-zone load balancing
- 504 error if underlying app not responding (web-server/db-level)
- legacy not recommended

Sticky Sessions
- bind a user's session to a specific EC2 instance
- ensures all req from session sent to same instance
- typically used with classic load balance
- doesn't work for NLB
- ALB has to be set on target group

X-Forwarded-For(XFF) header
- you need IPV4 addr, you get through X-Forwarded-For header

Health Checks
- ping server at specfic endpoint expecting a specific response back for health check
- either InService or OutofService
- does not terminate unhealthy instance

Cross-Zone Load Balancing 
- only classic/nlb
- req are distributed evenly across all instances in enabled availability zones
- disabled req are distrib evenly acrossinstances in only the respective az

Request Routing 
- specific to ALB
- rules to req to froward/redirect traffic
- w