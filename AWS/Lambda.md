run code without provisioning or managing servers
you pay only for compute time you consume

Lambda is cheap, serverless and scales automatically

Natively supports 7 runtime langs:
 all the gc langs you can think of basically

Ex:
- Processing Thumbnails
	- web-service allows users to upload their profile photo 
	- they are storeAd in s3 bucket event trigger invokes lambda which will process the profile photo into a thumbnail and store it back into bucjket

Contact Email:
- API Gateway Endpoint -> Process (via lambda) -> record in db and send email

Pricing
- 1 million requests per month are free 
- than 0.20 per 1 million req
- 400,000 GB seconds free per month 
- after 0.0000166667


128MB x 30M exec X 200ms = $5.83

Default 
- 1000 Lambdas running concurrently
- /tmp contain up to 500MB
- Lambda by default run in no vpc -> you can set to vpc but it loses internet access
- timeout max of 15 mins
- mem can be beween 128MB to 3008MB in increments of 64MB

Cold Starts:
- delay within when function initally run called a cold start
- if you invoke the function again recently thatn this is a warm server (server doesn't need to startup)

- cold starts can cause delays in user exp.
- pre warning keeps server contin running or give lambda more resp.