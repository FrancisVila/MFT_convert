{
    "title": "Archive Maintenance application",
    "linkTitle": "Archive Maintenance application",
    "weight": "180"
}The Archive Maintenance application automatically deletes archived files based on a schedule you define.

You must enable the `ArchiveMaintApp` rules package in the Transaction Manager before you can use an Archive Maintenance application. For more information, see <a href="../transaction_manager/t_st_rulesPackages.htm#EnableRulesPackage#Enable" class="MCXref xref">Manage rules packages</a>.

The configuration for an Archive Maintenance application is stored in the database.

> **Note:**
>
> If the database partition feature is not available because the export database feature is not installed, a warning message will be displayed. For additional information, refer to the SecureTransport Installation Guide.

The Archive Maintenance application defines the file archiving maintenance job schedule. Archive settings and retention policy can be configured on the **Setup &gt; File Archiving** page and for each individual business unit.

For information on configuring the file archiving global configuration, see <a href="../../c_st_setup/c_st_file_archiving/t_st_file_archiving_conf" class="MCXref xref">File archiving global configuration</a>.

1.  Select **Application** and click **Add New**.  
    The *New Application* page is displayed.

2.  Select **Archive Maintenance** from the mandatory **Application Type** list.

3.  Enter a unique **Application Name**. You cannot enter spaces-only values in this field. For more information, see <a href="../../accounts/useraccounts/t_st_create_user_account#Spaces" class="MCXref xref">Spaces in required fields</a>.  

    > **Note:**
    >
    > The application name cannot include any forward slash (/) characters.

4.  (Optional) Use the **Assign** and **Remove** buttons to assign business units for the application. The **Business Unit List** contains the names of business units you have created. For details, see <a href="../../c_st_advancedaccountadministration/c_st_businessunits#Advanced_Accounts_2036285406_1127756" class="MCXref xref">Business units</a>.

5.  (Optional) Enter an application **Description**.

6.  (Optional) In the *Schedule* pane, click **Configure** to <a href="##ConfigureMaintSchedule" class="MCXref xref">Configure a schedule for a maintenance application</a>.

7.  (Optional) Set **Additional attributes**: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](/Images/SecureTransport/SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See <a href="../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Addition" class="MCXref xref">Additional attributes</a>.

8.  Click **Create Application**.  
    To use the Archive Maintenance application, make sure that the `ArchiveMaintApp` and the `ArchiveAgent` rules packages are enabled in the *Rules Packages* page.

## Enable Multithreading

When the Archive maintenance application is to process a large number of files, it can be executed multi-threaded. To enable multithreading, set the number of threads to execute file deletion in the `FileArchiving.DeleteFiles.ProcessingThreads` configuration option.

Increasing the number of threads increases the load on the storage on which the application operates. The number of threads should not exceed 16.

## Set maximum run time

Occasionally, if the Archive Maintenance application is processing a large number of files, it may not be able to finish until the next scheduled occurrence. In this case, it may be advisable to specify the maximum time (in minutes) that you expect the application to run in the `FileArchiving.DeleteFiles.MaximumProcessingTime` configuration option. If you set it to `0`, the application continues to run until it completes.

See parent topic: <a href="../" class="MCXref xref">Applications</a> and follow shortcuts to other applications you need to create or configure.
