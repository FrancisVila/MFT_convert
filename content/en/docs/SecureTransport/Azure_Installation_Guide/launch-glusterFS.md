{
    "title": "Launch GlusterFS instances",
    "linkTitle": "Launch GlusterFS instances",
    "weight": "100"
}Follow the steps for launching RHEL Instances with the following specifics:

1.  Configure Instance **Settings-> High availability**.
2.  Select the respective Availability Zone for each GlusterFS instance.
3.  Configure Instance **Settings-> Storage**.
4.  Select *Yes* for **Use managed disks**.
5.  Configure Instance **Settings->Subnet**.
6.  Choose the first private subnet in your VNet.
7.  Configure Instance **Settings** -> **Public IP address**:
8.  Configure Instance **Settings** -> Network security group.
9.  Assign both GlusterFS servers to the previously created GlusterFS Network Security Group as described in *Network Security Groups* .

### Attach additional volumes

You will need to attach additional volumes to the GlusterFS instances, as they need two or more virtual disks.

Create two Managed Disks:

1.  Navigate to Azure Portal and click **Create a resource**.
2.  in the search field, type "Managed Disks" and click the search icon.
3.  Fill in the Settings.

For each GlusterFS Server do the following:

1.  Navigate to **Azure Portal ->All resources**.
2.  Select your GlusterFS Instance.
3.  Under**Settings** section select**Disks -> +Add data disk**.
4.  Select the previously created data disk.
5.  Click **Save**.

### Install GlusterFS

Follow the instructions for installing GlusterFS in the [GlusterFS Documentation](https://gluster.readthedocs.io/en/latest/).
