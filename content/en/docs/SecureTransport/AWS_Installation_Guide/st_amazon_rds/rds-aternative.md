{
    "title": "Alternative to RDS service",
    "linkTitle": "Alternative to RDS service",
    "weight": "120"
}If you would prefer not to use the AWS RDS Service, you can easily replace it with two RHEL Instances with an Oracle / PostgreSQL database set up on each.

The Oracle RHEL / PostgreSQL instances should match the same rules:

1.  One instance in each availability zone.
2.  Each instance in a separate private subnet.
3.  Both instances in one Database Security Group as defined in *Security Groups and Network Access Lists*.
