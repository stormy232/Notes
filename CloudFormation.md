IAC
- Infrastructure as code
- data machine provisioned through yaml,jsons,etc

Use Case:
- people pay for minecraft server they choose where and what size of server they want to run we can send the inputs and use lambda function to create a new cloudformation stack, we can send the ip addr of new instance to the server

CloudFormation Templates
- JSON/YAML
	- Sections
		- MetaData
		- Description
		- Params
		- Mappings (key value store lookup table)
		- Conditions: if else statemetns
		- Transform: macros
		- Resources: resource you want to create (this is req)
		- Outputs: Vals returned ex: ip-addr of new server created
