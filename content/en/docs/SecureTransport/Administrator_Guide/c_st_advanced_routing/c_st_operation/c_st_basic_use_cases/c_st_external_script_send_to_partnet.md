{
    "title": "External Script and Publish To Account",
    "linkTitle": "External Script and Publish To Account",
    "weight": "320"
}The following topics provide the overview, prerequisites, configuration steps, and flow of events for the External Script and Publish To Account use case:

-   [Overview](#overview)
-   [Prerequisites](#prerequi)
-   [Step to configure the flow](#step)
-   [Script example](#script)
-   [Flow of events](#flow)

**Related topics:**

-   [PGP Decryption and Publish To Account](../c_st_pgp_decryption_publish_to_account)
-   [Line Ending and Publish To Account](../c_st_line_ending_publish_to_account)
-   [PGP Encryption and Send To Partner](../c_st_send_to_partner)
-   [Compress and Send To Partner](../c_st_compress_send_to_partner)
-   [Decompress and Publish To Account](../c_st_decompress_publish_to_account)
-   [Send To Partner (PeSIT)](../c_st_send_to_partner_pesit)

## <span id="Overview"></span>Overview

Compress incoming files by leveraging an external script and publish the result archive to the local account.

## <span id="Prerequi"></span>Prerequisites

-   Download and install 7zip on your SecureTransport machine.
-   Create a Route Package Template. For instructions on creating a Route Package Template, refer to [Add Route Package Template](../../../c_st_configuration/t_st_manage_route_package_templates).
-   Create an Advanced Routing application instance. For instructions on creating an Advanced Routing application instance, refer to .
-   Create a SecureTransport user account. For instructions on creating an user account, refer to [User accounts](../../../../accounts/useraccounts).

## <span id="Step"></span>Step to configure the flow

1.  Create a script with the following contents that uses 7zip to compress the incoming files.  
    
    1.  Modify the third line of the script and set the correct path to the *7z* executable.
    2.  Name the script `7zip-compress.sh`.
    3.  Ensure the script is accessible by SecureTransport. For this example, it needs to be deployed in the `/bin/agents` subfolder of the SecureTransport installation folder.
2.  Create and configure a subscription to the Advanced Routing application by navigating to the account’s *Subscriptions* tab and clicking the **Subscribe…** button. For Advanced Routing subscription configuration details, refer to [Subscribe to Advanced Routing application](../../../c_st_configuration/t_st_subscribe_advanced_routing_application).
    1.  Configure the subscription folder.
    2.  To await multiple files, configure a condition (for example: trigger file) on which to submit the files to the route.
    3.  (Optional) Configure the rest of the settings.
    4.  Click **Add** when done.
3.  Navigate to the *Routes* tab of the created account and assign a new route package to the account by choosing the created Route Package Template and clicking the **Assign Route** button. For assigning a route configuration details, refer to [Assign Route Package Template](../../../c_st_configuration/t_st_assign_route_package_template).
4.  Assign a subscription to the new route package by selecting **Assign** in the *Subscriptions* pane and selecting the subscription created in Step 2.
5.  Create a new route by clicking the **New Route** button in the *Specific Settings* pane. For route configuration details, refer to [New Route](../../../c_st_configuration/t_st_manage_routes).
    1.  Configure the new route’s name and (optionally) description.
    2.  Add and configure an External Script step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button. For External Script configuration details, refer to [External Script](../../../c_st_route_step_transformations/t_st_external_script).
        1.  Specify the external script path and arguments as follows:
        2.  `/bin/sh -C ${FILEDRIVEHOME}/bin/agents/7zip-compress.sh archive-${timestamp}.7z`
        3.  Select **Log script's standard output to Server log**.
        4.  (Optional) Configure the rest of the settings.
        5.  Click **Save** when done.
    3.  Add and configure a Publish to Account step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button. For Publish To Account configuration details, refer to [Publish To Account](../../../c_st_route_steps/t_st_publish_to_account).
        1.  Uncheck **Proceed with route execution on step failure**.
        2.  Select an account to publish to (for example, the current account).
        3.  Select a folder to publish the file to (for example, the subscription folder configured in Step 2).
        4.  (Optional) Configure the rest of the settings.
        5.  Click **Save** when done.
6.  Save the route and the route package.

## <span id="Script"></span>Script example

    #!/bin/sh 

    SEVENZIP="<path to '7z' executable>"



    if [ "X${ST_ACCOUNT_HOME}" = "X" ]; then

            echo "ST_ACCOUNT_HOME environment variable not set, aborting."

            exit 1

    fi


    # Dump the environment in the account home folder

    env > ${ST_ACCOUNT_HOME}/dumpenv.${$}


    if [ ! -x $SEVENZIP ]; then

            echo "\"$SEVENZIP\" does not exist or is not an executable, aborting."

            exit 2

    fi


    # Go to the sandbox folder

    cd $SANDBOX_FOLDER


    # Keep track of the files that will be archived to delete them later

    FILELIST=`ls`


    $SEVENZIP a $1 *

    exitcode=$?


    if [ $exitcode -ne 0  ]; then

            echo "Failed to compress files \"$FILELIST\", aborting."

            exit $exitcode

    fi


    # Delete the archived files

    for file in $FILELIST ;

    do

    rm -f $file;

    done

                        
                        

## <span id="Flow"></span>Flow of events

1.  Multiple files are uploaded via any protocol to the Advanced Routing subscription folder.
2.  The trigger file (file with `.trigger` extension) is uploaded to the subscription folder.
3.  The Advanced Routing application triggers the route.
4.  The uploaded files are compressed into a single 7zip archive and published to the subscription folder.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In the end there will be several files present in the subscription folder – the input files, the trigger file, and the archive. To automatically remove the input files and the trigger file, select <strong>Post Processing Action &gt; On Success &gt; Delete</strong> in the subscription settings.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Publishing the archive file in <span>Advanced Routing</span> subscription folder does not trigger the route execution once again, because <em>Trigger target subscription actions</em> is <strong>unchecked</strong>.         </td>
      </tr>
</table>
