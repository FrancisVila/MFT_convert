{
    "title": "Launch SecureTransport Edge instances",
    "linkTitle": "Launch SecureTransport Edge instances",
    "weight": "120"
}## Launch SecureTransport Edge instances

Follow the steps for launching RHEL Instance with the following specifics:

1.  Go to Instance Details -> Subnet.
2.  First Server – choose the public subnet from availability zone eu-west-1 b.
3.  Second Server – choose the public subnet from availability zone eu-west-1 c.
4.  Go to Configure Instance Details and select to enable Auto-assign Public IP (if you need your Edge servers to be directly accessible from the Internet).
5.  Add storage.
6.  Enter a value for storage size sufficient for your SecureTransport Edge needs.
7.  Add Tags.
8.  Specify unique names, so you can easily distinguish between instances.
9.  Specify the Security Groups.

Assign the instances to the previously created SecureTransport Edge Security Group as described in the [](../../st_create_secgroups)[Create Security Groups and Network Access Lists](../../st_create_secgroups) section.
