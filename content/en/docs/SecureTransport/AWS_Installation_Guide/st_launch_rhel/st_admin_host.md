{
    "title": "Launch an instance for the Administration Host",
    "linkTitle": "Launch an instance for the Administration Host",
    "weight": "110"
}The Administration Host is an instance of a virtual machine you launch in one of the public subnets in your VPC. You can use this machine to perform the following activities:

-   Perform <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installations on launched instances.
-   Add configurations on your launched instances.
-   Perform maintenance and administration tasks on your instances.

Follow the steps for launching RHEL Instance with the following specifics:

1.  Choose an Amazon Machine Image and select the operating system that will be most suitable for your administering needs.
2.  Choose an Instance Type that will be most suitable for your administering needs.
3.  Go to Instance Details -> Subnet.
4.  Choose one of the public subnets from one of the availability zones.
5.  Go to Configure Instance Details and select to enable Auto-assign Public IP (depending on the connectivity you would like to have to this host).
6.  Add storage – enter a value for storage size sufficient for your needs.
7.  Add Tags – specify unique names, so you can easily distinguish between instances.
8.  Security Groups – assign the instance to the previously created Administration Host Security Group as described in the [](../../st_create_secgroups)<a href="../../st_create_secgroups" class="MCXref xref">Create Security Groups and Network Access Lists</a> section.
