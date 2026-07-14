**Network Access Control List** (NACL's)
- Virtual firewall at the subnet level
- auto get nacl with a vpc which allows all outbound and inbound traffic
- inbount and outbound rules
- rule # determines the order of eval from lowest to highest
- highest rule #32766 rec. to work in increments of 10/100
- you could block a single ip

Use Case
- determine that an IP is malicious we can add a rule to nacl and deny
- we never need to ssh we can further harden by denying port 22
