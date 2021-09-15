{
    "title": "Launch SecureTransport Server Instances",
    "linkTitle": "Launch SecureTransport Server Instances",
    "weight": "130"
}## Launch SecureTransport Server Instances

Follow the steps for launching RHEL Instance with the following specifics:

1.  Configure Instance Details -> Subnet.
2.  First Server - choose the private subnet from availability zone eu-west-1 b.  
    Second Server - choose the private subnet from availability zone eu-west-1 c.
3.  Configure Instance Details - &gt; Auto-assign Public IP: Disabled.
4.  Add storage.
5.  The default value of 10GB would be insufficient, so you can increase it to 20GB or more.
6.  Add Tags.
7.  Specify unique names, so you can easily distinguish between instances.
8.  Specify the Security Groups.
9.  Assign all SecureTransport Servers to the previously created Security Group as described in the [](../../st_create_secgroups)[Create Security Groups and Network Access Lists](../../st_create_secgroups) section.
