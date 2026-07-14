CloudWatch Logs
- Log Group -> collection of logs
	- Log in a log group is a log stream
- stored indefinitely and never expire

 CloudWatch Metrics:
 - predefined metrics
 - Ec2 Per-Instance Metrics

CloudWatch Events
- trigger events based on a condition in logs
- event source -> targets

Custom Metrics:
- aws cli and sdk you can create and publish your own custom metrics

HighResolution metrics
- lets you track under 1 minute down to 1 second

Alarms:
- triggers notification based on a breach on a metric
- example: billing alarm

create dashboards from metrics

ec2:
  basic monitoring - 5 min interval
  detailed monitoring - 1 min interval

CloudWatch Agent script that can be installed via systems manager run command onto ec2 instance (preinstalled on Amazon Linux)

Require Agent:
Memory Utilization
Disk Space uilization
