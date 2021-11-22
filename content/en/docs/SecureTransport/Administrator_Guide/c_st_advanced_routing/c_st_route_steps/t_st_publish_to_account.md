{
    "title": "Publish To Account",
    "linkTitle": "Publish To Account",
    "weight": "230"
}The Publish To Account routing step enables publishing files to a specified account as part of a route. To add Publish To Account to a Route Package Template or Route Package take the following steps:

1.  Designate file filtering.
2.  Determine whether or not to proceed with route execution on step failure.
3.  Enter and select the target settings.
4.  Determine post routing actions.

> **Note:**
>
> Steps 1 and 3 are mandatory. All other steps are optional.

> **Note:**
>
> Publish To Account is used only to publish files to accounts which belong to the same SecureTransport Server. The administrator is not able to publish files to accounts managed by other products including other instances of SecureTransport Server. To avoid this restriction the administrator could use a Send To Partner routing step instead. For more information refer to Send To Partner.

The following topics provide detailed Publish To Account route step configuration information:

-   <a href="#File" class="MCXref xref">Input Files</a>
-   <a href="#Proceed" class="MCXref xref">Proceed with route execution on step failure</a>
-   <a href="#Target" class="MCXref xref">Target Settings</a>
-   <a href="#Post" class="MCXref xref">Post Routing Action</a>

**Related topic:**

-   <a href="../t_st_send_to_partner" class="MCXref xref">Send To Partner</a>

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

## Proceed with route execution on step failure

If *Proceed with route execution on step failure* is checked, the route execution continues even if the step execution fails.

<span id="Target"></span>

## Target Settings

The target settings consists of selecting the account and the folder location to which to publish the designated files. The settings also include determining the name of the published file and selecting how to handle collisions.

### Account

This is the account to publish the file(s) to. You can specify either an account name or use an EL expression to determine the recipient based on the environment information (such as filename). If no account with such name exists SecureTransport will try to match an account by its login name (either virtual or external user).

The *Account* field has auto-completion which shows a list of existing accounts containing the same search term.

> **Note:**
>
> Auto-completion will suggest account names and user (login) names.

> **Note:**
>
> Publish To Account could publish files only to internal (virtual, unlicensed or service) users or external ones using an existing account template.

> **Note:**
>
> In order to publish files to an external account (real, LDAP account, or SiteMinder), the administrator must specify the login name of this account (not the name of the account template which will be used).

> **Note:**
>
> You can access the first value of a given SSO attribute with name attributeName with the expression ${sso.attributes\['attributeName'\]\[0\]}.

### Folder

This is the folder in the designated account to publish the file to. If the folder doesn't exist, it is automatically created. A folder name can be specified or an EL expression can be used to determine the folder based on the environment information. The folder name is a relative path to the home folder of the specified account.

> **Note:**
>
> A file will be successfully published to the specified folder only if the home folder of the designated account has a proper home folder access level. For more details see User accounts and Advanced Routing.

> **Note:**
>
> You can access the first value of a given SSO attribute with name attributeName with the expression ${sso.attributes\['attributeName'\]\[0\]}.

### Publish file as

This is the name of the published file. If this field is not empty, the file is published with the specified name. An EL script can also be used to specify a file name.

Examples:

-   New file name based on the current filename (since the transformation might have change it):

    `${basename(currentfulltarget)}.sent`

-   New file name based on the original filename with a timestamp:

    `${basename(transfer.target)}​.${timestamp}​.${extension(transfer.target)}`

-   You can access the first value of a given SSO attribute with name `attributeName` with the expression `${sso.attributes['attributeName'][0]}`.

> **Note:**
>
> The path of the new file (if any) is stripped off and only the filename is left.

### Collision settings

The collision setting determines the course of action to take in the event of duplicate file names. The possible collision settings are:

-   Fail operation
-   Replace existing file
-   Rename existing file
-   Use a different file name to publish the file
-   Append to existing file

#### Replace existing file

With replace of existing file, there is a dedicated configuration option `AdvancedRouting.PublishToAccount.allowSelfOverwrite`. It allows (or disallows) the overwrite of files with the same name when source and destination is the same. Note that this option is available with {{< SecureTransport/componentshortname  >}} 5.5-20210527 Update and later.

#### Rename existing file

Renames the existing file with the following pattern:

If file name is `myFile.txt`, after renaming the file name is `myFile (old copy 1).txt`

If this file already exists, after renaming the file name is `myFile (old copy 2).txt`

> **Note:**
>
> If the file doesn't have an extension, the name transformation is the same but without the extension - myFile (old copy 1).

#### Use different file name to publish the file

Uses a different name to publish the file. The name is derived from the name specified in the *Publish file as* field as follows:

If file name is `myFile.txt`, after renaming the file name is `myFile (new copy 1).txt`

If this file already exists, after renaming the file name is `myFile (new copy 2).txt`

> **Note:**
>
> If the file doesn't have an extension, the name transformation is the same but without the extension - myFile (new copy 1).

#### Trigger target subscription actions

This option allows administrators to define the behavior if the target folder is a subscription or other special folder.

When deselected (default) no further processing in the target folder is done.

When selected, the post processing actions defined in the target folder are executed.

#### Disable auto-create target folder

This option allows the administrators to disable the automatic creation of a target folder. Thе checkbox is deselected by default. When the option is selected and a target folder does not exist, it will not be created upon step execution and will result in step failure.

<span id="Post"></span>

## Post Routing Action

If *Delete files after step is complete* is selected, the files processed by the route step are deleted.

> **Note:**
>
> The output file names will be the same as the input file names. To change the file names use a Rename transformation step. To configure a Rename transformation step, refer to Rename.
