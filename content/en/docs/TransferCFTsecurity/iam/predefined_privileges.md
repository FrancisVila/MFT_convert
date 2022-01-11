{
    "title": "Predefined privileges",
    "linkTitle": "Predefined privileges and roles",
    "weight": "80"
}The following table lists predefined privileges and descriptions in Transfer CFT.

```

Privilege with CG

Privilege without CG

Resource

Resource actions

Manage PKI
CONFIGURATION:PKICER_ALL
CONFIGURATION:PKICER
CREATE, DELETE, EDIT, VIEW, ACTIVATE, DEACTIVATE
Manage CFTPARM
CONFIGURATION:CFTPARM_ALL
CONFIGURATION:CFTPARM
CREATE, DELETE, VIEW, EDIT
Manage CFTNET
CONFIGURATION:CFTNET_ALL
CONFIGURATION:CFTNET
CREATE, DELETE, VIEW, EDIT
Manage CFTPROT
CONFIGURATION:CFTPROT_ALL
CONFIGURATION:CFTPROT
CREATE, DELETE, VIEW, EDIT
Manage CFTSEND
CONFIGURATION:CFTSEND_ALL
CONFIGURATION:CFTSEND
CREATE, DELETE, VIEW, EDIT
Manage CFTSENDI
CONFIGURATION:CFTSENDI_ALL
CONFIGURATION:CFTSENDI
CREATE, DELETE, VIEW, EDIT
Manage CFTRECV
CONFIGURATION:CFTRECV_ALL
CONFIGURATION:CFTRECV
CREATE, DELETE, VIEW, EDIT
Manage CFTAUTH
CONFIGURATION:CFTAUTH_ALL
CONFIGURATION:CFTAUTH
CREATE, DELETE, VIEW, EDIT
Manage CFTXLATE
CONFIGURATION:CFTXLATE_ALL
CONFIGURATION:CFTXLATE
CREATE, DELETE, VIEW, EDIT
Manage CFTLOG
CONFIGURATION:CFTLOG_ALL
CONFIGURATION:CFTLOG
CREATE, DELETE, VIEW, EDIT
Manage CFTCAT
CONFIGURATION:CFTCAT_ALL
CONFIGURATION:CFTCAT
CREATE, DELETE, VIEW, EDIT
Manage CFTCOM
CONFIGURATION:CFTCOM_ALL
CONFIGURATION:CFTCOM
CREATE, DELETE, VIEW, EDIT
Manage CFTACCNT
CONFIGURATION:CFTACCNT_ALL
CONFIGURATION:CFTACCNT
CREATE, DELETE, VIEW, EDIT
Manage CFTEXIT
CONFIGURATION:CFTEXIT_ALL
CONFIGURATION:CFTEXIT
CREATE, DELETE, VIEW, EDIT
Manage CFTIDF
CONFIGURATION:CFTIDF_ALL
CONFIGURATION:CFTIDF
CREATE, DELETE, VIEW, EDIT
Manage CFTFOLDER
CONFIGURATION:CFTFOLDER_ALL
CONFIGURATION:CFTFOLDER
CREATE, DELETE, VIEW, EDIT
Manage CFTETB
CONFIGURATION:CFTETB_ALL
CONFIGURATION:CFTETB
CREATE, DELETE, VIEW, EDIT
Manage CFTAPPL
CONFIGURATION:CFTAPPL_ALL
CONFIGURATION:CFTAPPL
CREATE, DELETE, VIEW, EDIT
Manage CFTSSL
CONFIGURATION:CFTSSL_ALL
CONFIGURATION:CFTSSL
CREATE, DELETE, VIEW, EDIT
Manage CFTCRON
CONFIGURATION:CFTCRON_ALL
CONFIGURATION:CFTCRON
CREATE, DELETE, VIEW, EDIT, ACTIVATE, DEACTIVATE, RELOAD
Manage CFTPART
CONFIGURATION:CFTPART_ALL
CONFIGURATION:CFTPART
CREATE, DELETE, VIEW, EDIT, TURN, ACTIVATE, DEACTIVATE
Manage CFTDEST
CONFIGURATION:CFTDEST_ALL
CONFIGURATION:CFTDEST
CREATE, DELETE, VIEW, EDIT
Manage CFTTCP
CONFIGURATION:CFTTCP_ALL
CONFIGURATION:CFTTCP
CREATE, DELETE, VIEW, EDIT
Manage UCONF
CONFIGURATION:CFTUCONF_ALL
CONFIGURATION:CFTUCONF
DELETE, VIEW, EDIT
Purge Transfer List
SERVICE:CATALOG_PURGE
SERVICE:CATALOG
PURGE
Switch Log
SERVICE:LOG_SWITCH
SERVICE:LOG
SWITCH
Switch Accounts
SERVICE:ACCOUNT_SWITCH
SERVICE:ACCOUNT
SWITCH
Execute Batch Files
SERVICE:BATCH_EXECUTE
SERVICE:BATCH
EXECUTE
Manage Transfer CFT Server
SERVICE:CFTSRV_ALL
SERVICE:CFTSRV
STARTUP, SHUTDOWN, VIEW, EDIT
Connect to Transfer CFT UI
SERVICE:UI_CONNECT
SERVICE:UI
CONNECT
View Central Governance rights for all users
AM:RIGHTS_VIEW_ALL
AM:RIGHTS
VIEW_SELF, VIEW_OTHERS
View Central Governance rights for own users
AM:RIGHTS_VIEW_SELF
AM:RIGHTS
VIEW_SELF
Manage Communication Files
SERVICE:COM_ALL
SERVICE:COM
DELETE, VIEW
Manage Transfers
TRANSFER_ALL
TRANSFER
CREATE, DELETE, VIEW, EDIT, CANCEL, RESUME, PAUSE, EXECUTE, SUBMIT, END, VIEWFILE, EDITFILE, DELETEFILE
Manage Catalog Filters
FILTER:CATALOG_ALL
FILTER:CATALOG
CREATE, EDIT, VIEW, DELETE
Manage Log Filters
FILTER:LOG_ALL
FILTER:LOG
CREATE, EDIT, VIEW, DELETE
Manage Transfer CFT files
FILE_ALL
FILE
CREATE, EDIT, VIEW, DELETE
Manage CFTUIPREF
CONFIGURATION:CFTUIPREF_ALL
CONFIGURATION:CFTUIPREF
CREATE, DELETE, VIEW, EDIT
View File Name Definitions
URL_VIEW
URL
VIEW
Extract Transfer CFT Configuration
COMMAND:EXTRACT_ALL
COMMAND:EXTRACT
EXECUTE
Execute MQUERY command
COMMAND:MQUERY
COMMAND:MQUERY
EXECUTE
Execute Turn command for DMZ
COMMAND:TURN_ALL
COMMAND:TURN
EXECUTE
Execute cft_support
COMMAND:CFTSUPPORT_ALL
COMMAND:CFTSUPPORT
EXECUTE
View PKI
CONFIGURATION:PKICER_VIEW
CONFIGURATION:PKICER
VIEW
View CFTPARM
CONFIGURATION:CFTPARM_VIEW
CONFIGURATION:CFTPARM
VIEW
View CFTNET
CONFIGURATION:CFTNET_VIEW
CONFIGURATION:CFTNET
VIEW
View CFTPROT
CONFIGURATION:CFTPROT_VIEW
CONFIGURATION:CFTPROT
VIEW
View CFTSEND
CONFIGURATION:CFTSEND_VIEW
CONFIGURATION:CFTSEND
VIEW
View CFTSENDI
CONFIGURATION:CFTSENDI_VIEW
CONFIGURATION:CFTSENDI
VIEW
View CFTRECV
CONFIGURATION:CFTRECV_VIEW
CONFIGURATION:CFTRECV
VIEW
View CFTAUTH
CONFIGURATION:CFTAUTH_VIEW
CONFIGURATION:CFTAUTH
VIEW
View CFTXLATE
CONFIGURATION:CFTXLATE_VIEW
CONFIGURATION:CFTXLATE
VIEW
View CFTLOG
CONFIGURATION:CFTLOG_VIEW
CONFIGURATION:CFTLOG
VIEW
View CFTCAT
CONFIGURATION:CFTCAT_VIEW
CONFIGURATION:CFTCAT
VIEW
View CFTCOM
CONFIGURATION:CFTCOM_VIEW
CONFIGURATION:CFTCOM
VIEW
View CFTACCNT
CONFIGURATION:CFTACCNT_VIEW
CONFIGURATION:CFTACCNT
VIEW
View CFTEXIT
CONFIGURATION:CFTEXIT_VIEW
CONFIGURATION:CFTEXIT
VIEW
View CFTIDF
CONFIGURATION:CFTIDF_VIEW
CONFIGURATION:CFTIDF
VIEW
View CFTFOLDER
CONFIGURATION:CFTFOLDER_VIEW
CONFIGURATION:CFTFOLDER
VIEW
View CFTETB
CONFIGURATION:CFTETB_VIEW
CONFIGURATION:CFTETB
VIEW
View CFTAPPL
CONFIGURATION:CFTAPPL_VIEW
CONFIGURATION:CFTAPPL
VIEW
View CFTSSL
CONFIGURATION:CFTSSL_VIEW
CONFIGURATION:CFTSSL
VIEW
View CFTCRON
CONFIGURATION:CFTCRON_VIEW
CONFIGURATION:CFTCRON
VIEW
View CFTPART
CONFIGURATION:CFTPART_VIEW
CONFIGURATION:CFTPART
VIEW
View CFTDEST
CONFIGURATION:CFTDEST_VIEW
CONFIGURATION:CFTDEST
VIEW
View CFTTCP
CONFIGURATION:CFTTCP_VIEW
CONFIGURATION:CFTTCP
VIEW
View UCONF
CONFIGURATION:CFTUCONF_VIEW
CONFIGURATION:CFTUCONF
VIEW
View CFTUIPREF
CONFIGURATION:CFTUIPREF_VIEW
CONFIGURATION:CFTUIPREF
VIEW
View Communication File
SERVICE:COM_VIEW
SERVICE:COM
VIEW
Create, Execute and View Xfers
TRANSFER_CREATE_VIEW_EXECUTE
TRANSFER
CREATE, VIEW, EXECUTE
```

## Predefined default roles with Central Governance or Flow Manager

This section describes the predefined roles in Transfer CFT when registered with Central Governance.

> **Note**
>
> See theTransfer CFT User Guide for information on modifying predefined roles and privileges or creating new ones.

### Transfer CFT Administrator

This role enables full management on Transfer CFT, and groups the following privileges:

- Connect to Transfer CFT UI
- Execute Batch Files
- Execute cft\_support command
- Execute MQUERY command
- Execute Turn command for DMZ
- Extract Transfer CFT Configuration
- Manage Catalog Filters
- Manage CFTACCNT
- Manage CFTAPPL
- Manage CFTAUTH
- Manage CFTCAT
- Manage CFTCOM
- Manage CFTCRON
- Manage CFTDEST
- Manage CFTETB
- Manage CFTEXIT
- Manage CFTFOLDER
- Manage CFTIDF
- Manage CFTLOG
- Manage CFTNET
- Manage CFTPARM
- Manage CFTPART
- Manage CFTPRIV
- Manage CFTPRIV
- Manage CFTPROT
- Manage CFTRECV
- Manage CFTROLE
- Manage CFTSEND
- Manage CFTSENDI
- Manage CFTSSH
- Manage CFTSSL
- Manage CFTTCP
- Manage CFTTOKEN
- Manage CFTUIPREF
- Manage CFTXLATE
- Manage Communication Files
- Manage Log Filters
- Manage PKI certificates
- Manage PKI entities
- Manage PKI keys
- Manage Transfer CFT files
- Manage Transfer CFT Server
- Manage Transfers
- Manage UCONF
- Purge Transfer List
- Switch Accounts
- Switch Log
- View CG rights for all users
- View File Name Definitions
- View nodes status

### Application

This role enables applications to create and execute transfers, and groups the following privileges:

- All Actions for Transfers
- Connect to Transfer CFT UI
- File view
- Manage Catalog Filters
- Manage CFTUIPREF
- Manage Log Filters
- View CFTCOM
- View CFTDEST
- View CFTLOG
- View CFTPARM
- View CFTPART
- View CFTRECV
- View CFTSEND
- View nodes status

## Predefined default roles without Central Governance or {{< TransferCFTsecurity/flowmanager  >}}

This section describes the predefined roles in Transfer CFT when using PassPort AM without being registered with Central Governance.

> **Note**
>
> See theTransfer CFT User Guide for information on modifying predefined roles and privileges.

#### Administrator

This role enables you to perform all administrative tasks, and groups the following privileges:

- AM:RIGHTS\_VIEW\_ALL
- COMMAND:CFTSUPPORT\_ALL
- COMMAND:EXTRACT\_ALL
- COMMAND:MQUERY\_ALL
- COMMAND:TURN\_ALL
- CONFIGURATION:CFTACCNT\_ALL
- CONFIGURATION:CFTAPPL\_ALL
- CONFIGURATION:CFTAUTH\_ALL
- CONFIGURATION:CFTCAT\_ALL
- CONFIGURATION:CFTCOM\_ALL
- CONFIGURATION:CFTCRON\_ALL
- CONFIGURATION:CFTDEST\_ALL
- CONFIGURATION:CFTDNA\_ALL
- CONFIGURATION:CFTDSA\_ALL
- CONFIGURATION:CFTETB\_ALL
- CONFIGURATION:CFTEXIT\_ALL
- CONFIGURATION:CFTFOLDER\_ALL
- CONFIGURATION:CFTIDF\_ALL
- CONFIGURATION:CFTLOG\_ALL
- CONFIGURATION:CFTLU62\_ALL
- CONFIGURATION:CFTNET\_ALL
- CONFIGURATION:CFTPARM\_ALL
- CONFIGURATION:CFTPART\_ALL
- CONFIGURATION:CFTPRIV\_ALL
- CONFIGURATION:CFTPRIV\_ALL
- CONFIGURATION:CFTPROT\_ALL
- CONFIGURATION:CFTRECV\_ALL
- CONFIGURATION:CFTROLE\_ALL
- CONFIGURATION:CFTSEND\_ALL
- CONFIGURATION:CFTSENDI\_ALL
- CONFIGURATION:CFTSNA\_ALL
- CONFIGURATION:CFTSSH\_ALL
- CONFIGURATION:CFTSSL\_ALL
- CONFIGURATION:CFTTCP\_ALL
- CONFIGURATION:CFTTOKEN\_ALL
- CONFIGURATION:CFTUCONF\_ALL
- CONFIGURATION:CFTUIPREF\_ALL
- CONFIGURATION:CFTX25\_ALL
- CONFIGURATION:CFTXLATE\_ALL
- CONFIGURATION:PKICER\_ALL
- CONFIGURATION:PKIENTITY\_ALL
- CONFIGURATION:PKIKEY\_ALL
- FILE\_ALL
- FILTER:CATALOG\_ALL
- FILTER:LOG\_ALL
- SERVICE:ACCOUNT\_SWITCH
- SERVICE:BATCH\_EXECUTE
- SERVICE:CATALOG\_PURGE
- SERVICE:CFTSRV\_ALL
- SERVICE:CFTSRV\_VIEW
- SERVICE:COM\_ALL
- SERVICE:LOG\_SWITCH
- SERVICE:UI\_CONNECT
- TRANSFER\_ALL
- URL\_VIEW

### HelpDesk

This role enables you to view the log, transfers, and the configuration, and groups the following privileges:

- AM:RIGHTS\_VIEW\_SELF
- CONFIGURATION:CFTACCNT\_VIEW
- CONFIGURATION:CFTAPPL\_VIEW
- CONFIGURATION:CFTAUTH\_VIEW
- CONFIGURATION:CFTCAT\_VIEW
- CONFIGURATION:CFTCOM\_VIEW
- CONFIGURATION:CFTCRON\_VIEW
- CONFIGURATION:CFTDEST\_VIEW
- CONFIGURATION:CFTDNA\_VIEW
- CONFIGURATION:CFTDSA\_VIEW
- CONFIGURATION:CFTETB\_VIEW
- CONFIGURATION:CFTEXIT\_VIEW
- CONFIGURATION:CFTFOLDER\_VIEW
- CONFIGURATION:CFTIDF\_VIEW
- CONFIGURATION:CFTLOG\_VIEW
- CONFIGURATION:CFTLU62\_VIEW
- CONFIGURATION:CFTNET\_VIEW
- CONFIGURATION:CFTPARM\_VIEW
- CONFIGURATION:CFTPART\_VIEW
- CONFIGURATION:CFTPROT\_VIEW
- CONFIGURATION:CFTRECV\_VIEW
- CONFIGURATION:CFTSENDI\_VIEW
- CONFIGURATION:CFTSEND\_VIEW
- CONFIGURATION:CFTSNA\_VIEW
- CONFIGURATION:CFTSSH\_VIEW
- CONFIGURATION:CFTSSL\_VIEW
- CONFIGURATION:CFTTCP\_VIEW
- CONFIGURATION:CFTUCONF\_VIEW
- CONFIGURATION:CFTUIPREF\_ALL
- CONFIGURATION:CFTX25\_VIEW
- CONFIGURATION:CFTXLATE\_VIEW
- CONFIGURATION:PKICER\_VIEW
- CONFIGURATION:PKIENTITY\_VIEW
- CONFIGURATION:PKIKEY\_VIEW
- FILTER:CATALOG\_ALL
- FILTER:LOG\_ALL
- SERVICE:CFTSRV\_VIEW
- SERVICE:COM\_VIEW
- SERVICE:UI\_CONNECT
- TRANSFER\_VDPRC

### PartnerManager

This role enables you to create and manage partners, and groups the following privileges:

- AM:RIGHTS\_VIEW\_ALL
- CONFIGURATION:CFTAUTH\_VIEW
- CONFIGURATION:CFTDEST\_ALL
- CONFIGURATION:CFTDNA\_ALL
- CONFIGURATION:CFTDSA\_ALL
- CONFIGURATION:CFTFOLDER\_VIEW
- CONFIGURATION:CFTIDF\_VIEW
- CONFIGURATION:CFTLU62\_ALL
- CONFIGURATION:CFTNET\_VIEW
- CONFIGURATION:CFTPARM\_VIEW
- CONFIGURATION:CFTPART\_ALL
- CONFIGURATION:CFTPROT\_VIEW
- CONFIGURATION:CFTRECV\_VIEW
- CONFIGURATION:CFTSENDI\_VIEW
- CONFIGURATION:CFTSEND\_VIEW
- CONFIGURATION:CFTSNA\_ALL
- CONFIGURATION:CFTSSH\_VIEW
- CONFIGURATION:CFTSSL\_VIEW
- CONFIGURATION:CFTTCP\_ALL
- CONFIGURATION:CFTUIPREF\_VIEW
- CONFIGURATION:CFTX25\_ALL
- CONFIGURATION:CFTXLATE\_VIEW
- CONFIGURATION:PKICER\_ALL
- CONFIGURATION:PKIENTITY\_ALL
- CONFIGURATION:PKIKEY\_ALL
- SERVICE:CFTSRV\_VIEW
- SERVICE:UI\_CONNECT

### Designer

This role enables you to manage flows, and groups the following privileges:

- CONFIGURATION:CFTFOLDER\_ALL
- CONFIGURATION:CFTIDF\_ALL
- CONFIGURATION:CFTPARM\_VIEW
- CONFIGURATION:CFTRECV\_ALL
- CONFIGURATION:CFTSEND\_ALL
- CONFIGURATION:CFTSENDI\_ALL
- CONFIGURATION:CFTUIPREF\_VIEW
- CONFIGURATION:CFTXLATE\_ALL
- SERVICE:CFTSRV\_VIEW
- SERVICE:UI\_CONNECT

### Application

This role enables application to create and execute transfers, and groups the following privileges:

- CONFIGURATION:CFTCOM\_VIEW
- CONFIGURATION:CFTDEST\_VIEW
- CONFIGURATION:CFTLOG\_VIEW
- CONFIGURATION:CFTPARM\_VIEW
- CONFIGURATION:CFTPART\_VIEW
- CONFIGURATION:CFTRECV\_VIEW
- CONFIGURATION:CFTSEND\_VIEW
- CONFIGURATION:CFTUIPREF\_ALL
- FILE\_VIEW
- FILTER:CATALOG\_ALL
- FILTER:LOG\_ALL
- SERVICE:CFTSRV\_VIEW
- SERVICE:UI\_CONNECT
- TRANSFER\_ALL

### Configuration

This section contains information on:

- Security architecture
- Security configuration
- Secure by default configuration
- Product certificates