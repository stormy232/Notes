IAM allows managemnt of access of users and resources

IAM Users - end users who log in
IAM Groups - groups users so they share perm levels
IAM Roles - Associate perms to a role and assign this to a user or group

IAM Policies - JSON doc which grnts specific perms to access services. Policies are attached to IAM Identites (the three above)

User can belong to a group which has a role with IAM policies
You can assign direct to a user or a policy direct to a user as well (Inline Policy)
- you would only use Inline policy for a one off thing

Roles can have mult policies 
Roles can be attached to AWS resources, we saw this in EC2 demo

Types of Policies:
- Managed Policies
	- policy managed by AWS you can't edit (its labeled as such)
- Custmer Managed Policies
	- policy created by customer which can be editied
- Inline Policy
	- Directly attached to user, not managed so stuck to one resource

IAM Policy Syntax:

Version - policy lang version

2012-10-17 - latest version
Statement container for policy element, you can have multiple or group everything into an array by 
"Statement": [{}]

SID (optional): way to label statements
Effect: Allow or Deny
Principal: who do you want to allow or deny access
Action: list of actions that the policy allows/deny
Resource: resources action applies to
Condition (optional): In what circumstance should the action apply

Password Policy:
- you can set a Pass Policy to set min reqs of password and rotate passwords

Progamatic Access Keys:
- Access Keys allow users to interact with AWS service via CLI/SDK
- Users can only have up tot two access keys in account

MFA:
- can be turned on per user
- admin can't force mfa the user has to turn it on
- certain policies can be restricted to those using mfa

