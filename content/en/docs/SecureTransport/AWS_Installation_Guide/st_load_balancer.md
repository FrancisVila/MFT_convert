{
    "title": "Set up Classic Load Balancer",
    "linkTitle": "Set up Classic Load Balancer",
    "weight": "120"
}Amazon Web Services Cloud provides three types of Load Balancers – Application, Network and Classic. The deployment of SecureTransport on Amazon VPC has been verified with the Classic Load Balancer. You can load balance HTTP/HTTPS applications and use Layer 7-specific features, such as X-Forwarded and sticky sessions. You can also use strict Layer 4 load balancing for applications that rely purely on the TCP protocol. The load balancer takes requests from clients and distributes them across the EC2 instances that are registered with the load balancer.

When you create a load balancer in a VPC, you can either make it an internal load balancer, or an Internet-facing load balancer. You create an Internet-facing load balancer in a public subnet.

When you create your load balancer, you must configure listeners, health checks, and register back-end instances. You configure a listener by specifying a protocol and a port for front-end (client to load balancer) connections, and a protocol and a port for back-end (load balancer to back-end instances) connections. You can configure multiple listeners for your load balancer.

If you specify that the HTTPS listener sends requests to the instances on port 80, the load balancer terminates the requests and communication from the load balancer to the instances is not encrypted. If the HTTPS listener sends requests to the instances on port 443, communication from the load balancer to the instances is encrypted.

Follow these steps to create Classic Load Balancer redirecting requests to SecureTransport instances in Amazon VPC:  

1.  Log in to AWS.
2.  Navigate to Services->EC2->Load Balancing->Load Balancers.
3.  Click the **Create Load Balancer** located in the top of the page.
4.  Choose **Classic Load Balancer**.
5.  Add **Basic Configuration**:
    1.  Enter Load Balancer name.
    2.  Create the LB inside and choose your VPC.
    3.  Leave the "Create an internal load balancer" options unselected.
    4.  In the "Listener Configuration" add listeners by specifying a protocol and a port for front-end (client to load balancer) connections, and a protocol and a port for back-end (load balancer to back-end instances) connections.  
        Note that the listeners in the image are configured with default ports or ports specific for the test setup. Please change/add listeners according to your specific setup.  
        Check the FTP does not work through the firewall section in the SecureTransport Administrator's Guide if you want to configure FTP listeners.
    5.  Navigate to the "Select Subnets" section on the same page.
    6.  Choose your public subnets from both availability zones.
    7.  Choose "Assign Security Groups" and move to the next phase.  
          
6.  On the next step "Assign Security Groups"-> go to "Select an existing security group" and choose the security group you prepared previously for your load balancer, described in the [Security Groups](../st_create_secgroups/st_securitygroups) section of this guide.  
      
    <img src="/Images/SecureTransport/lb-security-group.PNG" class="maxWidth" />
7.  On the next stage **"Configure Security Settings"** choose certificate for the HTTPS listener - Choose a certificate from ACM (recommended)/Choose a certificate from IAM and leave default values for the rest of the security settings and proceed to the next stage (modify the security settings according to your needs).  
    <img src="/Images/SecureTransport/lb-security-settings.PNG" class="maxWidth" />  
8.  **Configure Health Check** on the next step - configure ping protocol and port and choose **Next: Add EC2 instances**.  
    Learn more about [HealthCheck](https://docs.aws.amazon.com/elasticloadbalancing/2012-06-01/APIReference/API_HealthCheck.html) in the AWS documentation.  
    <img src="/Images/SecureTransport/lb-health-check.PNG" class="maxWidth" />  
9.  **Add EC2 Instances**: choose your two SecureTransport Edge instances and choose **Next: Add Tags**.  
    <img src="/Images/SecureTransport/lb-ec2-instances.PNG" class="maxWidth" />  
10. On the next stage **Add Tags** add a tag for example with key **Name** and a value something unique and meaningful.  
    <img src="/Images/SecureTransport/lb-add-tag.PNG" class="maxWidth" />  
11. Review your load balancer settings and choose **Create**.  
    <img src="/Images/SecureTransport/lb-step7.png" class="maxWidth" />  
12. After successful creation of the load balancer you are redirected to a page confirming your load balancer creation status.  
13. Configure Stickiness. If you have HTTP/HTTPS listeners in your load balancer configuration you need to edit one more setting called Cookie Stickiness. Edit the setting after the load balancer is successfully created.  
    As per AWS Documentation:  
    By default, a Classic Load Balancer routes each request independently to the registered instance with the smallest load. However, you can use the *sticky session* feature (also known as *session affinity*), which enables the load balancer to bind a user's session to a specific instance. This ensures that all requests from the user during the session are sent to the same instance.  
    The key to managing sticky sessions is to determine how long your load balancer should consistently route the user's request to the same instance. If your application has its own session cookie, then you can configure Elastic Load Balancing so that the session cookie follows the duration specified by the application's session cookie. If your application does not have its own session cookie, then you can configure Elastic Load Balancing to create a session cookie by specifying your own stickiness duration.  
    Learn more about how to [Configure Sticky Sessions for Your Classic Load Balancer](http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-sticky-sessions.html) in the AWS documentation.  
      
    To Configure Stickiness, follow these steps:  
    1.  Log in to AWS.
    2.  Navigate to Services->EC2->Load Balancing->Load Balancers.
    3.  Choose your load balancer from the list.
    4.  In the Description section for your load balancer choose "Edit Stickiness" for HTTP and HTTPS Port Configuration.
    5.  In the Edit stickiness window displayed choose **"Enable load balancer generated cookie stickiness"** and enter expiration period in seconds.  
        (SecureTransport works with Load Balancer generated cookie stickiness).  
        <img src="/Images/SecureTransport/edit-stickiness.PNG" class="mediumWidth" />  

      
14. **Instance HealthCheck -** your instances should pass the health check you defined in order for your load balancer to become operational.  
    1.  Log in to AWS console.
    2.  Navigate to Services->EC2->Load Balancing->Load Balancers.
    3.  Choose your load balancer from the list.
    4.  In the **Instances** section for your load balancer check the Status of your instances.
    5.  During the health check execution their Status is "OutOfService".
    6.  If the check passes successfully the instances' Status changes to "InService".

Now, your load balancer is ready to fetch requests and distribute them among your SecureTransport Edge instances in the two availability zones in Amazon Web Services Cloud.  
If you would like to use a friendly DNS name to access your load balancer, instead of the default DNS name automatically assigned to your load balancer, you can create a custom domain name and associate it with the DNS name for your load balancer. Learn more in the [AWS documentation](https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/using-domain-names-with-elb.html?icmpid=docs_elb_console).
