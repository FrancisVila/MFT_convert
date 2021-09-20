{
    "title": "Configure MS SQL Server",
    "linkTitle": "Configure MS SQL Server",
    "weight": "110"
}Your SQL Cluster configuration includes installation of each SQL instance on Windows VMs (each in its respective Availability zone). You then must configure them in a WSFC cluster and then set them up in an Always On availability group.

You will need the following components:

1.  AD server containing domain accounts for SQL Server services account and SQL Server Agent service account
2.  File share witness server
3.  Azure Load Balancer
4.  Two Windows Datacenter VMs (each placed in a different Availability Zone).  
    
    1.  Follow the steps for launching a VM instance with the following specifics:
        1.  Select a supported Windows Server for image.
        2.  Select an appropriate size - for example SecureTransport with D4\_V3 Standard size for VM instance.
        3.  Configure Instance **Settings**-> **Subnet**.
        4.  Choose the respective private subnet in your VNet.
        5.  Configure Instance **Settings** -> **Public IP address:**
        6.  Configure Instance **Settings** -> **Network security group**.
        7.  Assign the Windows VM to the previously created Database Network security group as described in Network *Security Groups*
5.  Install SQL Server on each of the two instances.
6.  Set up Windows failover cluster
7.  Set up Always On availability group.
