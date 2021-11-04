{
    "title": "Send To Partner",
    "linkTitle": "Send To Partner",
    "weight": "240"
}The Send To Partner routing step enables routing to a specified partner account as part of a route. To add a Send To Partner routing step to a Route Package Template or Route Package take the following steps:

1.  Designate file filtering.
2.  Determine whether or not to proceed with route execution on step failure.
3.  Configure transfer settings.
4.  Configure retry settings.
5.  Determine post routing actions.

> **Note:**
>
> Steps 1 and 3 are mandatory. All other steps are optional.

The following topics provide detailed Send To Partner route step configuration information:

-   <a href="#File" class="MCXref xref">Input Files</a>
-   <a href="#Proceed" class="MCXref xref">Proceed with route execution on failure</a>
-   <a href="#Transfer" class="MCXref xref">Transfer Settings</a>
-   <a href="#Configur" class="MCXref xref">Configure advanced PeSIT settings</a>
-   <a href="#Overwrit" class="MCXref xref">Overwrite upload folder</a>
-   <a href="#Route" class="MCXref xref">Route files as</a>
-   <a href="#Send" class="MCXref xref">Send trigger file</a>
-   <a href="#Retry" class="MCXref xref">Retry settings</a>
-   <a href="#Post" class="MCXref xref">Post Routing Action</a>

**Related topic:**

-   <a href="../t_st_publish_to_account" class="MCXref xref">Publish To Account</a>

<span id="File"></span>

## Input Files

The Input Files settings consist of the selection *Process only result from preceding step* and determining the Name Filter.

### Process only result from preceding step

When *Process only result from preceding step* is **enabled** only files produced by the preceding step will be used as input for this step.

When *Process only result from preceding step* is **disabled** or this is the first step all current working files will be used as input for this step.

> **Note:**
>
> The Name Filter settings will also be applied on a given set of input files.

### Name Filter

The Name Filter can either be set to process all files forwarded by the selection of *Process only result from preceding step* or process files based on a designated filename pattern forwarded by the selection of *Process only result from preceding step*. If *Process all files* is selected, all files forwarded by the selection of *Process only result from preceding step* are processed. If *Process files based on a filename pattern* is selected, only the files that match the file globbing or regular expression pattern are processed.

#### Filename patterns

Filename pattern matching supports `glob` and `regexp` syntax expressions.

When the designated pattern type is *File Globbing* then the `String` representation of the filename is matched using a limited pattern language that resembles regular expressions but with a simpler syntax. For example:

-   Matches files ending in `.xml`.

    `*.xml`

-   Matches file names starting with `foo.` that have a double character extension.

    `foo.??`

-   Matches file names ending in `.1`, `.2`, `.3`, `.4`, `.5`, `.6`, `.7`, `.8`, `.9`, `.0`.

    `*.[0-9]`

-   Matches file names having a single character extension different from `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`, `0`.

    `*.[!0-9]`

When the designated syntax is *Regular Expression* then the `String` representation of the filename is matched against a `Perl5.003` regular expressions. Perl5 extended regular expressions are also supported. For example:

-   Matches files ending in `.xml` or `.txt`.

    `.*\.(xml|txt)`

-   Case insensitive match of` data.xml` file.

    `(?i)data\.xml`

<span id="Proceed"></span>

## Proceed with route execution on failure

If *Proceed with route execution on step failure* is checked, the route execution continues even if the step execution fails.

<span id="Transfer"></span>

## Transfer Settings

The transfer setting consist of specifying an account, selecting account transfer sites, and selecting a transfer site profile.

### Specify an account

The *Specify an account* field, is used to specify the account who holds the information (transfer site) about the recipient of the file. Either an account name, login name, or EL expression can be used to determine the recipient based on the environment information (such as filename).

The *Specify an account* field has auto-completion which shows a list of existing accounts containing the same search term.

Once an account is selected its transfer sites are populated in the select box. The population is possible only if the account name matches the login name of the user.

If an account name is unknown (for example, expression based) or the login name does not match the account name, its transfer sites are determined at runtime. Transfer sites can be expression based as well.

Account template names shouldn't be used in this field. The transfer sites which belong to the template will be populated but the step will fail. When using account templates, the value of this field should be the login name.

> **Note:**
>
> Auto-completion will suggest account names and user (login) names.

> **Note:**
>
> You can access the first value of a given SSO attribute with name attributeName with the expression ${sso.attributes\['attributeName'\]\[0\]}.

### Account transfer sites

Transfer sites can either be existing transfer sites retrieved from the account selected or expression based ones.

To use an expression, click the edit icon (![](/Images/SecureTransport/EditIcon.png)) next to the select box and enter the expression in field.

Expression for specifying the sites allows both EL and the wild card symbols - '\*' and '?'.

Example:

If expression like `${account.name}-HTTP-*` is specified this would match all transfer sites (within the account selected) such as:

`- jsmith-HTTP-Partner1`

`- jsmith-HTTP-Partner2`

`- etc.`

> **Note:**
>
> Only transfer sites with proper access level will be listed. For more details see Transfer sites.

### Transfer profile

Transfer profile property is used only if the transfer site is of type PeSIT. Otherwise, it is ignored.

When the transfer profile is specified by using an EL expression there are three possible cases:

1.  EL expression does not match any account transfer profiles - the default transfer profile is used then.
2.  EL expression matches more than one transfer profile - the default transfer profile is used.
3.  EL expression matches exactly one transfer profile - the matched transfer profile is used.

The transfer profile can be selected from the listed ones or an EL expression can be used. To use an expression, click the edit icon (![](/Images/SecureTransport/EditIcon.png)) next to the select menu and enter the expression in field.

<span id="Configur"></span>

## Configure advanced PeSIT settings

If *Configure advanced PeSIT settings* is selected, the advanced PeSIT settings can be configured. The advanced PeSIT settings consist of selecting the store and forward mode, specifying the virtual file name and data encoding, and configuring the record length, file label, final destination, and user message.

> **Note:**
>
> PeSIT settings are only used for transfers over PeSIT.

<span id="Store"></span>

### Store and forward mode

The store and forward mode selections are:

-   START\_NEW
-   PRESERVE

The *PRESERVE* store and forward mode preserves the current store and forward transfer (if any). The transfer will fail if the PeSIT transfer site is used for sending files that were received via a protocol other than PeSIT.  

The *START\_NEW* store and forward mode initiates a new store and forward transfer and the current transfer (if any) is acknowledged.

### Virtual file name

The *Virtual file name* field is used to overwrite the virtual file name (PI12) predefined in the transfer profile. To preserve the predefined virtual file name, either leave the field empty or enter the EL expression `${pesit.file.filename}`.

This configuration parameter corresponds to the **IDF** parameter in Axway Transfer CFT.

### Data encoding

Data encoding selections are:

-   ASCII
-   EBCDIC
-   BINARY
-   EBCDIC\_NATIVE

The *Data encoding* field is used to overwrite the data encoding (PI16) predefined in the transfer profile.

To preserve the predefined data encoding, do not make a data encoding selection or use the EL expression `${pesit.pi.dataEncoding}`. To use the EL expression, click the Edit icon (![](/Images/SecureTransport/EditIcon.png)) next to the select menu and enter the expression in field.

This configuration parameter corresponds to the **FCODE** parameter in Axway Transfer CFT.

### Record format

Record format selections are:

-   Variable
-   Fixed

In *START\_NEW* transfer mode, the **Record format** field is used to overwrite the record format (PI31) predefined in the transfer profile.

In *PRESERVE* transfer mode, the **Record format** field defines PI31. It can be an empty value, EL expression `${pesit.pi.recordFormat}`, or a numeric value. When the **Record format** field is empty and the file was originally received over PeSIT, the Record format (PI31) is preserved from the original file transfer. If file is received over a different protocol, the Record format (PI31) is preserved from the transfer profile.

This configuration parameter corresponds to the **FRECFM** parameter in Axway Transfer CFT.

### Record length

In *START\_NEW* transfer mode, the **Record length** field is used to overwrite the record format (PI32) predefined in the transfer profile.

In *PRESERVE* transfer mode, the **Record length** field defines PI32. It can be an empty value, EL expression `${pesit.pi.recordLength}`, or a numeric value. When the **Record length** field is empty and the file was originally received over PeSIT, the Record length (PI32) is preserved from the original file transfer. If file is received over a different protocol, the Record length (PI32) is preserved from the transfer profile.

This configuration parameter corresponds to the **FRECL** parameter in Axway Transfer CFT.

### File label

The *File label* field is used to overwrite the file label (PI37) predefined in the transfer profile.

To preserve the predefined file label, either leave the field empty or enter the EL expression `${pesit.pi.fileLabel}` in the field.

This configuration parameter corresponds to the **NFNAME** parameter in Axway Transfer CFT.

### Originator

The *Originator* field is used to overwrite the original sender (PI61) of the transfer.

To preserve the originator of the previous transfer, enter the EL expression `${pesit.pi.originalSenderID}.` in the field.

<span id="AR_SP_Originator"></span>To make a Store and Forward PeSIT transfer specify the originator and choose the intermediate partner (**IPART** parameter in Axway Transfer CFT) in the transfer site list.

> **Note:**
>
> Originator can only be changed when Store and Forward mode is set to START\_NEW.

### Final Destination

The *Final Destination* field is used to overwrite the final destination (PI62) of the transfer.

To preserve the final destination of the previous transfer, enter the EL expression `${pesit.pi.finalDestinationID}` in the field.

<span id="AR_SP_Final_Destination"></span>To make a Store and Forward PeSIT transfer specify the final destination and choose the intermediate partner (**IPART** parameter in Axway Transfer CFT) in the transfer site list.

> **Note:**
>
> Final destination can only be changed when Store and Forward mode is set to START\_NEW.

### User message

The *User message* field is used to overwrite the predefined user message (PI99) in the PeSIT transfer site. To preserve the predefined user message, either leave the field empty or enter the EL expression `${pesit.pi.serviceParam}` in the field.

This configuration parameter corresponds to the **PARM** parameter in Axway Transfer CFT.

<span id="Overwrit"></span>

## Overwrite upload folder

If Overwrite upload folder is selected, the value specified is used to overwrite the upload folder configured in the transfer site settings (if allowed in the transfer site).

> **Note:**
>
> The upload folder must be created on the target file system. Otherwise, the sending of the trigger file could fail.

> **Note:**
>
> The upload folder of a custom Pluggable Transfer Site cannot be overwritten.

An EL expression can be used to specify the new upload folder.

Example: You can access the first value of a given SSO attribute with name `attributeName` with the expression `${sso.attributes['attributeName'][0]}`.

 

<span id="Route"></span>

## Route files as

If *Route files as* is selected, the entry in the field overwrites *Send File As* property which is set in the transfer site. An EL expression can be used to specify a route files as name.

Examples:

-   New file name based on the current filename (since the transformation might have changed it):

    `${basename(currentfulltarget)}.sent`

-   New file name based on the original filename with a timestamp:

    `${basename(transfer.target)}.​${timestamp}​.${extension(transfer.target)}`

> **Note:**
>
> You can access the first value of a given SSO attribute with name attributeName with the expression
> ${sso.attributes\['attributeName'\]\[0\]}.

> **Note:**
>
> The path of the new file (if any) is stripped off and only the filename is left.

<span id="Send"></span>

## Send trigger file

If *Send trigger file* is selected, a designated trigger file is sent to the transfer site after successful routing of files. To designate the trigger file, name the trigger file, determine whether or not to send a trigger file for each transferred file, and create the trigger file content. To complete the configuration of the trigger file, select the trigger file destinations by specifying a destination account, selecting account transfer sites, selecting the transfer profile (if applicable), and determining whether or not to overwrite the upload folder.

> **Note:**
>
> The trigger file is created after the successful transfer of a file or files. The trigger file exists only in the sandbox folder. The trigger file is deleted right after it was successfully transferred to the trigger destination or destinations.

> **Note:**
>
> The Max number of parallel transfers and Retry settings are applied for both the data file and the trigger file.

### Trigger file name

The *Trigger file name* field is used to name the trigger file to be sent to the transfer site after the successful routing of file(s). EL expressions are supported.

Examples:

-   New file name based on the current filename (since the transformation might have changed it):

    `${basename(currentfulltarget)}.sent`

-   New file name based on the original filename with a timestamp:

    `${basename(transfer.target)}​.${timestamp}​.${extension(transfer.target)}`

-   You can access the first value of a given SSO attribute with the name `attributeName` with the expression `${sso.attributes['attributeName'][0]}`.

> **Note:**
>
> Send File as option, in the site used to send the trigger file, is ignored and the name of the trigger file remains unchanged. Though, other Post Transmission Settings, if any, are applied over the name of the trigger file.

### Send trigger file for each transferred file

If *Send trigger file for each transferred file* is selected, a trigger file is sent after each successful routing of a data file to the transfer site. If this option is not selected, one trigger file is sent after all transformed files are successfully routed to the transfer site.

> **Note:**
>
> If Send trigger file for each transferred file is not selected and the sending of one or more of the transformed files fails, the trigger file is not sent even though most of the files were successfully transferred.

### Trigger file content

The *Trigger file content* field is used to specify the content of the trigger file. EL expressions are supported.

If the content is not specified an empty (zero byte) trigger file is sent.

`\n\r` (CRLF) is used as a line separator for the content of the trigger file.

### Trigger files destinations

To specify a trigger file destinations, specify the destination account, select account transfer sites and transfer profile (if applicable), and determine whether or not to overwrite the upload folder.

#### Specify an account

The Specify an account field, is used to specify the account who holds information (transfer site) about the trigger destination. Either an account name, login name, or EL expression can be used to determine the recipient based on the environment information (such as filename).

The *Specify an account* field has auto-completion which shows a list of existing accounts containing the same search term.

Once an account is selected its transfer sites are populated in the select box. The population is only possible if the account name matches the login name of the user.

If an account name is unknown (for example, expression based) or the login name does not match the account name, its transfer sites are determined at runtime. Transfer sites can be expression based as well.

Account template names should not be used in this field. The transfer sites which belong to the template will be populated but the step will fail. When using account templates, the value of this field should be the login name.

> **Note:**
>
> Auto-completion will suggest account names and user (login) names.

#### Account transfer sites

Transfer sites can either be existing transfer sites retrieved from the account selected or expression based ones.

To use an expression, click the Edit icon (![](/Images/SecureTransport/EditIcon.png)) next to the select box and enter the expression in field.

Expression for specifying the sites allows both EL and the wild card symbols - '\*' and '?'.

Example:

If expression like `${account.name}-HTTP-*` is specified this would match all transfer sites (within the account selected) such as:

`- jsmith-HTTP-Partner1`

`- jsmith-HTTP-Partner2`

`- etc.`

> **Note:**
>
> Only transfer sites with proper access level will be listed. For more details see Transfer sites.

#### Transfer profile

Transfer profile property is used only if the transfer site is of type PeSIT. Otherwise, it is ignored.

When the transfer profile is specified by using an EL expression there are three possible cases:

1.  EL expression does not match any account transfer profiles - the default transfer profile is used then.
2.  EL expression matches more than one transfer profile - the default transfer profile is used.
3.  EL expression matches exactly one transfer profile - the matched transfer profile is used.

The transfer profile can be selected from the listed ones or an EL expression can be used. To use an expression, click the Edit icon (![](/Images/SecureTransport/EditIcon.png)) next to the select menu and enter the expression in field.

#### Overwrite upload folder

If Overwrite upload folder is selected, the specified value is used to overwrite the upload folder configured in the transfer site settings (if allowed in the transfer site).

An EL expression can be used to specify the new upload folder.

> **Note:**
>
> The upload folder must be created on the target file system. Otherwise, the sending of the trigger file could fail.

### Max number of parallel transfers

The entry in the *Max number of parallel transfers* field determines the maximum number of parallel transfers for each route used for both the data file and trigger file, if configured. The default number of maximum parallel transfers is 4 which means you cannot have more than 4 concurrent transfer connections at a time. Note that files are processed one by one but are published in bulk to the configured transfer sites.

No retries are triggered if the reason for the failure is permanent (for example, the wrong credentials are specified in the transfer site being used).

<span id="Retry"></span>

## Retry settings

The retry settings include setting the maximum number of retries, setting the sleep time between retries, and setting the sleep increment between retries. Those settings are used for both the data file and trigger file, if configured.

### Max number of retries

The entry in the *Max Number of Retries* field determines the maximum of transfer retries. The default maximum number of retries is 5.

### Sleep between retries

The entry in the *Sleep Between Retries* field determines the sleep time in milliseconds between retries. The default sleep time between retries is 3000.

### Sleep increment between retries

The entry in the *Sleep Increment Between Retries* field determines the increment time in milliseconds between retries. The default sleep increment time between retries is 2000.

<span id="Post"></span>

## Post Routing Action

The post routing action selections determine what actions occur once the route step is completed. The post routing actions include deleting and archiving files.

> **Note:**
>
> Post routing actions are not performed over the trigger file, since this file has already been deleted except when File Archiving is enabled. When File Archiving is enabled, the trigger file will be archived as a normal file. For information on the global configuration of File Archiving (including enabling File Archiving), refer to File archiving global configuration.

> **Note:**
>
> The post routing actions are executed in the sandbox folder only.

> **Note:**
>
> Post routing actions are executed for successfully transferred data files only. If the transfer fails (permanently or reaches its maximum number of retries), post routing actions are not executed except when File Archiving is enabled. When File Archiving is enabled, the selected Archive Files On Failure action will occur. For information on the global configuration of File Archiving (including enabling File Archiving), refer to File archiving global configuration.

> **Note:**
>
> The output file names will be the same as the input file names. To change the file names use a Rename transformation step. To configure a Rename transformation step, refer to Rename.

### Delete files after step is complete

If *Delete files after step is complete* is selected, the files processed by the route step are deleted.

### Archive files on success

The *Archive Files On Success* selection determines how the files are backed up in the configured archive folder if the step execution succeeds.

-   If **Default** is selected, the files will archive the files based on the account configuration.
-   If **Enable** is selected, the files will always be archived.
-   If **Disable** is selected, the files will not be archived.

> **Note:**
>
> The Archive Files On Success selection will only be visible if File Archiving is enabled. For information on the global configuration of File Archiving (including enabling File Archiving), refer to File archiving global configuration.

> **Note:**
>
> In order for the administrator to be able to resubmit successful outbound transfers initiated by the Send To Partner step, you must have the Archive Files On Success set to enabled.

### Archive files on failure

The *Archive Files On Failure* selection determines how the files are backed up in the configured archive folder if the step execution fails.

-   If **Default** is selected, the files will archive the files based on the account configuration.
-   If **Enable** is selected, the files will always be archived.
-   If **Disable** is selected, the files will not be archived.

> **Note:**
>
> The Archive Files On Failure selection will only be visible if File Archiving is enabled. For information on the global configuration of File Archiving (including enabling File Archiving), refer to File archiving global configuration.

> **Note:**
>
> In order for the administrator to be able to resubmit failed outbound transfers initiated by the Send To Partner step, you must have the Archive Files On Success set to enabled.
