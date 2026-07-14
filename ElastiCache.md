caching services

supports 2 open-source:
- Memcached
- Redis

Memcached -> preferred for caching HTML fragments 
Redis -> can support more operations but may arguably be not as fast as Memcached

High Availability arch (HA)

when service unavailable:
- AZ becomes unavailable
- region becomes unavailable
- web-app unresponsive
- instancebecomes unavailable
- unresponsive due to distance in geo location

Solution
- run instances in Multi-AZ, elastic load balancer
- run instances in another region route through route53
- auto scaling groups to increase instances to meet demand of traffic
- auto scalling groupts to ensure min instances and ELB route traffic to healthy instances
- CloudFront to cache content. run instances in nearby regions and route via geolocation policy route53

Scale Up -> vert
Scale Out -> horizontal