{
    "title": "Subscribe to Advanced Routing application",
    "linkTitle": "Subscribe to Advanced Routing application",
    "weight": "270"
}To use <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> features, you must subscribe a user account or account template to an <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application.

**Prerequisites**

-   Create an <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application. For instructions on creating an <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application, see <a href="../t_st_create_advanced_routing_application" class="MCXref xref">Create Advanced Routing application</a>.
-   Create at least one transfer site for the selected user account. For instructions on creating a transfer site, see
    <a href="../../../accounts/transfersites" class="MCXref xref">Transfer sites</a>
-   Assign at least one route to the selected user account. For instructions on assigning a Route Template Package, see <a href="../t_st_assign_route_package_template" class="MCXref xref">Assign Route Package Template</a>.

**Workflow**

1.  <a href="#Select" class="MCXref xref">Select a user account</a>
2.  <a href="#Configur" class="MCXref xref">Configure general settings</a>
3.  <a href="#Configur2" class="MCXref xref">Configure post transmission actions</a>
4.  <a href="#Complete" class="MCXref xref">Complete the subscription</a>

<span id="Select"></span>

## Select a user account

1.  Select **Accounts > User Accounts**. The *User Accounts* page is displayed.
2.  Click on the name of the account that you want to subscribe to the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application.  
    The *User Account Settings* page is displayed with details for the selected account.
3.  Click the **Subscriptions** tab for the selected account.
4.  Click **Subscribe**.  
    The settings page for the subscription is displayed.

<span id="Configur"></span>

## Configure general settings

In the *General Settings* pane:

1.  In the **Subscription Folder** field, type the full subscription folder path under the user's home folder. The subscription folder name can contain up to 254 characters.  

    > **Note:**
    >
    > You cannot use the following characters in the subscription folder name: \* &lt; > ? " \\ | :

2.  Select the **Encrypt mode**. Selecting the **Encrypt mode** allows you to configure repository encryption for accounts at the per-subscription level. For additional information, refer to <a href="../../../c_st_setup/c_st_certificates/t_st_repository_encryption_certificate" class="MCXref xref">Repository encryption certificate</a>.  
    Select **Default** to inherit the encryption mode for the subscription folder from the account or the global settings.  
    Select **Enable** to encrypt all files uploaded to the subscription folder.  
    Select **Disable** to upload unencrypted files to the subscription folder.  

    > **Note:**
    >
    > Files that are transferred via Advanced Routing or Standard Routing will be encrypted or not based on the target subscription folder repository encryption setting.

      
    For additional subscription folder repository encryption information, refer to <a href="../../../accounts/c_st_subscriptions/t_st_subscriptions#Configur" class="MCXref xref">Configure general settings</a>.

3.  In the *Flow Settings* pane, select the **Existing flow attributes**.  
    If **Preserve** is selected, the attributes defined in the *Flow Attributes* pane will be applied only to newly received files which do not have associated flow attributes.  
    If **Overwrite** is selected, the attributes defined in the *Flow Attributes* pane will overwrite any existing attributes for incoming files (for example, files published to this folder from another subscription folder).  
    When **Append** is selected, only the attributes which are not defined for incoming files will be applied. Existing attributes will be preserved.

4.  In the *Flow/Subscription Attributes* pane:
    1.  To add a flow or a subscription attribute, click **Add Attribute**. For additional information, refer to <a href="../../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Flow" class="MCXref xref">Flow and subscription attributes</a>.
    2.  **Add Attribute** allows you to add custom properties as Key=Value pairs. Flow attributes can be used for expression evaluation in Advanced Routing only when the application operates with files. Subscription attributes are bound to the subscription, therefore, they can be used for expression evaluation in all Advanced Routing fields.
    3.  Some examples of attributes are:
        <table>
           <thead>
              <tr>
        <th class="HeadE-Column1-Header1">Attribute         </th>
        <th class="HeadD-Column1-Header1">Value         </th>
              </tr>
           </thead>
           <tbody>
              <tr>
                 <td>userVars.1         </td>
                 <td>internalEmail@axway.com         </td>
              </tr>
              <tr>
                 <td>userVars.2         </td>
                 <td>ReportsMonitor         </td>
              </tr>
           </tbody>
        </table>

        To access attributes, see the following examples:`${account.attributes['userVars.1']}``${account.attributes['userVars.2']}`
        For example, the `account.attributes` is the selector for attributes of the account used to execute the current route - it must be written exactly as shown.The `userVars.` prefix must be prepended to the attribute name .All this should be written as an EL expression: `${...}`
    4.  Click the **Save** (![](/Images/SecureTransport/SaveIcon.png)) icon.

<span id="Configur2"></span>

## Configure post transmission actions

Configuring the post transformation actions is divided into selecting the post transformation actions, the post client download actions, and the post routing settings.

### Select the post transformation actions

In the *For Files Received from this Account or its Partners* pane:

1.  To set a schedule for automatic retrieval of files from a remote server, select the **Automatically Retrieve Files From** check box and then select the transfer site from the drop-down list. If you select a PeSIT transfer site, you can select a **Transfer Profile** from the list or leave the field empty to use the default PeSIT transfer profile. For more information, see <a href="../../../accounts/transfersites#AccountsMenu_2253641766_1248932" class="MCXref xref">Transfer sites</a>.  
    The *Schedule* pane and the **Retrieve Files Now** button are displayed.  
    If subscription retrieves files from a Folder Monitor transfer site, to configure a scheduled Folder Monitor operation, you must select **Set explicit FolderMonitor Schedule**.

2.  Click **Configure** in the *Schedule* pane to set up a future one time event or a recurring schedule.  
    The *Configure Schedule* dialog box is displayed.

3.  In the *Configure Schedule* dialog box, specify the desired conditions for the scheduled server‑initiated file retrieval.  
    To schedule an immediate recurrent task, select **Schedule events on a recurring basis** and then select **Start now** in the *Length of Recurrence* pane. The task will begin on the next minute.  

    > **Note:**
    >
    > If the schedule is set on a recurring basis, the Recurrence options dynamically change with respect to the recurrence condition: Hourly, Daily, Weekly, Monthly, or Yearly.If the server goes down and restarts, the scheduler will not execute any scheduled tasks missed during the server down time.If you configure a schedule and save it after the scheduled start time, the task will not be executed. You must save your configured schedule before the scheduled start time.

4.  (Optional) Enter the **Maximum number of parallel transfers**. If you enter a value greater than zero, SecureTransport executes only the specified number of transfers in parallel. If the value is null or zero, the maximum number of parallel transfers is limited by system capacity.  
    The maximum number of parallel transfers limit is applied cluster wide. The limit for files transferred from the client will not be exceeded. Due to limitations in Standard Cluster communication mode, the parallel pulls limit can be exceeded when there are several connections. If you want to force the limit, then the `force.standart.cluster.sit.pulls.sync=true` system property should be added to the `start_tm_console`. Adding the property to the `start_tm_console` has a performance penalty due to increased cluster communication.  
    Note that the `force.standart.cluster.sit.transfers.sync` value overrides the value of the `force.standart.cluster.sit.pulls.sync` property, used in previous <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> versions for the same purposes.  

5.  (Optional) Click the **Retrieve Files Now** button to immediately trigger a one time file
    pull.  

    > **Note:**
    >
    > When the one-time pull event is triggered, the admin daemon will try to connect to the Transaction Manager until the maximum number of retry attempts is reached as specified by the Streaming.Event.maxRetries server configuration parameter. The period between each retry is specified by the Streaming.Event.idleTimeout server configuration parameter. When the maximum number of retries is reached, the execution process finishes. For more information on server configuration parameters, refer to View and change server configuration parameters.

6.  In the *Post Transmission Settings* pane, select the **Route**. The selected route will be executed on files uploaded to the subscription folder.

7.  In the *On Success* pane, to execute the selected route when the server does not return any, select the **Execute route when the remote server returns no files** check box. The selected route will be executed when directory listing is successful but there are no files matching the download pattern.

8.  To trigger processing of files based on a specific condition, select the **Trigger processing of files based on condition** check box.  
    When **unchecked**, each file received in the subscription folder is submitted for processing.  
    When **checked**, processing of the files in the subscription folder will be triggered upon a specific condition.

9.  Enter the trigger condition in the **Trigger condition** field.  
    Example:  
    To trigger file processing when the file the extension trigger arrives:  
    `${stenv['target'].matches('.*.trigger')?1:0}`

10. Select the files to submit for processing.  
    If **All files in the subscription folder** (default) is selected, all files in the subscription folder are processed except for the trigger file.  
    If **Files read from trigger file content** is selected, data file names will be read from the trigger file content. Each file name should be on a new line. The whitespace characters before and after the file names are discarded. Also, lines containing only whitespace characters are not considered as files.  
    Trigger file format:  
    `file1.txt`  
    `file2.txt`  
    `file3.png`  
    When **Files read from trigger file content** is selected, the panel expands with three options which determine what happens with the AR processing if there is a missing file listed in the trigger file:  
    -   If **Fail** is selected, the AR processing will fail.
    -   If **Continue** is selected, the AR processing will continue for the existing files.
    -   If **Retry** is selected, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> will retry to execute the trigger file. You need to specify the number of times it should retry and the delay between each attempt in seconds.

      
    If **Files matching specific filename pattern** is selected, the files matching the defined filename pattern will be processed.  
    The expression language can be used to specify the filename pattern.  
    Examples:  
    All text files - with `.txt` extension:  
    `*.txt`  
    All files that have names same as the trigger file name without extension.  
    `${basename(stenv['target'])}.*`

11. In the *On Temporary Failure* pane, select the option for temporary failed transfers. The temporarily failed transfers will be retried. The temporary failure option is not applicable for Client Initiated Transfers.  

    > **Note:**
    >
    > The following actions are applied to files that did not properly arrive in the designated folder.

      
    If **No Action** is selected, no actions take place on the temporarily failing files.  
    If **Route** is selected, the selected route will be triggered. By default, the route will be triggered without the temporarily failing files. Select **Submit the transferred file(s) to the route for processing** to perform transformations on the temporarily failing files inside the selected route.  
    If **Delete** is selected, the temporarily failing files are deleted.  
    If **Move/Rename File To** is selected, you are required to specify a directory in the location where you are transferring the temporarily failing files to and to provide an expression to rename the files.

12. In the *On Failure* pane, select the permanent failure option.  

    > **Note:**
    >
    > The following actions are applied to files that did not properly arrive in the designated folder.

      
    If **No Action** is selected, no actions take place on the failed files.  
    If **Route** is selected, the selected route will be triggered. By default, the route will be triggered without the failed files. Select **Submit the transferred file(s) to the route for processing** to perform transformations on the failed files inside the selected route.  
    If **Delete** is selected, the failed files are deleted.  
    If **Move/Rename File To** is selected, you are required to specify a directory in the location where you are transferring the failed files to and to provide an expression to rename the files.

### Select the post client download actions

In the *Post Client Download Actions* pane:

> **Note:**
>
> Post Client Download Actions will be applied to each file downloaded from the subscription folder.

1.  In the *On Success* pane, select the action to take place for each successful client download.  
    If **No Action** is selected, no actions take place on the downloaded files.  
    If **Route** is selected, the selected route will be triggered. By default, the route will be triggered without the files that are being downloaded. Select **Submit the transferred file(s) to the route for processing** to perform transformations on the files that are being downloaded inside the selected route.  
    If **Delete** is selected, after a file is successfully downloaded by the client, it is deleted from the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> subscription folder.
2.  In the *On Failure* pane, select the action to take place for each failed client download.  
    If **No Action** is selected, no actions take place on the files that failed downloading.  
    If **Route** is selected, the selected route will be triggered. By default, the route will be triggered without the files that are being downloaded. Select **Submit the transferred file(s) to the route for processing** to perform transformations on the files that are being downloaded inside the selected route.  
    If **Delete** is selected, after a file download by the client fails, the file is deleted from the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> subscription folder.

### Select the post routing actions

In the *Post Routing Settings* pane:

> **Note:**
>
> The Post Routing Settings actions are applied to files that have triggered a route package.

1.  In the *On Success* pane, select the action to take place for each file that successfully triggered a route.  
    If **No Action** is selected, no actions take place on the files that successfully triggered a route.  
    If **Delete** is selected, the files that successfully triggered a route are deleted.  
    If **Move/Rename File To**is selected, you are required specify a directory in the location where you are transferring the files to that successfully triggered a route and to provide an expression rename the files.
2.  In the *On Failure* pane, select the action to take place for each file that failed to trigger a route.  
    If **No Action** is selected, no actions take place on the files that failed to trigger a route.  
    If **Delete** is selected, the files that failed to trigger a route are deleted.  
    If **Move/Rename File To**is selected, you are required specify a directory in the location where you are transferring the files to that failed to trigger a route and to provide an expression rename the files.

<span id="Complete"></span>

## Complete the subscription

To complete the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> subscription, click **Add**.

**Related topics:**

-   <a href="../t_st_create_delegated_administrator" class="MCXref xref">Advanced Routing delegated administrator</a>
-   <a href="../t_st_create_user_accounts" class="MCXref xref">Create user accounts</a>
-   <a href="../t_st_create_advanced_routing_application" class="MCXref xref">Create Advanced Routing application</a>
-   <a href="../t_st_manage_route_package_templates" class="MCXref xref">Manage Route Package Templates</a>
-   <a href="../t_st_manage_routes" class="MCXref xref">Manage Routes</a>
-   <a href="../t_st_assign_route_package_template" class="MCXref xref">Assign Route Package Template</a>