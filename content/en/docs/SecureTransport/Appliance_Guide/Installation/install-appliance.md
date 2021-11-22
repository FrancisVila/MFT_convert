{
    "title": "Install the appliance",
    "linkTitle": "Install the virtual appliance",
    "weight": "70"
}{{< SecureTransport/componentshortname  >}} {{< SecureTransport/componentversion  >}} is available as a 64-bit virtual appliance running SLES in the following format:

-   **Appliance iso image file** – *SecureTransport\_5.5\_Install\_ap-x86-64\_&lt;BuildNumber>.zip*

Before installing, review and understand the following information:

-   A new installation of SecureTransport 5.5 is also supported on hardware appliances.
-   When you start an appliance or virtual appliance, press **Alt+F2** to switch to tty2 and access the Linux login.
-   Non-root installation is not supported on appliances.
-   Memory and CPU requirements: minimum 40 GB hard drive space, 8 GB RAM, 4 CPUs.

To install the operating system, you need to upload the ISO image to the hypervisor storage and attach it to a blank virtual machine. Note that the installer wipes out the contents of the hard drive of the machine without prompting.

To make a virtual machine available for use, refer to the Amazon Elastic Compute Cloud (EC2) or VMware documentation.

> **Note:**
>
> To connect to SLES on your SecureTransport appliance using SSH, use port 10022. (After you install SecureTransport, you will use port 22 to connect to SecureTransport using SFTP or SCP). You can change the SLES SSH port number after installation by editing /etc/ssh/sshd\_config.

Once you have installed the appliance operating system, you can install SecureTransport in Standalone mode, Standard Cluster, or Enterprise Cluster. For more information, see <a href="../install-st-on-appliance" class="MCXref xref">Install SecureTransport on the appliance</a>.

-   <a href="../../app_network_config" class="MCXref xref">Configure network settings</a> - Provides how to instructions for setting appliance network configuration parameters.
-   <a href="../../app_network_config#Configur3" class="MCXref xref">Configure the DNS server address, host name, and domain name</a> - Provides how to instructions for configuring the DNS server address and host name.
