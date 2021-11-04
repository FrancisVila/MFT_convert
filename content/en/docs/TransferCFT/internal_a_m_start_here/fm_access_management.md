{
    "title": "Access Management using Flow Manager",
    "linkTitle": "Flow Manager access management ",
    "weight": "150"
}You can use <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> to define and control Transfer CFT access management as described in the following sections.

How it works

If you have opted to use the <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> for <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> access management, after configuring both <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> and <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span>:

1.  A user logs in via the <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> UI, CFTUTIL, or other.
2.  A login request is sent to <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span>.
3.  If the login is successful, <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> returns the list of roles for the user.
4.  The user login is complete. Transfer CFT then stores these roles in the cache and applies them accordingly. The information about this user is stored in the cache and is only updated when a new login is performed.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>All role and permission definitions are stored in CFTPARM.         </td>
      </tr>
   </tbody>
</table>

However, if you are an <span class="code">am.superuser</span> user, <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> does not check your access for resources, and permissions are granted unconditionally. Additionally, it is useful to note that if you define a service account during <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> installation, this user is automatically added to the UCONF <span class="code">am.superuser</span> parameter's list.

See also, <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> *Security Guide &gt;*[Predefined roles](https://docs.axway.com/bundle/FlowManager_20_allOS_en_HTML5/page/predefined_roles.html) and [Predefined privileges](https://docs.axway.com/bundle/FlowManager_20_allOS_en_HTML5/page/predefined_privileges.html) (requires account login).

<img src="/Images/TransferCFT/cg_am.jpg" class="mediumWidth" />

Limitations

-   <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span> ROLES are stored on <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span> in upper case. This means that if you create roles **XXX** and **Xxx** on <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span>, there is only one ROLE in <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span>, which is <span class="code">ID=XXX</span>.

<span id="Using"></span>

## Using roles and privileges

The <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> method of access management impacts two <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> objects that are defined in the CFTPARM database: roles (CFTROLE) and privileges (CFTPRIV). You assign these roles and privileges in <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span>, which are then deployed on Transfer CFT.

Conversely, you can create roles and privileges locally in Transfer CFT, as you do with other objects.

### Using CFTROLE

A role is a general profile that can be associated with a user. A role is based on one or more privileges, and a privilege is based on a resource. There are two types of roles: predefined and user-defined. Predefined roles are available by default to assign to users.

You can assign users to one or more roles. Typically, users with multiple roles have more privileges than users with fewer roles.

Examples of roles can be ADMINISTRATOR, PARTNER MANAGER, IT MANAGER, and so on.

<table>
   <th>
      <tr>
<th><p>Field</p>         </th>
<th><p>Type</p>         </th>
<th><p>Comment</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>id</p>         </td>
         <td><p>String32</p>         </td>
         <td><p>Role identifier</p>         </td>
      </tr>
      <tr>
         <td><p>comment</p>         </td>
         <td><p>String80</p>         </td>
         <td><p>Comment</p>         </td>
      </tr>
      <tr>
         <td><p>privs[]</p>         </td>
         <td><p>List of String32</p>         </td>
         <td><p>List of privileges associated to this role (1 to 128)</p>         </td>
      </tr>
   </tbody>
</table>

Example of CFTROLE in a configuration file:



    CFTROLE      ID          = 'Application',
                 COMMENT     = 'My comments',
                 PRIVS       = ( 'SERVICE:UI_CONNECT',
                                 'MYPRIV1',
                                 'CONFIGURATION:CFTCOM_VIEW',
                                 'CONFIGURATION:CFTPARM_VIEW',
                                 'CONFIGURATION:CFTPART_VIEW',
                                 'CONFIGURATION:CFTDEST_VIEW',
                                 'CONFIGURATION:CFTSEND_VIEW',
                                 'CONFIGURATION:CFTRECV_VIEW',
                                 'CONFIGURATION:CFTLOG_VIEW',
                                 'FILTER:CATALOG_ALL',
                                 'FILTER:LOG_ALL',
                                 'FILE_VIEW'),
                 ORIGIN      = 'CFTUTIL',
                 MODE        = 'REPLACE'

### Using CFTPRIV

Privileges give users authorization to access and perform actions in the user interface. Examples of actions include CREATE, DELETE, VIEW, EDIT (use \* to assign all actions).

<table>
   <th>
      <tr>
<th><p>Field</p>         </th>
<th><p>Type</p>         </th>
<th><p>Comment</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>id</p>         </td>
         <td><p>String32</p>         </td>
         <td><p>Privilege identifier</p>         </td>
      </tr>
      <tr>
         <td><p>comment</p>         </td>
         <td><p>String80</p>         </td>
         <td><p>Comment</p>         </td>
      </tr>
      <tr>
         <td><p>resource</p>         </td>
         <td><p>String32</p>         </td>
         <td><p>Resource on which this privilege applies</p>         </td>
      </tr>
      <tr>
         <td><p>actions</p>         </td>
         <td><p>List of String32</p>         </td>
         <td><p>Actions authorized on the resource (1 to 16 actions)</p>         </td>
      </tr>
      <tr>
         <td><p>condition</p>         </td>
         <td><p>String256</p>         </td>
         <td><p>Condition to check for authorizing (<a href="#Specifyi">see below</a>)</p>         </td>
      </tr>
   </tbody>
</table>

Example of CFTPRIV in a configuration file:



    CFTPRIV      ID          = 'MYPRIV1',
                COMMENT     = 'My comment',
                 RESOURCE    = 'TRANSFER',
                 ACTIONS     = ( 'CREATE' , 'DELETE', 'VIEW', 'EDIT', 'CANCEL', 'RESUME', 
                                'PAUSE', 'EXECUTE', 'SUBMIT', 'END' ),
                 CONDITION   = '',
                 ORIGIN      = 'CFTUTIL',
                 MODE        = 'REPLACE'

<span id="Specifyi"></span>

### Specifying conditions

Conditions allow you to assign finer control on resources and actions by specifying a logical condition that must be true to authorize the action.

Examples

In these examples <span class="code">PART </span>and <span class="code">ID </span>are properties of the resource being checked. As you can see, you can use parenthesis and logical operators <span class="code">&&</span> (AND) and <span class="code">||</span> (OR).



    PART=="PARIS" && ID=="IDFDEF"
    (PART=="PARIS" || PART==”NEWYORK”) && ID~="IDF*"

Comparison operators include:

-   == : equals
-   != : not equal
-   ~= : matches (use \* and ? for jokers)
-   /= : not matching (use \* and ? for jokers)
-   &lt; : inferior to
-   &gt; : superior to
-   &lt;= : inferior or equal to
-   &gt;= :superior or equal to

### Resource properties in privileges

The following table is an exhaustive list of all properties for all resources. These properties are available regardless of the action to be checked. However, if a resource has no properties, setting a condition for it has no impact.

<table>
   <th>
      <tr>
<th><p>Resource</p>         </th>
<th><p>Actions</p>         </th>
<th><p>Properties</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>CONFIGURATION:PKICER</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT,  ACTIVATE, DEACTIVATE</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:PKIENTITY</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT,  ACTIVATE, DEACTIVATE</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:PKIKEY</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT,  ACTIVATE, DEACTIVATE</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTPARM</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTNET</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTPROT</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION: CFTSEND</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION: CFTSENDI <sup>(1)</sup></p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION: CFTRECV</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTAUTH</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTXLATE</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTLOG</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTCAT</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTCOM</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTACCNT</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTEXIT</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTIDF</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTFOLDER</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT,  ACTIVATE, DEACTIVATE</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTETB</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTAPPL</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTSSL</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTCRON</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT,  ACTIVATE, DEACTIVATE, RELOAD</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTPART</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT,  ACTIVATE, DEACTIVATE, TURN</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTDEST</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTTCP</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION:CFTUCONF</p>         </td>
         <td><p>DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>SERVICE:BATCH <sup>(2)</sup></p>         </td>
         <td><p>EXECUTE</p>         </td>
         <td><p>ID, FNAME</p>         </td>
      </tr>
      <tr>
         <td><p>SERVICE:UI <sup>(3)</sup></p>         </td>
         <td><p>CONNECT</p>         </td>
         <td><p>TYPE, ID, GROUP</p>         </td>
      </tr>
      <tr>
         <td><p>SERVICE:BATCH</p>         </td>
         <td><p>EXECUTE</p>         </td>
         <td><p>ID, FNAME</p>         </td>
      </tr>
      <tr>
         <td><p>SERVICE:CATALOG</p>         </td>
         <td><p>PURGE</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>SERVICE:LOG</p>         </td>
         <td><p>SWITCH</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>SERVICE:ACCOUNT</p>         </td>
         <td><p>SWITCH</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>SERVICE:CFTSRV</p>         </td>
         <td><p>STARTUP, SHUTDOWN</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>SERVICE:COM</p>         </td>
         <td><p>DELETE, VIEW</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>COMMAND:EXTRACT</p>         </td>
         <td><p>EXECUTE</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>COMMAND:MQUERY</p>         </td>
         <td><p>EXECUTE</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>COMMAND:TURN</p>         </td>
         <td><p>EXECUTE</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>COMMAND:CFTSUPPORT</p>         </td>
         <td><p>EXECUTE</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>TRANSFER</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT, CANCEL, RESUME, PAUSE, EXECUTE, SUBMIT, END, VIEWIFLE, EDITFILE, DELETEFILE</p>         </td>
         <td><p>IDAPPL, ID, PART, SPART, RPART, IPART, TYPE, DIRECT, MODE, FNAME, MESSAGE, SUSER, RUSER, SAPPL, RAPPL, NFNAME</p>         </td>
      </tr>
      <tr>
         <td><p>AM:RIGHTS <sup>(4)</sup></p>         </td>
         <td><p>VIEW_SELF, VIEW_OTHERS</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>FILTER:CATALOG</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>FILTER:LOG</p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>ID</p>         </td>
      </tr>
      <tr>
         <td><p>FILE <sup>(5)</sup></p>         </td>
         <td><p>CREATE, DELETE, VIEW, EDIT</p>         </td>
         <td><p>FNAME</p>         </td>
      </tr>
      <tr>
         <td><p>URL <sup>(6)</sup></p>         </td>
         <td><p>VIEW</p>         </td>
         <td><p>URL</p>         </td>
      </tr>
   </tbody>
</table>

1.  Manage implicit SEND object definitions.
2.  Manage batch files.
3.  Connect to user interface.
4.  Rights from PassPort AM.
5.  Manage Transfer CFT file definition objects.
6.  Manage file name definitions.

## Use cases

### Restrict user to a specific partner and IDF

As an Administrator, you want to authorize a user to work only with a given partner and a specific IDF.

This user can preform the following operations only with an IDF name equal to "MYIDF" and the PART name equal to "MYPART":

-   View transfers (LISTCAT and DISPLAY)
-   Create transfers
-   Delete transfers
-   Cancel transfers
-   Resume transfers
-   Execute transfers

In this use case, you assign the user a role that references a privilege having these characteristics:

-   RESOURCE = 'TRANSFER',
-   ACTIONS = ( ‘VIEW’, ‘CREATE’, ‘DELETE’, ‘CANCEL', 'RESUME', ‘EXECUTE’ ),
-   CONDITION = ' IDF=="MYIDF" && PART=="MYPART" '

The following is an example of the <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> configuration for this use case (the ROLE must exist in <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span>, and be available for required users):



    CFTROLE      ID          = 'TRANSFER-ROLE',
                 COMMENT     = '',
    /*           ALIASES     = ( ) ,*/
                 PRIVS       = ( 'PRIV-XFER-SPE',
                                  'PRIV-CONN-INTERFACES',
                                  'CONFIGURATION:CFTCOM_VIEW',
                                  'CONFIGURATION:CFTPARM_VIEW',
                                  'FILTER:CATALOG_ALL',
                                  'FILTER:LOG_ALL',
                                  'FILE_VIEW',
                                  'CONFIGURATION:PKICER_VIEW',
                                  'CONFIGURATION:PKIENTITY_VIEW',
                                   'CONFIGURATION:PKIKEY_VIEW',
                                  'CONFIGURATION:CFTPARM_VIEW',
                                  'CONFIGURATION:CFTNET_VIEW',
                                  'CONFIGURATION:CFTPROT_VIEW',
                                  'CONFIGURATION:CFTSEND_VIEW',
                                  'CONFIGURATION:CFTSENDI_VIEW',
                                  'CONFIGURATION:CFTRECV_VIEW',
                                  'CONFIGURATION:CFTAUTH_VIEW',
                                  'CONFIGURATION:CFTXLATE_VIEW',
                                  'CONFIGURATION:CFTLOG_VIEW',
                                  'CONFIGURATION:CFTCAT_VIEW',
                                  'CONFIGURATION:CFTCOM_VIEW',
                                  'CONFIGURATION:CFTACCNT_VIEW',
                                  'CONFIGURATION:CFTEXIT_VIEW',
                                  'CONFIGURATION:CFTIDF_VIEW',
                                  'CONFIGURATION:CFTFOLDER_VIEW',
                                  'CONFIGURATION:CFTETB_VIEW',
                                  'CONFIGURATION:CFTAPPL_VIEW',
                                  'CONFIGURATION:CFTSSL_VIEW',
                                  'CONFIGURATION:CFTCRON_VIEW',
                                  'CONFIGURATION:CFTPART_VIEW',
                                  'CONFIGURATION:CFTDEST_VIEW',
                                  'CONFIGURATION:CFTTCP_VIEW',
                                  'CONFIGURATION:CFTUCONF_VIEW',
                                  'SERVICE:COM_VIEW',
                                  'AM:RIGHTS_VIEW_SELF'),
                  MODE        = 'REPLACE'
     
    CFTPRIV       ID          = 'PRIV-XFER-SPE',
                  COMMENT     = 'PRIV limits transfers - no delete condition',
                  RESOURCE    = 'TRANSFER',
                  ACTIONS     = ( 'CREATE',
                                  'RESUME',
                                  'VIEW',
                                  'CANCEL',   
                                   'PAUSE',
                                  'EXECUTE'),
                  CONDITION   = ' IDF=="MYIDF" && PART=="MYPART" ',
                  ORIGIN      = 'CFTUTIL',
                  MODE        = 'REPLACE'

### Add an administrator role

As an administrator, you want to assign a role equivalent to classic 'Administrator' role to a user, but I would like to restrict access in the UI (Copilot or CFTUI) to a given Transfer CFT Name or a Group of Transfer CFTs, based on the Transfer CFT instance ID and instance group.

In this use case, you assign the user role that refers to a privilege having these characteristics:

-   RESOURCE = SERVICE:UI,
-   ACTIONS = ( 'CONNECT' ),
-   CONDITION = ' GROUP=="PRODUCTION" && ID~=''CFT-PROD-ITEM\*'' '

A user with this privilege can only connect to a Transfer CFT server whose UCONF <span class="code">cft.instance\_group</span> value is set to PRODUCTION, and whose <span class="code">cft.instance\_id</span> value begins with CFT-PROD-ITEM.

The following is an example of the <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> configuration for this use case (the ROLE must exist in <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span>, and be available for required users):



    CFTROLE      ID          = 'ADMIN_ROLE',
                  COMMENT     = 'Administrator role for Production Transfer CFT Windows',
                  PRIVS       = ('PRIV-CONN-INTERFACES',               

                                  'AM:RIGHTS_VIEW_ALL',
                                  'CONFIGURATION:PKICER_ALL',
                                  'CONFIGURATION:PKIENTITY_ALL',
                                  'CONFIGURATION:PKIKEY_ALL',
                                  'CONFIGURATION:CFTPARM_ALL',
                                  'CONFIGURATION:CFTNET_ALL',
                                  'CONFIGURATION:CFTPROT_ALL',
                                  'CONFIGURATION:CFTSEND_ALL',
                                  'CONFIGURATION:CFTSENDI_ALL',
                                  'CONFIGURATION:CFTRECV_ALL',
                                  'CONFIGURATION:CFTAUTH_ALL',
                                  'CONFIGURATION:CFTXLATE_ALL',
                                  'CONFIGURATION:CFTLOG_ALL',
                                  'CONFIGURATION:CFTCAT_ALL',
                                  'CONFIGURATION:CFTCOM_ALL',
                                   'CONFIGURATION:CFTACCNT_ALL',
                                  'CONFIGURATION:CFTEXIT_ALL',
                                  'CONFIGURATION:CFTIDF_ALL',
                                  'CONFIGURATION:CFTFOLDER_ALL',
                                  'CONFIGURATION:CFTETB_ALL',
                                  'CONFIGURATION:CFTAPPL_ALL',
                                  'CONFIGURATION:CFTSSL_ALL',
                                  'CONFIGURATION:CFTCRON_ALL',
                                  'CONFIGURATION:CFTPART_ALL',
                                   'CONFIGURATION:CFTDEST_ALL',
                                  'CONFIGURATION:CFTROLE_ALL',
                                  'CONFIGURATION:CFTPRIV_ALL',
                                  'CONFIGURATION:CFTTCP_ALL',
                                   'CONFIGURATION:CFTUCONF_ALL',
                                  'SERVICE:CATALOG_PURGE',
                                  'SERVICE:LOG_SWITCH',
                                  'SERVICE:ACCOUNT_SWITCH',
                                  'SERVICE:BATCH_EXECUTE',
                                   'SERVICE:CFTSRV_ALL',
                                  'SERVICE:COM_ALL',
                                  'TRANSFER_ALL',
                                  'FILTER:CATALOG_ALL',
                                  'FILTER:LOG_ALL',
                                  'FILE_ALL',
                                  'URL_VIEW',
                                  'COMMAND:EXTRACT_ALL',
                                  'COMMAND:MQUERY_ALL',
                                  'COMMAND:TURN_ALL',
                                  'COMMAND:CFTSUPPORT_ALL'),
                  MODE        = 'REPLACE'
     
    CFTPRIV      ID          = 'PRIV-CONN-INTERFACES',
                  COMMENT     = 'PRIV LIMITs the connection for a given Transfer CFT name',
                 RESOURCE    = 'SERVICE:UI',
                 ACTIONS     = ( 'CONNECT'),
                 CONDITION   = 'GROUP=="PRODUCTION" && ID~="CFT-PROD-ITEM*"',  
                 MODE        = 'REPLACE'
     

A user with this privilege can only connect to a Transfer CFT server whose UCONF <span class="code">cft.instance\_group</span> value is set to <span class="code">PRODUCTION</span>, and whose <span class="code">cft.instance\_id</span> value begins with <span class="code">CFT-PROD-ITEM</span>.
