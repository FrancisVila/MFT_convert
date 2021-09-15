{
    "title": "Flow Manager access management ",
    "linkTitle": "Flow Manager access management ",
    "weight": "150"
}You can use Flow Manager to define and control Transfer CFT access management as described in the following sections.

How it works

If you have opted to use the Flow Manager for Transfer CFT access management, after configuring both Transfer CFT and Flow Manager:

1.  A user logs in via the Transfer CFT UI, CFTUTIL, or other.
2.  A login request is sent to Flow Manager.
3.  If the login is successful, Flow Manager returns the list of roles for the user.
4.  The user login is complete. Transfer CFT then stores these roles in the cache and applies them accordingly. The information about this user is stored in the cache and is only updated when a new login is performed.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">All role and permission definitions are stored in CFTPARM.         </td>
      </tr>
</table>

However, if you are an am.superuser user, Transfer CFT does not check your access for resources, and permissions are granted unconditionally. Additionally, it is useful to note that if you define a service account during Transfer CFT installation, this user is automatically added to the UCONF am.superuser parameter's list.

See also, Flow Manager *Security Guide &gt;*[Predefined roles](https://docs.axway.com/bundle/FlowManager_20_allOS_en_HTML5/page/predefined_roles.html) and [Predefined privileges](https://docs.axway.com/bundle/FlowManager_20_allOS_en_HTML5/page/predefined_privileges.html) (requires account login).

![](cg_am.jpg)

Limitations

-   Transfer CFT ROLES are stored on Transfer CFT in upper case. This means that if you create roles **XXX** and **Xxx** on Flow Manager, there is only one ROLE in Transfer CFT, which is ID=XXX.

## <span id="Using"></span>Using roles and privileges

The Flow Manager method of access management impacts two Transfer CFT objects that are defined in the CFTPARM database: roles (CFTROLE) and privileges (CFTPRIV). You assign these roles and privileges in Flow Manager, which are then deployed on Transfer CFT.

Conversely, you can create roles and privileges locally in Transfer CFT, as you do with other objects.

### Using CFTROLE

A role is a general profile that can be associated with a user. A role is based on one or more privileges, and a privilege is based on a resource. There are two types of roles: predefined and user-defined. Predefined roles are available by default to assign to users.

You can assign users to one or more roles. Typically, users with multiple roles have more privileges than users with fewer roles.

Examples of roles can be ADMINISTRATOR, PARTNER MANAGER, IT MANAGER, and so on.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Field</p>
</th>
         <th>
            <p>Type</p>
</th>
         <th>
            <p>Comment</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>id</p>
         </td>
         <td>
            <p>String32</p>
         </td>
         <td>
            <p>Role identifier</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>comment</p>
         </td>
         <td>
            <p>String80</p>
         </td>
         <td>
            <p>Comment</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>privs[]</p>
         </td>
         <td>
            <p>List of String32</p>
         </td>
         <td>
            <p>List of privileges associated to this role (1 to 128)</p>
         </td>
      </tr>
   </tbody>
</table>

Example of CFTROLE in a configuration file:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTROLE      ID          = 'Application',</p>
            <p>             COMMENT     = 'My comments',</p>
            <p>             PRIVS       = ( 'SERVICE:UI_CONNECT',</p>
            <p>                             'MYPRIV1',</p>
            <p>                             'CONFIGURATION:CFTCOM_VIEW',</p>
            <p>                             'CONFIGURATION:CFTPARM_VIEW',</p>
            <p>                             'CONFIGURATION:CFTPART_VIEW',</p>
            <p>                             'CONFIGURATION:CFTDEST_VIEW',</p>
            <p>                             'CONFIGURATION:CFTSEND_VIEW',</p>
            <p>                             'CONFIGURATION:CFTRECV_VIEW',</p>
            <p>                             'CONFIGURATION:CFTLOG_VIEW',</p>
            <p>                             'FILTER:CATALOG_ALL',</p>
            <p>                             'FILTER:LOG_ALL',</p>
            <p>                             'FILE_VIEW'),</p>
            <p>             ORIGIN      = 'CFTUTIL',</p>
            <p>             MODE        = 'REPLACE'</p>
         </td>
      </tr>
   </tbody>
</table>

### Using CFTPRIV

Privileges give users authorization to access and perform actions in the user interface. Examples of actions include CREATE, DELETE, VIEW, EDIT (use \* to assign all actions).

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Field</p>
</th>
         <th>
            <p>Type</p>
</th>
         <th>
            <p>Comment</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>id</p>
         </td>
         <td>
            <p>String32</p>
         </td>
         <td>
            <p>Privilege identifier</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>comment</p>
         </td>
         <td>
            <p>String80</p>
         </td>
         <td>
            <p>Comment</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>resource</p>
         </td>
         <td>
            <p>String32</p>
         </td>
         <td>
            <p>Resource on which this privilege applies</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>actions</p>
         </td>
         <td>
            <p>List of String32</p>
         </td>
         <td>
            <p>Actions authorized on the resource (1 to 16 actions)</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>condition</p>
         </td>
         <td>
            <p>String256</p>
         </td>
         <td>
            <p>Condition to check for authorizing (<a href="#specifyi">see below</a>)</p>
         </td>
      </tr>
   </tbody>
</table>

Example of CFTPRIV in a configuration file:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTPRIV      ID          = 'MYPRIV1',</p>
            <p>            COMMENT     = 'My comment',</p>
            <p>             RESOURCE    = 'TRANSFER',</p>
            <p>             ACTIONS     = ( 'CREATE' , 'DELETE', 'VIEW', 'EDIT', 'CANCEL', 'RESUME', </p>
            <p>                            'PAUSE', 'EXECUTE', 'SUBMIT', 'END' ),</p>
            <p>             CONDITION   = '',</p>
            <p>             ORIGIN      = 'CFTUTIL',</p>
            <p>             MODE        = 'REPLACE'</p>
         </td>
      </tr>
   </tbody>
</table>

### <span id="Specifyi"></span>Specifying conditions

Conditions allow you to assign finer control on resources and actions by specifying a logical condition that must be true to authorize the action.

Examples

In these examples PART and ID are properties of the resource being checked. As you can see, you can use parenthesis and logical operators && (AND) and || (OR).

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>PART=="PARIS" &amp;&amp; ID=="IDFDEF"</p>
            <p>(PART=="PARIS" || PART==”NEWYORK”) &amp;&amp; ID~="IDF*"</p>
         </td>
      </tr>
   </tbody>
</table>

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

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Resource</p>
</th>
         <th>
            <p>Actions</p>
</th>
         <th>
            <p>Properties</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>CONFIGURATION:PKICER</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT,  ACTIVATE, DEACTIVATE</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:PKIENTITY</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT,  ACTIVATE, DEACTIVATE</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:PKIKEY</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT,  ACTIVATE, DEACTIVATE</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTPARM</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTNET</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTPROT</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION: CFTSEND</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION: CFTSENDI <sup>(1)</sup></p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION: CFTRECV</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTAUTH</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTXLATE</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTLOG</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTCAT</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTCOM</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTACCNT</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTEXIT</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTIDF</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTFOLDER</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT,  ACTIVATE, DEACTIVATE</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTETB</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTAPPL</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTSSL</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTCRON</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT,  ACTIVATE, DEACTIVATE, RELOAD</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTPART</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT,  ACTIVATE, DEACTIVATE, TURN</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTDEST</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTTCP</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CONFIGURATION:CFTUCONF</p>
         </td>
         <td>
            <p>DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>SERVICE:BATCH <sup>(2)</sup></p>
         </td>
         <td>
            <p>EXECUTE</p>
         </td>
         <td>
            <p>ID, FNAME</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>SERVICE:UI <sup>(3)</sup></p>
         </td>
         <td>
            <p>CONNECT</p>
         </td>
         <td>
            <p>TYPE, ID, GROUP</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>SERVICE:BATCH</p>
         </td>
         <td>
            <p>EXECUTE</p>
         </td>
         <td>
            <p>ID, FNAME</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>SERVICE:CATALOG</p>
         </td>
         <td>
            <p>PURGE</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>SERVICE:LOG</p>
         </td>
         <td>
            <p>SWITCH</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>SERVICE:ACCOUNT</p>
         </td>
         <td>
            <p>SWITCH</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>SERVICE:CFTSRV</p>
         </td>
         <td>
            <p>STARTUP, SHUTDOWN</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>SERVICE:COM</p>
         </td>
         <td>
            <p>DELETE, VIEW</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>COMMAND:EXTRACT</p>
         </td>
         <td>
            <p>EXECUTE</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>COMMAND:MQUERY</p>
         </td>
         <td>
            <p>EXECUTE</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>COMMAND:TURN</p>
         </td>
         <td>
            <p>EXECUTE</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>COMMAND:CFTSUPPORT</p>
         </td>
         <td>
            <p>EXECUTE</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>TRANSFER</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT, CANCEL, RESUME, PAUSE, EXECUTE, SUBMIT, END, VIEWIFLE, EDITFILE, DELETEFILE</p>
         </td>
         <td>
            <p>IDAPPL, ID, PART, SPART, RPART, IPART, TYPE, DIRECT, MODE, FNAME, MESSAGE, SUSER, RUSER, SAPPL, RAPPL, NFNAME</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>AM:RIGHTS <sup>(4)</sup></p>
         </td>
         <td>
            <p>VIEW_SELF, VIEW_OTHERS</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>FILTER:CATALOG</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>FILTER:LOG</p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>ID</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>FILE <sup>(5)</sup></p>
         </td>
         <td>
            <p>CREATE, DELETE, VIEW, EDIT</p>
         </td>
         <td>
            <p>FNAME</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>URL <sup>(6)</sup></p>
         </td>
         <td>
            <p>VIEW</p>
         </td>
         <td>
            <p>URL</p>
         </td>
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

The following is an example of the Transfer CFT configuration for this use case (the ROLE must exist in Flow Manager, and be available for required users):

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTROLE      ID          = '<span>TRANSFER-ROLE</span>',</p>
            <p>             COMMENT     = '',</p>
            <p>/*           ALIASES     = ( ) ,*/</p>
            <p>             PRIVS       = ( '<span>PRIV-XFER-SPE</span>',</p>
            <p>                              'PRIV-CONN-INTERFACES',</p>
            <p>                              'CONFIGURATION:CFTCOM_VIEW',</p>
            <p>                              'CONFIGURATION:CFTPARM_VIEW',</p>
            <p>                              'FILTER:CATALOG_ALL',</p>
            <p>                              'FILTER:LOG_ALL',</p>
            <p>                              'FILE_VIEW',</p>
            <p>                              'CONFIGURATION:PKICER_VIEW',</p>
            <p>                              'CONFIGURATION:PKIENTITY_VIEW',</p>
            <p>                               'CONFIGURATION:PKIKEY_VIEW',</p>
            <p>                              'CONFIGURATION:CFTPARM_VIEW',</p>
            <p>                              'CONFIGURATION:CFTNET_VIEW',</p>
            <p>                              'CONFIGURATION:CFTPROT_VIEW',</p>
            <p>                              'CONFIGURATION:CFTSEND_VIEW',</p>
            <p>                              'CONFIGURATION:CFTSENDI_VIEW',</p>
            <p>                              'CONFIGURATION:CFTRECV_VIEW',</p>
            <p>                              'CONFIGURATION:CFTAUTH_VIEW',</p>
            <p>                              'CONFIGURATION:CFTXLATE_VIEW',</p>
            <p>                              'CONFIGURATION:CFTLOG_VIEW',</p>
            <p>                              'CONFIGURATION:CFTCAT_VIEW',</p>
            <p>                              'CONFIGURATION:CFTCOM_VIEW',</p>
            <p>                              'CONFIGURATION:CFTACCNT_VIEW',</p>
            <p>                              'CONFIGURATION:CFTEXIT_VIEW',</p>
            <p>                              'CONFIGURATION:CFTIDF_VIEW',</p>
            <p>                              'CONFIGURATION:CFTFOLDER_VIEW',</p>
            <p>                              'CONFIGURATION:CFTETB_VIEW',</p>
            <p>                              'CONFIGURATION:CFTAPPL_VIEW',</p>
            <p>                              'CONFIGURATION:CFTSSL_VIEW',</p>
            <p>                              'CONFIGURATION:CFTCRON_VIEW',</p>
            <p>                              'CONFIGURATION:CFTPART_VIEW',</p>
            <p>                              'CONFIGURATION:CFTDEST_VIEW',</p>
            <p>                              'CONFIGURATION:CFTTCP_VIEW',</p>
            <p>                              'CONFIGURATION:CFTUCONF_VIEW',</p>
            <p>                              'SERVICE:COM_VIEW',</p>
            <p>                              'AM:RIGHTS_VIEW_SELF'),</p>
            <p>              MODE        = 'REPLACE'</p>
            <p> </p>
            <p>CFTPRIV       ID          = '<span>PRIV-XFER-SPE</span>',</p>
            <p>              COMMENT     = 'PRIV limits transfers - no delete condition',</p>
            <p>              RESOURCE    = 'TRANSFER',</p>
            <p>              ACTIONS     = ( 'CREATE',</p>
            <p>                              'RESUME',</p>
            <p>                              'VIEW',</p>
            <p>                              'CANCEL',   </p>
            <p>                               'PAUSE',</p>
            <p>                              'EXECUTE'),</p>
            <p>              CONDITION   = ' IDF=="MYIDF" &amp;&amp; PART=="MYPART" ',</p>
            <p>              ORIGIN      = 'CFTUTIL',</p>
            <p>              MODE        = 'REPLACE'</p>
         </td>
      </tr>
   </tbody>
</table>

### Add an administrator role

As an administrator, you want to assign a role equivalent to classic 'Administrator' role to a user, but I would like to restrict access in the UI (Copilot or CFTUI) to a given Transfer CFT Name or a Group of Transfer CFTs, based on the Transfer CFT instance ID and instance group.

In this use case, you assign the user role that refers to a privilege having these characteristics:

-   RESOURCE = SERVICE:UI,
-   ACTIONS = ( 'CONNECT' ),
-   CONDITION = ' GROUP=="PRODUCTION" && ID~=''CFT-PROD-ITEM\*'' '

A user with this privilege can only connect to a Transfer CFT server whose UCONF cft.instance\_group value is set to PRODUCTION, and whose cft.instance\_id value begins with CFT-PROD-ITEM.

The following is an example of the Transfer CFT configuration for this use case (the ROLE must exist in Flow Manager, and be available for required users):

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTROLE      ID          = '<span>ADMIN_ROLE</span>',</p>
            <p>              COMMENT     = 'Administrator role for Production Transfer CFT Windows',</p>
            <p><span>              PRIVS       = ('<span>PRIV-CONN-INTERFACES</span>',               </span>
</p>
            <p>                              'AM:RIGHTS_VIEW_ALL',</p>
            <p>                              'CONFIGURATION:PKICER_ALL',</p>
            <p>                              'CONFIGURATION:PKIENTITY_ALL',</p>
            <p>                              'CONFIGURATION:PKIKEY_ALL',</p>
            <p>                              'CONFIGURATION:CFTPARM_ALL',</p>
            <p>                              'CONFIGURATION:CFTNET_ALL',</p>
            <p>                              'CONFIGURATION:CFTPROT_ALL',</p>
            <p>                              'CONFIGURATION:CFTSEND_ALL',</p>
            <p>                              'CONFIGURATION:CFTSENDI_ALL',</p>
            <p>                              'CONFIGURATION:CFTRECV_ALL',</p>
            <p>                              'CONFIGURATION:CFTAUTH_ALL',</p>
            <p>                              'CONFIGURATION:CFTXLATE_ALL',</p>
            <p>                              'CONFIGURATION:CFTLOG_ALL',</p>
            <p>                              'CONFIGURATION:CFTCAT_ALL',</p>
            <p>                              'CONFIGURATION:CFTCOM_ALL',</p>
            <p>                               'CONFIGURATION:CFTACCNT_ALL',</p>
            <p>                              'CONFIGURATION:CFTEXIT_ALL',</p>
            <p>                              'CONFIGURATION:CFTIDF_ALL',</p>
            <p>                              'CONFIGURATION:CFTFOLDER_ALL',</p>
            <p>                              'CONFIGURATION:CFTETB_ALL',</p>
            <p>                              'CONFIGURATION:CFTAPPL_ALL',</p>
            <p>                              'CONFIGURATION:CFTSSL_ALL',</p>
            <p>                              'CONFIGURATION:CFTCRON_ALL',</p>
            <p>                              'CONFIGURATION:CFTPART_ALL',</p>
            <p>                               'CONFIGURATION:CFTDEST_ALL',</p>
            <p>                              'CONFIGURATION:CFTROLE_ALL',</p>
            <p>                              'CONFIGURATION:CFTPRIV_ALL',</p>
            <p>                              'CONFIGURATION:CFTTCP_ALL',</p>
            <p>                               'CONFIGURATION:CFTUCONF_ALL',</p>
            <p>                              'SERVICE:CATALOG_PURGE',</p>
            <p>                              'SERVICE:LOG_SWITCH',</p>
            <p>                              'SERVICE:ACCOUNT_SWITCH',</p>
            <p>                              'SERVICE:BATCH_EXECUTE',</p>
            <p>                               'SERVICE:CFTSRV_ALL',</p>
            <p>                              'SERVICE:COM_ALL',</p>
            <p>                              'TRANSFER_ALL',</p>
            <p>                              'FILTER:CATALOG_ALL',</p>
            <p>                              'FILTER:LOG_ALL',</p>
            <p>                              'FILE_ALL',</p>
            <p>                              'URL_VIEW',</p>
            <p>                              'COMMAND:EXTRACT_ALL',</p>
            <p>                              'COMMAND:MQUERY_ALL',</p>
            <p>                              'COMMAND:TURN_ALL',</p>
            <p>                              'COMMAND:CFTSUPPORT_ALL'),</p>
            <p>              MODE        = 'REPLACE'</p>
            <p> </p>
            <p>CFTPRIV      ID          = '<span>PRIV-CONN-INTERFACES</span>',</p>
            <p>              COMMENT     = 'PRIV LIMITs the connection for a given Transfer CFT name',</p>
            <p>             RESOURCE    = 'SERVICE:UI',</p>
            <p>             ACTIONS     = ( 'CONNECT'),</p>
            <p>             CONDITION   = 'GROUP=="PRODUCTION" &amp;&amp; ID~="CFT-PROD-ITEM*"',  </p>
            <p>             MODE        = 'REPLACE'</p>
            <p> </p>
         </td>
      </tr>
   </tbody>
</table>

A user with this privilege can only connect to a Transfer CFT server whose UCONF cft.instance\_group value is set to PRODUCTION, and whose cft.instance\_id value begins with CFT-PROD-ITEM.
