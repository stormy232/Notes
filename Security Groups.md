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
