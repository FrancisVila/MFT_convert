{
    "title": "FTP SITE META command",
    "linkTitle": "FTP SITE META command",
    "weight": "270"
}SecureTransport has added support for a new command - SITE META. The command is part of the already existing SITE commands and provides capabilities to store user-specific information as metadata over the FTP protocol. It does not comply with any RFC documents and has a generic syntax.

The command accepts input in the format of key - value pairs. The supplied information is stored in the FTP session and is available until the session finishes or times out. For files uploaded during the same session, the provided information will be stored as file metadata attributes. The information can be evaluated at a later point for each file.

This way, the SITE META input could be used for defining routing rules for server-initiated transfers. For file metadata persistence specifics, see [Subscription flow attributes and FTP related attributes](#subscrip).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To save the SITE META attributes for a file, the command execution and the file upload must happen within one session. Sharing attributes between different FTP sessions is not supported.         </td>
      </tr>
</table>

## FTP SITE META command syntax

The command accepts arguments in the format of key-value pairs. Everything beyond the META will be considered as a command argument. The format follows the pattern:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>SITE META &lt;key&gt;=&lt;value&gt;         </td>
      </tr>
   </tbody>
</table>

The commands supports multiple arguments as well:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>SITE META &lt;key1&gt;=&lt;value1&gt;;&lt;key2&gt;=&lt;value2&gt;;&lt;key3&gt;=&lt;value3&gt;         </td>
      </tr>
   </tbody>
</table>

Supplying same key names with different values will result in overwriting the previous values with the latest one.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The “=” and ‘;’ are considered special symbols: <br/>- the semicolon sign (‘;’) is used to delimit the different pairs,<br/>- the equals sign (“=”) splits the key name from its value. <br/>If using them as part of the payload, escaping is required. They must be preceded by “\” or \\, depending on the manner how FTP clients accept command arguments.         </td>
      </tr>
</table>

When a file is uploaded using a common session, the commands arguments are stored as part of the file meta information. They are written in an existing namespace - the flow attributes user variables (*userVars*). For more information about flow attributes, see *Flow attributes* section in [Mail template commands and variables](../../t_st_mailtemplates/c_st_mail_template_commands_variables).

The command supports entering keys with empty values:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>SITE META &lt;key1&gt;=;&lt;key2&gt;=;         </td>
      </tr>
   </tbody>
</table>

This will result in deleting existing flow attributes with the same key name (if any) for already existing files. For new files these attributes are discarded and will not be persisted.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The supplied key-value pairs are saved on the file system as metadata for each file. The information is stored in a serialized and readable format. We do not recommend storing any sensitive or confidential information.         </td>
      </tr>
</table>

## Evaluate SITE META user metadata

FTP meta information can be evaluated and used to define basic transfer flows for server-initiated transfers. Evaluation of those attributes is possible from the Advanced Routing Steps, Transfer Sites and Subscriptions for fields that support expression evaluation (marked with a yellow stripe).

Within the Routing steps, metadata that comes from the SITE META command, along with any other file flow attributes can be evaluated using:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>${flow.attributes['userVars.&lt;key&gt;']}         </td>
      </tr>
   </tbody>
</table>

When using transfer sites and subscriptions, the file flow attributes (both SITE META and subscription), the expression is:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>${stenv['DXAGENT_FLOW_USERVARS.&lt;KEY-in-upper-case&gt;']}         </td>
      </tr>
   </tbody>
</table>

## <span id="Subscrip"></span>Subscription flow attributes and FTP related attributes

Key-value pairs from subscription properties and those from FTP SITE META share a common space and are all persisted as file attributes for each file (if any).

Uploading files in the subscription directory within an FTP session with SITE META commands, the subscription flow attribute settings will always take precedence.

For more information about flow attributes settings, see *Configure general settings* section in [Subscribe to Advanced Routing application](../../../c_st_advanced_routing/c_st_configuration/t_st_subscribe_advanced_routing_application).
