{
    "title": "Launch RHEL instances",
    "linkTitle": "Launch RHEL instances",
    "weight": "90"
}For the purpose of our setup, we need seven RHEL instances in total:

-   Two SecureTransport Servers – one in each Private Subnet
-   Two SecureTransport Edges – one in each Public Subnet
-   Two GlusterFS Servers – one in each Private Subnet  
    **Note:** This is in case you use GlusterFS for a shared file system instead of EFS service.  
-   One instance to administer and access the above instances – Administration Host in one of the public subnets

To launch a RHEL instance, follow these steps:

1.  Navigate to AWS console -> Services.

2.  Go to the Compute section and select **EC2**.

3.  Select Instances and then click **Launch Instance**.

4.  Choose an Amazon Machine Image and select Red Hat Enterprise Linux (HVM), SSD Volume Type - ami-bb9a6bc2 (64 bit) .

5.  Choose an Instance Type according to the *Minimum UNIX hardware requirements* in the {{< SecureTransport/componentshortname >}} {{< SecureTransport/componentversion >}} *Installation Guide*. We recommend a minimum setup of mx3.large with 4 cores & 15GB RAM & 2x40GB SSD.  
    Learn more about [Instance Types](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html) in the AWS documentation.

6.  Configure Instance Details by providing the following options:  
     

    -   **Number of instances:** 1  
        Launch the instances one by one because of the different settings.
    -   **Network:** select your VPC from the drop-down list.
    -   **Subnet:** select a subnet from the drop-down list.
    -   **Auto-assign Public IP:** Requests a public IP address from Amazon's public IP address pool to make your instance accessible from the Internet.
    -   For instances in the public subnets, select **Enabled**.
    -   **IAM role:** An IAM role automatically deploys AWS credentials to resources that assume it. Select the instance profile that contains the required IAM role.  
        Learn more about [IAM Roles](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/iam-roles-for-amazon-ec2.html) in the AWS documentation.  
    -   **Shutdown behavior:** Specify the instance behavior when an OS-level shutdown is performed. Instances can be either terminated or stopped.
    -   **Enable termination protection:** You can protect instances from being accidentally terminated.
    -   **Monitoring:** Enables you to monitor, collect, and analyze metrics about your instances through Amazon CloudWatch.
    -   **EBS-optimized instance:** Enables additional, dedicated throughput between Amazon EC2 and Amazon EBS, and therefore improved performance for your Amazon EBS volumes.
    -   **Tenancy:** You can choose to run your instances on physical servers fully dedicated for your use.

    <img src="/Images/SecureTransport/rhel-security.PNG" class="maxWidth" />

    -   **Network Interfaces:** You can attach one more network interface to your instance during launch.
    -   **Advanced Details:** You can specify user data to configure an instance or run a configuration script during launch.

    <img src="/Images/SecureTransport/rhel-netw-intrf.PNG" class="maxWidth" />  
    Learn more about [Security Groups](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-network-security.html?icmpid=docs_ec2_console#vpc-security-groups) in the AWS documentation.

7.  Add Storage – specify storage device settings.  
    <img src="/Images/SecureTransport/rhel-storage.PNG" class="maxWidth" />

8.  Add Tags – a tag consists of a case-sensitive key-value pair.  
    For example, you could define a tag with key = Name and value = SecureTransport-Server1.  
    <img src="/Images/SecureTransport/rhel-tags.PNG" class="maxWidth" />

9.  Configure Security Group – create new or choose an existing one.  
    A security group is a set of firewall rules that control the traffic for your instance. On this page, you can add rules to allow specific traffic to reach your instance.  
    **Note:** SecureTransport Servers, SecureTransport Edges, GlusterFS Servers, EFS Mount Targets and Administration Host have specific security groups.  
    Learn more about [Security Groups.](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-network-security.html?icmpid=docs_ec2_console#vpc-security-groups)  

10. Review and Launch your instance.

11. Select an existing key pair or create a new one.  
    -   Create a new key pair – type a key pair name and then click **Download Key Pair**.
    -   Choose an existing key pair – select a key pair from the drop-down menu and select the **I acknowledge...** check-box.

    After download, you will be able to click **Launch Instances**.  
    <img src="/Images/SecureTransport/rhel-keypair.PNG" class="maxWidth" />

  
