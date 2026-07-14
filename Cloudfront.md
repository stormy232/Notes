CDN
- deliver webpages based on geo location
- req served from nearest edge location

Distirbution
- collection of edge locations
- specify the origin s3,ec2,elb,route 53
- replicates copies based on price class
- 2 types of distribs
	- web
	- rtmp (streaming media)
- Redirections (behaviours)
- Invalidations (cache invalidations)
- Error pages
- Restrictions (Geo restrictions)

Lambda Edge
- lambda function to override behaviour of req and response
- 4 available
	- Viewer req
		- req from viewer
	- Origin req
		- forwards req to origin
	- Origin res
		- res from origin
	- Viewer res
		- response to viewer

- Protection
	- Original Identity Access (OAI)
		- virtual user identity that will be used to give cloudfront distribs perms to fetch private objs
	- signed urls
		- url with temp access to cached objs
	- signed cookies
		- cookie passed along req to cloudfront
		- cookie can prov access to mult restricted files