DNS - translates domain names to IP addrs
IP addrs - uniquely idenitfy computers on a network

IPV4  - 32bits (2^32)
IPV6 - 128bits (2^128)

Domain Registars auths who have ability to assign domain names under top-levels domains
Domains get registered through InterNIC service enforcing uniqueness of domain names on internet

WhoIS database 

Top-Level Domains what comes after the . (.com)
second word within a domain name is second-leve .co for instance

Start of Authority (SOA):
- SOA way for Domain Admins to provide info about domain
- required for all domains

Structure:
- Name
- IN (zone)
- SOA
- NNAME
- RNAME
- SERIAL
- REFRESH
- REtry
- ttl

Zone file can only have one SOA record

DNS A RECORDS:
- allows you to convert name of a domain directly to an IP addr

CNAME:
- resolve one domain name to another rather than an IP addr
- adv unlikely to change whereas IP addrs can change dynamic

NS records:
- used by top-level domain servers to direct traffic to auth DNS records

TTL
- length of time that a DNS record is cached on servers or users local machine
- TTL measured in seconds under IPV4