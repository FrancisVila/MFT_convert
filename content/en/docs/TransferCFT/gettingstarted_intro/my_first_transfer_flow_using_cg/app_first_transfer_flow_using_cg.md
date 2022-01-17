{
    "title": "Add applications to use in flows",
    "linkTitle": "Add applications to use in flows",
    "weight": "130"
}When you are working in Central Governance you create *applications* to use in flows. Therefore, if your products did not create applications upon registering, you must create at least two applications to use in your flows.

In this section you create three applications in Central Governance to represent the MainOffice, `Store_66`, and `Store_89`.

### View the registered Transfer CFTs in Central Governance

#### In Central Governance

Select **Products** on the top toolbar to open the **Product List** page.

![](/Images/TransferCFT/gettingstarted1.png)

****Copy the host name for each of the three Transfer CFTs that you will use in these exercises, for example copy them into a table as shown here.****


| Transfer CFT  | Host  | Application name  |
| --- | --- | --- |
| Transfer CFT{{< TransferCFT/componentshortname  >}} 1  | &lt; hostname 1&gt;  | MainOffice  |
| Transfer CFT{{< TransferCFT/componentshortname  >}} 2  | &lt; hostname 2&gt;  | Store_66  |
| Transfer CFT{{< TransferCFT/componentshortname  >}} 1  | &lt; hostname 3&gt;  | Store_89  |


### Add an application

#### In Central Governance

1. Select **Applications** on the top toolbar.  
    ![](/Images/TransferCFT/gettingstarted2.png)
1. Click **Add application**, and complete the Name and Host name fields using the values that you copied from the **Products** page. You can leave other values set to the default.
1. Click **Save application**.

****Results: Your **Application List** page should resemble the following diagram.****

![Application list in Central Governance showing 3 example applications to use in flows](/Images/TransferCFT/application_list_complete.png)
