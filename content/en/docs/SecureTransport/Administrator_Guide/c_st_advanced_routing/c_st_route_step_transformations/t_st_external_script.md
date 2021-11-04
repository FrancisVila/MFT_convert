{
    "title": "External Script",
    "linkTitle": "External Script",
    "weight": "270"
}> **Note:**
>
> The External Script transformation does not function with repository encryption.

The External Script transformation step enables adding the execution of external script as part of a route. To add an External Script transformation step to a Route Package Template take the following steps:

1.  Determine whether or not to proceed with route execution on step failure.
2.  Select the external script path.
3.  Determine whether or not to log the external script's standard output to the server log.
4.  Select whether or not to run scripts as the root administrator.

> **Note:**
>
> Step 2 is mandatory. All other steps are optional.

The following topics provide configuration details for the External Script transformation step:

-   <a href="#Proceed" class="MCXref xref">Proceed with route execution on step failure</a>
-   <a href="#Script" class="MCXref xref">Script Settings</a>
-   <a href="#Logging" class="MCXref xref">Logging Settings</a>
-   <a href="#Logging" class="MCXref xref">Logging Settings</a>

**Related topics:**

-   <a href="../t_st_pgp_encryption" class="MCXref xref">PGP Encryption</a>
-   <a href="../t_st_pgp_decryption" class="MCXref xref">PGP Decryption</a>
-   <a href="../t_st_compress" class="MCXref xref">Compress</a>
-   <a href="../t_st_decompress" class="MCXref xref">Decompress</a>
-   <a href="../t_st_line_ending" class="MCXref xref">Line Ending</a>

<!-- -->

-   <a href="../t_st_charset_conversion" class="MCXref xref">Encoding Conversion</a>
-   <a href="../t_st_replace" class="MCXref xref">Characters Replace</a>
-   <a href="../t_st_line_padding" class="MCXref xref">Line Padding</a>
-   <a href="../t_st_file_folding" class="MCXref xref">Line Folding</a>
-   <a href="../t_st_line_truncating" class="MCXref xref">Line Truncating</a>
-   <a href="../t_st_rename" class="MCXref xref">Rename</a>

<span id="Proceed"></span>

## Proceed with route execution on step failure

If *Proceed with route execution on step failure* is checked, the route execution continues even if the step execution fails.

<span id="Script"></span>

## Script Settings

The script settings consist of the selecting the external script path.

### External script path

The external script path is an absolute path to external script.

Example script expressions:

-   For \*nix environment:  
    `/usr/bin/env bash -c "${FILEDRIVEHOME}/bin/agents/example.sh ${date('yyyyMMdd')} ${currentfulltarget} ${transfer.transferredBytes} ${routing.originalFiles}"`
-   For Windows environment:  
    `cmd /c ${FILEDRIVEHOME}\bin\agents\example.bat ${date('yyyyMMdd')} ${currentfulltarget} ${transfer.transferredBytes} ${routing.originalFiles}`

<span id="Logging"></span>

## Logging Settings

The logging settings consists of determining whether or not the external script's standard output is logged to the server log.

### Log script's standard output to Server log

If *Log script's standard output to Server log* is selected, the external script's standard output is logged to the server log.

### Run as root for external script

External script steps can be configured to run scripts as a root administrator for each individual step instance.

When running scripts as a system superuser, scripts have the ability to execute the full scope of commands, thus exposing the system in the hands of the writer of the script.

General recommendation is to avoid using this option or to use it with caution.

By default, the option is unchecked.

For more information, refer to the SecureTransport Security Guide.

> **Note:**
>
> Running scripts as root is not default behavior. Enabling it makes possible running commands to which the routing step might not have permissions to execute otherwise.

> **Note:**
>
> This option is available to administrators with sufficient level of permission only. By default, master and account administrators can manage the option.For delegated administrator privileges, see Delegated administration.

> **Note:**
>
> When running scripts from the external script routing step, the execution environment might not have full scope of environment variables initialized. The script writer is responsible to properly export and initialize the necessary environment in the script itself before the actual script execution specifics.

> **Note:**
>
> The option is applicable only for root and non-Windows deployments.