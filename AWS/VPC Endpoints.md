Provision a logically isolated isolation of aws cloud in virt network

CIDR -> basically classful addresses the subnet works in octets, wheras cidr can be any number of bits /2, /10, /26 up to 32 obv cause IPV4



complete control over your virtual networking environment

![[Pasted image 20260708135232.png]]

**Core Components**
- Internet Gateway
- Virtual Private Gateway
- Routing Tables
- Network Access Control Lists
- Security Groups
- Public Subnets
- Private Subnets
- Nat Gateway
- Customer Gateway
- VPC Endpoints
- VPC Peering

Key Features:
- Region Specific
- 5 VPC per region
- 200 subnets per VPC
- Ipv4 Cidr Block in addition to IPv6
- Nat Gateway, VPC Endpoints, VPN gateway, Customer gateway cost you money everything no cost
- DNS hostnames: (Not turned on by default), its for ec2 instances

Default VPC in every region so you can immediately deploy instances
- Create a VPC with size/16 Ipv4 CIDR block 
- Create a size /20 default subnet
- Create and Internet Gateway
- Create a default security group
- Create a default nacl
- associate the default DHCP settings with aws account

0.0.0.0/0 -> is known as default
it reprs all possible ip addr

we use it in our route table for IGW
in security groups inbound traffic allowing anyone on internet in

VPC peering connect one vpc to another over direct network using private Ip addr

Instance on peered VPC behave like same network 
can go accross aws accounts and regions
No transitive peering -> VPC C wants to talk to VPC B traffic doesn't flow through VPC A they need to have thier own direct VPC peering
No overlapping CIDR blocks

**Route Tables**
- Where network traffic is directed
- Subnet only associated with one route table at a time

**Internet Gatway** (IGW):
- provide a target in VPC route table internet routable 
- perform netwrok addr translation for instances that have been assigned public Ipv4 addresses

 to route to internet add 0.0.0.0/0 to the routing table towards wtv resource  you want available

**Bastion/Jumpbox**
- Bastions are EC2 instances which are security hardened, designed to help you gain access to your EC2 instances via SSH or RCP, that are in a private subnet

- EC2 in private subnet bastion connected to ec2 which itself is in a public subnet that outside can connect to
- Nat gatway is a type of bastion (not secure to use it in the same way)
- System Manager's Sessions Manager replaces need for bastions

**Direct Connect**
- Aws direct connect is solution for estab. dedicated net connection from on-premise to AWS
- Very fast Network
- Reduces network cost and throughpout more consistent as well

**VPC Endpoints**
- VPC Endpoints allow you to privately connect your VPC to other AWS services and VPC endpoints
- Eliminates need for internet gatway, Nat, VPN, AWS Direct Connect
- Instances in VPC don't need public IP addr to communicate with service resources
- Traffic doesn't leave AWS network
- Horizontally scaled, highly available
- secure communication between instances and services without adding availability risks or bandwidth constrainsts
-
- Interface Endpoints
	- Elastic Network Interfaces with a private Ip addr
	- serve as an entry point for traffic going to a supported service
	- Costs ~$7.5/mo, 0.01/h, 0.01/gb
- Gateway Endpoint
	- free
	- target for specific route in route table 
	- only support dynamodb and S3
	- target for a specific route in your route table

**VPC Flow Logs**
- capture IP traffic info
Can be created for:
- VPC
- Subnets
- Network Interface

stores the source Ipv4/Ipv6 addr and dstaddr

**Network Access Control List** (NACL's)
- Virtual firewall at the subnet level
- auto get nacl with a vpc which allows all outbound and inbound traffic
- inbount and outbound rules
- rule # determines the order of eval from lowest to highest
- highest rule #32766 rec. to work in increments of 10/100
- you could block a single ip

Use Case
- determine that an IP is malicious we can add a rule to nacl and deny
- we never need to ssh we can further harden by denying port 22

**Security Groups**
- virt firewall at instance level
- sec groups associated with EC2 instance
- each sec group contain a set or inbound and outbound rules
- traffic blocked by default unless a rule allows it
- mult instances across mult subnets can belong to a sec groups

Use Case:
- we have a web app running on a ec2 subnet and a private subnet with rbds port and we have sec group on rdbs with the specific ip and port
- you can specify on sec group
- ec2 instance can be in the same sec group, instance can belong to mult sec groups, rules are permissive (if one allow and one deny, you will be allowed)

Limits:
- 10,000 sec groups in region (def. 2500)
- 60 inbound and 60 outbound
- 16 sec groups (def. 5)

**NAT**
- remapping one IP addr space one another 
- private network gets mapped to a public ip addr
- if you have two networks with conflicting net addrs use a nat to make them agreeable
- have to be in public subnet

**NAT Instances (Legacy)**
- Individual EC2 instances
- Community AMIs exist to launch NAT instances

**NAT Gateways**
- managed service which launches a redundant instance within the selected AZ
