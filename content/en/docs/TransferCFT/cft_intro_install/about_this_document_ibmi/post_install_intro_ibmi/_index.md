{
    "title": "Post-installation",
    "linkTitle": "Post-installation",
    "weight": "160"
}## Transfer CFT in production

This chapter describes how to operate Transfer CFT, and is comprised of the following sections:

-   [Predefined commands](operating_cft/predefined_commands)
-   [CFTUTIL commands](operating_cft/submit_cftutil_commands)
-   [Source files interpretation](operating_cft/interpret_source_member)
-   [Start/stop the UI server](start_copilot_server)
-   [Run Transfer CFT](operating_cft/running_transfer_cft) jobs:
    -   [Query Transfer CFT messages](querying_transfer_cft_messages.htm)
    -   [Start Transfer CFT](operating_cft/start_cft)
    -   [Submit a transfer command](submit_transfer_command)
-   [Transfer CFT shutdown](operating_cft/shut_cft)

## <span id="Transfer"></span>Transfer CFT menu usage

Other than during installation, which runs the Transfer CFT manager automatically, you can enter one of the following commands to start the manager:

-   CFT
-   CALL CFTMENU

## Create Transfer CFT system object

Now that you have installed your Transfer CFT, you will want to recreate Transfer CFT objects. Proceed to the Transfer CFT menu and press 4 to access the following options:

1\. Create job queue.

Create a JOBQ object to launch Transfer CFT jobs using the default values.

2\. Create job description.

Create a JOBD object to launch Transfer CFT jobs using the default values. This programs the initial library list and the Transfer CFT production libraries (CFTPGM and CFTPROD).

3\. Create subsystem.

Create an SBS object to launch Transfer CFT jobs. This creates a subsytem with a storage size of 250MB.

4\. Add job-queue entry.

Add a job queue entry to the subsystem that you created in step 3 to link it with the JOBQ that you created in step 1. The maximum active job is unlimited.

5\. Create class.

Create a class CLS object for Transfer CFT with a time slice of 5000 milliseconds.

6\. Add routing entry.

Add a routing entry to the subsytem created in step 3 to link it with the class created in step 5. This uses the SEQNBR(9999) CMPVAL(\*ANY) and PGM(QCMD) options.

7\. Add communication entry.

Add a communication entry to link the subsystem created in step 3 with the JOBD created in step 2. This uses the DFTUSR(CFT) ??MODE(\*ANY) ??MAXACT(\*NOMAX) options.

8\. Change profile.

Change the user profile of the current user to specify that the user now uses the JOBD in step 2, and subsequently the subsystem and JOBQ created in the other steps and linked with the JOBD.

## Verify your installation

See the installation if you encounter problems with starting Transfer CFT.

### Installed directories

The act of installing Transfer CFT creates a library that contains product binaries and templates. Do no store any personal files in this library, or modify existing files in this library, as both are erased during updates.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">By default, this library is called CFTPGM.</td>
</tr>
</tbody>
</table>

## Register with Central Governance

If you intend to implement Central Governance, please refer to the Transfer CFT *User's Guide &gt; [*Register with* Central Governance](https://docs.axway.com/bundle/TransferCFT_36_UsersGuide_allOS_en_HTML5/page/Content/cft_installation/migrate/register_CG.htm)* page for registration details.
