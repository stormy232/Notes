Route53 a DNS with more synergy with AWS services

Route53 - Use Case
- Record Sets can point to aws services
- API -> api gateway, static hosting -> cloudfront, domain to ec2, etc...

Record Sets:
- record sets allow us to point our naked domain and subdomains via Domain Records
- Alias (AWS special) -> allows you to more easily directly select AWS services can detect changes in AWS resource changes (use whenever you can)

Traffic Flow
- visual editor lets you create routing configs for resources $50 per policy record/month charged after you save

Routing Policies:
- Simple Routing 
	- most basic have 1 record and provide multiple ip addrs
	- when multiple values are specifed for a record Route53 will return all vals back to the user in a random order
- Weighted Routing Policies
	- split up traffic based on diff weights
	- make two record sets one stable and one experiment (set weight to 85% and 15%)
	- 85% traffic goes to stable 15% to exp.
- Latency Based Routing Policies
	- direct traffic based on lowest net latency possible for end-user based on region
- Failover Routing Policies
	- active/passive setup
	- Route 53 monitors health-checks of primary site and if its failed traffic routed to secondary location
- Geolocation Routing Policies
	- direct traffic based on the geographic location of where the request originated from
- GeoProximity Routing Policies
	- You have to use traffic flow (does not work with routing sets)
	- You are choosing a region (draws custom boundries if you want)
	- Boundaries that set bias 
- Multi-Value Answer Policy
	- Same as simple but checks for health

Route53 - Health Checks
- Checks health every 30s by default can be reduced to 10s
- health check can monitor other health checks -> create chain of reactions
- CloudWatch alarm can alert you
- up to 50 health checks -> 0.50 per health check/month

Resolver
- route DNS queries between VPC and your network
- Hybrid Envs