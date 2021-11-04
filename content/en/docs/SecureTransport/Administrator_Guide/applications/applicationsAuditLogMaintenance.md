{
    "title": "Audit Log Maintenance application",
    "linkTitle": "Audit Log Maintenance application",
    "weight": "190"
}The Audit Log Maintenance application automatically deletes Audit log records that are older than a specified number of days or months (6 months by default). You can schedule how often to run this application and configure it to optionally export these records prior to deletion.

Make sure that the `AuditLogMaintApp` rules package is enabled in the Transaction Manager before you enable an Audit Log Maintenance application. For more information, see <a href="../transaction_manager/t_st_rulesPackages.htm#EnableRulesPackage#Enable" class="MCXref xref">Manage rules packages</a>.

Use the following procedure to create an Audit Log Maintenance application.

1.  Select **Application** and click **Add New**.  
    The *New Application* page is displayed.

2.  Select **Audit Log Maintenance** from the mandatory **Application Type** list.

3.  Enter a unique **Application Name**. You cannot enter spaces-only values in this field. For more information, see <a href="../../accounts/useraccounts/t_st_create_user_account#Spaces" class="MCXref xref">Spaces in required fields</a>.  

    > **Note:**
    >
    > The application name cannot include any forward slash (/) characters.

4.  (Optional) Use the **Assign** and **Remove** buttons to assign business units for the application. The **Business Unit List** contains the names of business units you have created. For details, see <a href="../../c_st_advancedaccountadministration/c_st_businessunits#Advanced_Accounts_2036285406_1127756" class="MCXref xref">Business units</a>.  

    > **Note:**
    >
    > As with all applications, assigning business units to the application controls which delegated administrators can manage the application. It does not control which log entries Transfer Log Maintenance processes.

5.  (Optional) Enter an application **Description**.

6.  In the **Delete audit log entries when** field, specify in days or months how old transfer log entries will be when they are deleted. This field is mandatory.  
    You cannot enter spaces-only values in this field. For more information, see <a href="../../accounts/useraccounts/t_st_create_user_account#Spaces" class="MCXref xref">Spaces in required fields</a>.

7.  To export the deleted audit log entries to a file before they are deleted, select **Enable data export**, and, in the **Export folder** field, specify where the export files are stored. You must enter a full directory path.

8.  (Optional) In the *Schedule* pane, click **Configure** to<a href="##ConfigureMaintSchedule" class="MCXref xref">Configure a schedule for a maintenance application</a>.  
    For information on working with the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> scheduler , see <a href="../../accounts/c_st_subscriptions/t_st_subscriptions#Schedule" class="MCXref xref">Scheduled downloads and tasks</a>. Click **OK** when finished setting the schedule.

9.  (Optional) Set **Additional attributes**: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](/Images/SecureTransport/SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See <a href="../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Addition" class="MCXref xref">Additional attributes</a>.

10. Click **Create Application**.

  
See parent topic: <a href="../" class="MCXref xref">Applications</a> and follow shortcuts to other applications you need to create or configure.