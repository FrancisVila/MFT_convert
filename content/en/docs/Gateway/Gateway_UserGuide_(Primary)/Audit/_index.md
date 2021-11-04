{
    "title": "Managing Audit files",
    "linkTitle": "Managing Audits",
    "weight": "180"
}[Viewing Archived Audits](viewing_managing_audit)

[Archiving the current Audit](viewing_managing_audit#Archive_Audit)

[Filtering the Audit message display](viewing_managing_audit#Filter_Audit)

[Refreshing the Audit display](viewing_managing_audit#Filter_Audit)

[Exporting the Audit display](viewing_managing_audit#Export_Audit)

  

Gateway stores the actions performed by users relating to the Gateway configuration in a dedicated audit file, to provide traceability of changes done to the product's configuration. This concerns changes both to global and to object configuration.

This functionality cannot be disabled, and the audit file can only be written by the audit process inside Gateway.

The content can be exported in a readable text format using the command line or UI. When Gateway is stopped, the audit can still be consulted using a dedicated command line tool.

You can archive the current audit file. Gateway then creates an archive file from the current <span class="code">audit.dat </span>file by adding the archiving timestamp. To automatize the process of audit file archiving, you can create a scheduler to call a script calling the archive command.

## How to read the audit file

The audit file is stored in binary mode, unlike the <span class="code">log.dat </span>file, stored in text mode. The audit file is located at %GTW\_installation\_dir%\\Gateway\\run\_time\\audit\\audit.dat.

There are two ways of getting information from the audit file:

-   directly from the GUI, at any time (in the same way as the log file)
-   by exporting the audit file to a text file using <span class="code">pelbase export\_audit </span>or <span class="code">pelauditexport </span>command line commands

## Content of the audit file after export

Here is what you will find in the audit after it is exported:

-   The user login from remote command line commands and GUI. Note that successful user login from local command line commands is not logged.
-   User action on objects. If the object has been modified, both the old and new value of the updated parameters are present in the audit. See below the general syntax for an entry:  
    %tag to linked entries% %timestamp% username:%user% resource\_type:%object type% resource name:%name of the object% action\_type:%action name% action\_result:%result%  
    \[Changed:%parameter% from %old\_value% to %new\_value%\]  
    where:
    -   Resource type: Site, Trading Partner, Configuration, etc
    -   Action type: Update, Create, Delete, Start, Stop, Resume, etc
    -   Action result: Attempt, Success, Failed, Denied. For each action initiated by a user you’ll see at least 2 entries in the audit file: the ‘Attempt’ and the actual result of the action.
    -   For filling %parameter%, %old\_value%, %new\_value% - the terminology from the command line commands have been used.

## Actions not logged to the audit

-   Gateway start, status and stop actions and commands which are using these actions (ex: pelmon), because they are not linked with a Gateway’s user.
-   Users ‘view’ actions on objects, because all the other actions imply also a ‘view’ and the audit would be polluted with lots of ‘view’ actions. This means that the commands which perform view/export operations are not present into the audit file.
-   ‘peluconf standlone’ actions, because they are done when Gateway is stopped and no user is logged
-   pelmig, pelimport, pelexport, because Gateway is stopped when the commands are used
-   local command lines commands: user login/logout
-   pelencpass - does not require user authentication/authorization
-   peluconf get (similar with the view/export on the objects)
-   XMS connector in, xms connector out (deprecated)

Other notes:

-   when creating a new transfer, on the 'Attempt' action, the transfer identifier is unknown, that is why the resource\_name will be “0”.
-   <span class="code">pelpur</span>: only the purge action and the number of transfers deleted are added into the audit; the effective deletion of the transfers is not audited because it is performed by an internal process with admin rights.

## Actions logged into audit without user action

Some actions performed by the Gateway core process (<span class="code">supervisor</span>) may appear in the audit file, because they are triggered by user actions: for example the creation of a transfer implies an update done internally, which is also present in the audit file.

## Actions for Audit files

Actions for audit files are listed in <a href="working_with_audits_cli" class="MCXref xref">Working with Audits (command line)</a>.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
