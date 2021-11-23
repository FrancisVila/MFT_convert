{
    "title": "FTP SITE META command",
    "linkTitle": "FTP SITE META command",
    "weight": "260"
}{{< SecureTransport/componentshortname  >}} has added support for a new command - SITE META. The command is part of the already existing SITE commands and provides capabilities to store user-specific information as metadata over the FTP protocol. It does not comply with any RFC documents and has a generic syntax.

The command accepts input in the format of key - value pairs. The supplied information is stored in the FTP session and is available until the session finishes or times out. For files uploaded during the same session, the provided information will be stored as file metadata attributes. The information can be evaluated at a later point for each file.

This way, the SITE META input could be used for defining routing rules for server-initiated transfers. For file metadata persistence specifics, see [Subscription flow attributes and FTP related attributes](#Subscrip).

> **Note:**
>
> To save the SITE META attributes for a file, the command execution and the file upload must happen within one session. Sharing attributes between different FTP sessions is not supported.

## FTP SITE META command syntax

The command accepts arguments in the format of key-value pairs. Everything beyond the META will be considered as a command argument. The format follows the pattern:


    SITE META <key>=<value>

The commands supports multiple arguments as well:


    SITE META <key1>=<value1>;<key2>=<value2>;<key3>=<value3>

Supplying same key names with different values will result in overwriting the previous values with the latest one.

> **Note:**
>
> The “=” and ‘;’ are considered special symbols: - the semicolon sign (‘;’) is used to delimit the different pairs,- the equals sign (“=”) splits the key name from its value. If using them as part of the payload, escaping is required. They must be preceded by “\\” or \\\\, depending on the manner how FTP clients accept command arguments.

When a file is uploaded using a common session, the commands arguments are stored as part of the file meta information. They are written in an existing namespace - the flow attributes user variables (*userVars*). For more information about flow attributes, see *Flow attributes* section in [Mail template commands and variables](../../t_st_mailtemplates/c_st_mail_template_commands_variables).

The command supports entering keys with empty values:


    SITE META <key1>=;<key2>=;

This will result in deleting existing flow attributes with the same key name (if any) for already existing files. For new files these attributes are discarded and will not be persisted.

> **Note:**
>
> The supplied key-value pairs are saved on the file system as metadata for each file. The information is stored in a serialized and readable format. We do not recommend storing any sensitive or confidential information.

## Evaluate SITE META user metadata

FTP meta information can be evaluated and used to define basic transfer flows for server-initiated transfers. Evaluation of those attributes is possible from the Advanced Routing Steps, Transfer Sites and Subscriptions for fields that support expression evaluation (marked with a yellow stripe).

Within the Routing steps, metadata that comes from the SITE META command, along with any other file flow attributes can be evaluated using:


    ${flow.attributes['userVars.<key>']}

When using transfer sites and subscriptions, the file flow attributes (both SITE META and subscription), the expression is:


    ${stenv['DXAGENT_FLOW_USERVARS.<KEY-in-upper-case>']}

<span id="Subscrip"></span>

## Subscription flow attributes and FTP related attributes

Key-value pairs from subscription properties and those from FTP SITE META share a common space and are all persisted as file attributes for each file (if any).

Uploading files in the subscription directory within an FTP session with SITE META commands, the subscription flow attribute settings will always take precedence.

For more information about flow attributes settings, see *Configure general settings* section in [Subscribe to Advanced Routing application](../../../c_st_advanced_routing/c_st_configuration/t_st_subscribe_advanced_routing_application).
