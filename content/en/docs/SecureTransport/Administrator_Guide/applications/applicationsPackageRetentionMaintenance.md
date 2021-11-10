{
    "title": "Package Retention Maintenance application",
    "linkTitle": "Package Retention Maintenance application",
    "weight": "280"
}The Package Retention Maintenance applicaiton deletes expired file packages from ad hoc file transfers.

You must enable the `PackageRetentionMaintApp` rules package in the Transaction Manager before you can use a Package Retention Maintenance application. For more information, see <a href="../transaction_manager/t_st_rulesPackages.htm#EnableRulesPackage#Enable" class="MCXref xref">Manage rules packages</a>.

> **Note:**
>
> It is still possible to download anonymous attachments after message expiration, if they have not yet been deleted by any scheduled Package Retention Maintenance Applications.

Use the following procedure to create a Package Retention Maintenance application.

1.  Select **Application** and click **Add New**.  
    The *New Application* page is displayed.

2.  Select **Package Retention Maintenance** from the mandatory **Application Type** list.

3.  Enter a unique **Application Name**. You cannot enter spaces-only values in this field. For more information, see <a href="../../accounts/useraccounts/t_st_create_user_account#Spaces" class="MCXref xref">Spaces in required fields</a>.  

    > **Note:**
    >
    > The application name cannot include any forward slash (/) characters.

4.  (Optional) Use the **Assign** and **Remove** buttons to assign business units for the application. The **Business Unit List** contains the names of business units you have created. For details, see <a href="../../c_st_advancedaccountadministration/c_st_businessunits#Advanced_Accounts_2036285406_1127756" class="MCXref xref">Business units</a>.

5.  (Optional) Enter an application **Description**.

6.  In the **Stop running after: \_\_\_\_ minutes** field, enter the maximum number of minutes the application runs each time it is started.

7.  (Optional) In the *Schedule* pane, click **Configure** to<a href="#ConfigureMaintSchedule" class="MCXref xref">Configure a schedule for a maintenance application</a>.

8.  (Optional) Set **Additional attributes**: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](/Images/SecureTransport/SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See <a href="../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Addition" class="MCXref xref">Additional attributes</a>.

9.  Click **Create Application**.

  
See parent topic: <a href="../" class="MCXref xref">Applications</a> and follow shortcuts to other applications you need to create or configure.

**Related topics:**

-   <a href="" class="MCXref xref">Manage applications</a>
-   <a href="../applicationsarchivemaintenance" class="MCXref xref">Archive Maintenance application</a>
-   <a href="../applicationsauditlogmaintenance" class="MCXref xref">Audit Log Maintenance application</a>
-   <a href="../applicationssentinellinkdatamaintenance" class="MCXref xref">Axway Sentinel Link Data Maintenance application</a>
-   <a href="../applicationstransfercft" class="MCXref xref">Axway Transfer CFT application</a>
-   <a href="../applicationsbasic" class="MCXref xref">Basic Application</a>
-   <a href="../applicationstransferfileservicesinterface" class="MCXref xref">File Transfer via File Services Interface application</a>
-   <a href="../applicationsh2s" class="MCXref xref">Human to System application</a>
-   <a href="../applicationslogentrymaintenance" class="MCXref xref">Log Entry Maintenance application</a>
-   <a href="../applicationsloginthresholdmaintenance" class="MCXref xref">Login Threshold Maintenance application</a>
-   <a href="../applicationssharedfolder" class="MCXref xref">Shared Folder application</a>
-   <a href="../applicationssitemailbox" class="MCXref xref">Site Mailbox application</a>
-   <a href="../applicationsstandardrouter" class="MCXref xref">Standard Router application</a>
-   <a href="../applicationstransferlogmaintenance" class="MCXref xref">Transfer Log Maintenance application</a>
-   <a href="../applicationsunlicensedacctsmaintenance" class="MCXref xref">Unlicensed Accounts Maintenance application</a>
