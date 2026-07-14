solution to create secure apis

you can throttle requests
restful api
maintain mult versions of api

Resources:
- When you create api you need multiple resources
- resources can have child resources

Methods:
- methods need to be defined on resources
- you can def mult methods on a resource

Methods -> Http Methods

Stages -> versions of api
Invoke URL -> each stage give an invoke url this is the endpoint you will hit

Deploy API
- everytime you make changes you need to deploy the api action, here you will choose the stage

Config:
- you need to choose an integration type
- most common is lambda

Caching:
- caches responses from endpoints for a specific ttl
- api gateway responds to reqs by looking from cache
- reduces # of calls
- improve latency

CORS
- allows restricted resources to be req from diff domain than inital resource
- always enforced by client

Same Origin Policy
- web browser permits scipts contained in a first web page to access data in a second
- same origin policies used to prevent XSS
- only works if both req from same domain