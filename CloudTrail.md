Logs API calls between AWS services 

monitor API calls and Actions

Easily Identify which users and accounts made call to AWS
- Where IP addr
- When EventTime
- Who User, UserAgent
- What Region,Resource,Action

Event History:
- logging by default in last 90 days via Event history
- if more than 90 days you need to create a trail
- trails output to s3 and have no gui use athena

Trail Options:
- can log all regions
- can across all accounts in an org
- you can encrypt logs 
- integrity of logs can be checked with log file validation

Management Events:
- Configuring security
	- IAM roles
- Registering Devices
- Config rules for routing
- setting up logging

Data Events:
- S3, Lambda, DB's, etc..
- very high volume, more detailed events