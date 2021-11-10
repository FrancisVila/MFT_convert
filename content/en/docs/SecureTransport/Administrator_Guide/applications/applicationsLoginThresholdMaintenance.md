{
    "title": "Login Threshold Maintenance application",
    "linkTitle": "Login Threshold Maintenance application",
    "weight": "270"
}The Login Threshold Maintenance application unlocks accounts locked according to the selected "Lock account after N successful logins" option in the *Account settings* and sends a report to specified email contacts.

Use the following procedure to create a Login Threshold Maintenance application.

1.  Select **Application** and click **Add New**.  
    The *New Application* page is displayed.

2.  Select **Login Threshold Maintenance** from the mandatory **Application Type** list.

3.  Enter an unique **Application Name**. You cannot enter spaces-only values in this field. For more information, see <a href="../../accounts/useraccounts/t_st_create_user_account#Spaces" class="MCXref xref">Spaces in required fields</a>.  

    > **Note:**
    >
    > The application name cannot include any forward slash (/) characters.

4.  (Optional) Use the **Assign** and **Remove** buttons to assign business units for the application. The **Business Unit List** contains the names of business units you have created. For details, see <a href="../../c_st_advancedaccountadministration/c_st_businessunits#Advanced_Accounts_2036285406_1127756" class="MCXref xref">Business units</a>.

5.  (Optional) Enter an application **Description**.

6.  (Optional) Select **Enable unlock functionality**. **Enable unlock functionality** is selected by default.

7.  (Optional) Select **Send Report**. If **Send Report** is selected, a report will be sent to the specified email addresses.
    -   If **Enable unlock functionality** is selected, the report will contain a list of unlocked users.
    -   If **Enable unlock functionality** is not selected, the report will contain a list of locked, due to login threshold functionality, users.

8.  Enter the email address or addresses to deliver the report to in the **Email Contact(s)** field. Email addresses can be separated by either a comma or a semicolon.

9.  Select the email template for the report from the **Report Email Template** list. The `LoginThresholdReport.xhtml` template is the default template for the Login Threshold Maintenance application.

10. (Optional) In the *Schedule* pane, click **Configure** to <a href="#ConfigureMaintSchedule" class="MCXref xref">Configure a schedule for a maintenance application</a>.

11. (Optional) Set **Additional attributes**: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](/Images/SecureTransport/SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See <a href="../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Addition" class="MCXref xref">Additional attributes</a>.

12. Click **Create Application**.

  
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
-   <a href="../applicationspackageretentionmaintenance" class="MCXref xref">Package Retention Maintenance application</a>
-   <a href="../applicationssharedfolder" class="MCXref xref">Shared Folder application</a>
-   <a href="../applicationssitemailbox" class="MCXref xref">Site Mailbox application</a>
-   <a href="../applicationsstandardrouter" class="MCXref xref">Standard Router application</a>
-   <a href="../applicationstransferlogmaintenance" class="MCXref xref">Transfer Log Maintenance application</a>
-   <a href="../applicationsunlicensedacctsmaintenance" class="MCXref xref">Unlicensed Accounts Maintenance application</a>
