{
    "title": "Access Management using Flow Manager",
    "linkTitle": "Flow Manager access management ",
    "weight": "150"
}You can use {{< TransferCFT/flowmanager  >}} to define and control Transfer CFT access management as described in the following sections.

How it works

If you have opted to use the {{< TransferCFT/flowmanager  >}} for {{< TransferCFT/transfercftname  >}} access management, after configuring both {{< TransferCFT/transfercftname  >}} and {{< TransferCFT/flowmanager  >}}:

1.  A user logs in via the {{< TransferCFT/transfercftname >}} UI, CFTUTIL, or other.
2.  A login request is sent to {{< TransferCFT/flowmanager >}}.
3.  If the login is successful, {{< TransferCFT/flowmanager >}} returns the list of roles for the user.
4.  The user login is complete. Transfer CFT then stores these roles in the cache and applies them accordingly. The information about this user is stored in the cache and is only updated when a new login is performed.

> **Note:**
>
> All role and permission definitions are stored in CFTPARM.

However, if you are an `am.superuser` user, {{< TransferCFT/transfercftname  >}} does not check your access for resources, and permissions are granted unconditionally. Additionally, it is useful to note that if you define a service account during {{< TransferCFT/componentlongname  >}} installation, this user is automatically added to the UCONF `am.superuser` parameter's list.

See also, {{< TransferCFT/flowmanager  >}} *Security Guide &gt;*[Predefined roles](https://docs.axway.com/bundle/FlowManager_20_allOS_en_HTML5/page/predefined_roles.html) and [Predefined privileges](https://docs.axway.com/bundle/FlowManager_20_allOS_en_HTML5/page/predefined_privileges.html) (requires account login).

<img src="/Images/TransferCFT/cg_am.jpg" class="mediumWidth" />

Limitations

-   {{< TransferCFT/hflongproductname >}} ROLES are stored on {{< TransferCFT/hflongproductname >}} in upper case. This means that if you create roles **XXX** and **Xxx** on {{< TransferCFT/flowmanager >}}, there is only one ROLE in {{< TransferCFT/hflongproductname >}}, which is `ID=XXX`.

<span id="Using"></span>

## Using roles and privileges

The {{< TransferCFT/flowmanager  >}} method of access management impacts two {{< TransferCFT/transfercftname  >}} objects that are defined in the CFTPARM database: roles (CFTROLE) and privileges (CFTPRIV). You assign these roles and privileges in {{< TransferCFT/flowmanager  >}}, which are then deployed on Transfer CFT.

Conversely, you can create roles and privileges locally in Transfer CFT, as you do with other objects.

### Using CFTROLE

A role is a general profile that can be associated with a user. A role is based on one or more privileges, and a privilege is based on a resource. There are two types of roles: predefined and user-defined. Predefined roles are available by default to assign to users.

You can assign users to one or more roles. Typically, users with multiple roles have more privileges than users with fewer roles.

Examples of roles can be ADMINISTRATOR, PARTNER MANAGER, IT MANAGER, and so on.


|  Field  |  Type  |  Comment  |
| --- | --- | --- |
|  id  |  String32  |  Role identifier  |
|  comment  |  String80  |  Comment  |
|  privs[]  |  List of String32  |  List of privileges associated to this role (1 to 128)  |


Example of CFTROLE in a configuration file:

```
CFTROLE      ID          = 'Application',
             COMMENT     = 'My comments',
             PRIVS       = ( 'SERVICE:UI\_CONNECT',
                             'MYPRIV1',
                             'CONFIGURATION:CFTCOM\_VIEW',
                             'CONFIGURATION:CFTPARM\_VIEW',
                             'CONFIGURATION:CFTPART\_VIEW',
                             'CONFIGURATION:CFTDEST\_VIEW',
                             'CONFIGURATION:CFTSEND\_VIEW',
                             'CONFIGURATION:CFTRECV\_VIEW',
                             'CONFIGURATION:CFTLOG\_VIEW',
                             'FILTER:CATALOG\_ALL',
                             'FILTER:LOG\_ALL',
                             'FILE\_VIEW'),
             ORIGIN      = 'CFTUTIL',
             MODE        = 'REPLACE'
```

### Using CFTPRIV

Privileges give users authorization to access and perform actions in the user interface. Examples of actions include CREATE, DELETE, VIEW, EDIT (use \* to assign all actions).


|  Field  |  Type  |  Comment  |
| --- | --- | --- |
|  id  |  String32  |  Privilege identifier  |
|  comment  |  String80  |  Comment  |
|  resource  |  String32  |  Resource on which this privilege applies  |
|  actions  |  List of String32  |  Actions authorized on the resource (1 to 16 actions)  |
|  condition  |  String256  |  Condition to check for authorizing (<a href="#Specifyi">see below</a>)  |


Example of CFTPRIV in a configuration file:

```
CFTPRIV      ID          = 'MYPRIV1',
            COMMENT     = 'My comment',
             RESOURCE    = 'TRANSFER',
             ACTIONS     = ( 'CREATE' , 'DELETE', 'VIEW', 'EDIT', 'CANCEL', 'RESUME',
                            'PAUSE', 'EXECUTE', 'SUBMIT', 'END' ),
             CONDITION   = '',
             ORIGIN      = 'CFTUTIL',
             MODE        = 'REPLACE'
```
<span id="Specifyi"></span>

### Specifying conditions

Conditions allow you to assign finer control on resources and actions by specifying a logical condition that must be true to authorize the action.

Examples

In these examples `PART `and `ID `are properties of the resource being checked. As you can see, you can use parenthesis and logical operators `&&` (AND) and `||` (OR).

```
PART=="PARIS" && ID=="IDFDEF"
(PART=="PARIS" || PART==”NEWYORK”) && ID~="IDF\*"
```

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


|  Resource  |  Actions  |  Properties  |
| --- | --- | --- |
|  CONFIGURATION:PKICER  |  CREATE, DELETE, VIEW, EDIT, ACTIVATE, DEACTIVATE  |  ID  |
|  CONFIGURATION:PKIENTITY  |  CREATE, DELETE, VIEW, EDIT, ACTIVATE, DEACTIVATE  |  ID  |
|  CONFIGURATION:PKIKEY  |  CREATE, DELETE, VIEW, EDIT, ACTIVATE, DEACTIVATE  |  ID  |
|  CONFIGURATION:CFTPARM  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION:CFTNET  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION:CFTPROT  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION: CFTSEND  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION: CFTSENDI <sup>(1)</sup>  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION: CFTRECV  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION:CFTAUTH  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION:CFTXLATE  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION:CFTLOG  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION:CFTCAT  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION:CFTCOM  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION:CFTACCNT  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION:CFTEXIT  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION:CFTIDF  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION:CFTFOLDER  |  CREATE, DELETE, VIEW, EDIT, ACTIVATE, DEACTIVATE  |  ID  |
|  CONFIGURATION:CFTETB  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION:CFTAPPL  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION:CFTSSL  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION:CFTCRON  |  CREATE, DELETE, VIEW, EDIT, ACTIVATE, DEACTIVATE, RELOAD  |  ID  |
|  CONFIGURATION:CFTPART  |  CREATE, DELETE, VIEW, EDIT, ACTIVATE, DEACTIVATE, TURN  |  ID  |
|  CONFIGURATION:CFTDEST  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION:CFTTCP  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  CONFIGURATION:CFTUCONF  |  DELETE, VIEW, EDIT  |  ID  |
|   |   |   |
|  SERVICE:BATCH <sup>(2)</sup>  |  EXECUTE  |  ID, FNAME  |
|  SERVICE:UI <sup>(3)</sup>  |  CONNECT  |  TYPE, ID, GROUP  |
|  SERVICE:BATCH  |  EXECUTE  |  ID, FNAME  |
|  SERVICE:CATALOG  |  PURGE  |   |
|  SERVICE:LOG  |  SWITCH  |   |
|  SERVICE:ACCOUNT  |  SWITCH  |   |
|  SERVICE:CFTSRV  |  STARTUP, SHUTDOWN  |   |
|  SERVICE:COM  |  DELETE, VIEW  |   |
|   |   |   |
|  COMMAND:EXTRACT  |  EXECUTE  |   |
|  COMMAND:MQUERY  |  EXECUTE  |   |
|  COMMAND:TURN  |  EXECUTE  |   |
|  COMMAND:CFTSUPPORT  |  EXECUTE  |   |
|  TRANSFER  |  CREATE, DELETE, VIEW, EDIT, CANCEL, RESUME, PAUSE, EXECUTE, SUBMIT, END, VIEWIFLE, EDITFILE, DELETEFILE  |  IDAPPL, ID, PART, SPART, RPART, IPART, TYPE, DIRECT, MODE, FNAME, MESSAGE, SUSER, RUSER, SAPPL, RAPPL, NFNAME  |
|  AM:RIGHTS <sup>(4)</sup>  |  VIEW_SELF, VIEW_OTHERS  |  ID  |
|  FILTER:CATALOG  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  FILTER:LOG  |  CREATE, DELETE, VIEW, EDIT  |  ID  |
|  FILE <sup>(5)</sup>  |  CREATE, DELETE, VIEW, EDIT  |  FNAME  |
|  URL <sup>(6)</sup>  |  VIEW  |  URL  |


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

The following is an example of the {{< TransferCFT/transfercftname  >}} configuration for this use case (the ROLE must exist in {{< TransferCFT/flowmanager  >}}, and be available for required users):

```
CFTROLE      ID          = '',
             COMMENT     = '',
/\*           ALIASES     = ( ) ,\*/
             PRIVS       = ( '',
                              'PRIV-CONN-INTERFACES',
                              'CONFIGURATION:CFTCOM\_VIEW',
                              'CONFIGURATION:CFTPARM\_VIEW',
                              'FILTER:CATALOG\_ALL',
                              'FILTER:LOG\_ALL',
                              'FILE\_VIEW',
                              'CONFIGURATION:PKICER\_VIEW',
                              'CONFIGURATION:PKIENTITY\_VIEW',
                               'CONFIGURATION:PKIKEY\_VIEW',
                              'CONFIGURATION:CFTPARM\_VIEW',
                              'CONFIGURATION:CFTNET\_VIEW',
                              'CONFIGURATION:CFTPROT\_VIEW',
                              'CONFIGURATION:CFTSEND\_VIEW',
                              'CONFIGURATION:CFTSENDI\_VIEW',
                              'CONFIGURATION:CFTRECV\_VIEW',
                              'CONFIGURATION:CFTAUTH\_VIEW',
                              'CONFIGURATION:CFTXLATE\_VIEW',
                              'CONFIGURATION:CFTLOG\_VIEW',
                              'CONFIGURATION:CFTCAT\_VIEW',
                              'CONFIGURATION:CFTCOM\_VIEW',
                              'CONFIGURATION:CFTACCNT\_VIEW',
                              'CONFIGURATION:CFTEXIT\_VIEW',
                              'CONFIGURATION:CFTIDF\_VIEW',
                              'CONFIGURATION:CFTFOLDER\_VIEW',
                              'CONFIGURATION:CFTETB\_VIEW',
                              'CONFIGURATION:CFTAPPL\_VIEW',
                              'CONFIGURATION:CFTSSL\_VIEW',
                              'CONFIGURATION:CFTCRON\_VIEW',
                              'CONFIGURATION:CFTPART\_VIEW',
                              'CONFIGURATION:CFTDEST\_VIEW',
                              'CONFIGURATION:CFTTCP\_VIEW',
                              'CONFIGURATION:CFTUCONF\_VIEW',
                              'SERVICE:COM\_VIEW',
                              'AM:RIGHTS\_VIEW\_SELF'),
              MODE        = 'REPLACE'
 
CFTPRIV       ID          = '',
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
```

### Add an administrator role

As an administrator, you want to assign a role equivalent to classic 'Administrator' role to a user, but I would like to restrict access in the UI (Copilot or CFTUI) to a given Transfer CFT Name or a Group of Transfer CFTs, based on the Transfer CFT instance ID and instance group.

In this use case, you assign the user role that refers to a privilege having these characteristics:

-   RESOURCE = SERVICE:UI,
-   ACTIONS = ( 'CONNECT' ),
-   CONDITION = ' GROUP=="PRODUCTION" && ID~=''CFT-PROD-ITEM\*'' '

A user with this privilege can only connect to a Transfer CFT server whose UCONF `cft.instance_group` value is set to PRODUCTION, and whose `cft.instance_id` value begins with CFT-PROD-ITEM.

The following is an example of the {{< TransferCFT/transfercftname  >}} configuration for this use case (the ROLE must exist in {{< TransferCFT/flowmanager  >}}, and be available for required users):

```
CFTROLE      ID          = '',
              COMMENT     = 'Administrator role for Production Transfer CFT Windows',
                              'AM:RIGHTS\_VIEW\_ALL',
                              'CONFIGURATION:PKICER\_ALL',
                              'CONFIGURATION:PKIENTITY\_ALL',
                              'CONFIGURATION:PKIKEY\_ALL',
                              'CONFIGURATION:CFTPARM\_ALL',
                              'CONFIGURATION:CFTNET\_ALL',
                              'CONFIGURATION:CFTPROT\_ALL',
                              'CONFIGURATION:CFTSEND\_ALL',
                              'CONFIGURATION:CFTSENDI\_ALL',
                              'CONFIGURATION:CFTRECV\_ALL',
                              'CONFIGURATION:CFTAUTH\_ALL',
                              'CONFIGURATION:CFTXLATE\_ALL',
                              'CONFIGURATION:CFTLOG\_ALL',
                              'CONFIGURATION:CFTCAT\_ALL',
                              'CONFIGURATION:CFTCOM\_ALL',
                               'CONFIGURATION:CFTACCNT\_ALL',
                              'CONFIGURATION:CFTEXIT\_ALL',
                              'CONFIGURATION:CFTIDF\_ALL',
                              'CONFIGURATION:CFTFOLDER\_ALL',
                              'CONFIGURATION:CFTETB\_ALL',
                              'CONFIGURATION:CFTAPPL\_ALL',
                              'CONFIGURATION:CFTSSL\_ALL',
                              'CONFIGURATION:CFTCRON\_ALL',
                              'CONFIGURATION:CFTPART\_ALL',
                               'CONFIGURATION:CFTDEST\_ALL',
                              'CONFIGURATION:CFTROLE\_ALL',
                              'CONFIGURATION:CFTPRIV\_ALL',
                              'CONFIGURATION:CFTTCP\_ALL',
                               'CONFIGURATION:CFTUCONF\_ALL',
                              'SERVICE:CATALOG\_PURGE',
                              'SERVICE:LOG\_SWITCH',
                              'SERVICE:ACCOUNT\_SWITCH',
                              'SERVICE:BATCH\_EXECUTE',
                               'SERVICE:CFTSRV\_ALL',
                              'SERVICE:COM\_ALL',
                              'TRANSFER\_ALL',
                              'FILTER:CATALOG\_ALL',
                              'FILTER:LOG\_ALL',
                              'FILE\_ALL',
                              'URL\_VIEW',
                              'COMMAND:EXTRACT\_ALL',
                              'COMMAND:MQUERY\_ALL',
                              'COMMAND:TURN\_ALL',
                              'COMMAND:CFTSUPPORT\_ALL'),
              MODE        = 'REPLACE'
 
CFTPRIV      ID          = '',
              COMMENT     = 'PRIV LIMITs the connection for a given Transfer CFT name',
             RESOURCE    = 'SERVICE:UI',
             ACTIONS     = ( 'CONNECT'),
             CONDITION   = 'GROUP=="PRODUCTION" && ID~="CFT-PROD-ITEM\*"', 
             MODE        = 'REPLACE'
 
```

A user with this privilege can only connect to a Transfer CFT server whose UCONF `cft.instance_group` value is set to `PRODUCTION`, and whose `cft.instance_id` value begins with `CFT-PROD-ITEM`.
