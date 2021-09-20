{
    "title": "Address Book use cases",
    "linkTitle": "Address Book use cases",
    "weight": "350"
}This topic outlines Address Book use cases. In all of the use cases, only Local and LDAP sources are enabled.

## Local user sends an AdHoc package to recipients

Assuming that the global Address Book settings are taken into consideration and the user’s Address Book setting is Default. At the global configuration level a LDAP source is enabled and **Allow collaboration with non-Address Book recipients** is selected. A user can send AdHoc packages to all entries available in its address book (the LDAP source) and to external users.

When the user creates a draft message, a list of the available Address Book entries that can be selected as recipients is displayed. In this case, the user can also type in email addresses that do not exist in their configured Address Book.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If the total number of recipients (resolved email addresses) exceeds the value of the <code>AddressBook.Limit.AdHoc.Recipients</code> configuration option, the send operation will fail and an error message will be displayed to the user stating the reason for the failure.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If <strong>Allow collaboration with non-Address Book recipients</strong> is not selected, the user is not allowed to type email addresses in recipient fields - only Address Book contacts can be selected.         </td>
      </tr>
</table>

For additional information, refer to the *SecureTransport Web Client User Guide*.

## Local user in a Business Unit sends AdHoc package to recipients

Assuming that the business unit level Address Book settings are taken into consideration and the account level Address Book settings are Default. At the business unit level, the Address Book settings are **Custom** and a Local source is assigned. **Allow collaboration with non-Address Book recipients** is not selected for the business unit. When the Local source type is **All Business Units**, the user can send mails to all SecureTransport accounts that have email addresses configured. When the Local source type is **User's own business unit**, the user can send mails only to accounts in the same business unit. The list of available contacts will be displayed to the user. The user will not be able to type external emails as this type of collaboration is not allowed for its business unit.

## Local user shares a folder

As well as sending mails, an account can share folders to defined recipients. The server configuration option `SharedFolders.AllowCollaboration` should be **true**. This is valid for global and account level. If an account is in a business unit, the business unit option **Allow collaboration with non-Address Book recipients** should be selected. Then Address Book settings can regulate whether a folder will or will not be shared with the list of recipients.

When the user starts to type in shared folder collaborators, a list of Address Book contact names are displayed to the end user. Each of the listed contacts can be selected as collaborators.

If the **Allow collaboration with non-Address Book recipients** option is enabled for the user, the user will be able to type in email addresses and specify them as collaborators.

If the number of specified collaborators exceeds the `AddressBook.Limit.AdHoc.Recipients` option value, the share operation will fail and an error message will be displayed to the user stating the reason for the failure.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If the <strong>Allow people to view collaborators</strong> option is enabled, only collaborators’ email addresses will be displayed, display names will not be shown even if collaborators are part of the address book.         </td>
      </tr>
</table>

For additional information, refer to the *SecureTransport Web Client User Guide*.

## LDAP user shares a folder

For LDAP sources, the SecureTransport administrator can specify one of the already defined LDAP domains or the **Logged In (current domain)** option. When an LDAP user is logged in to SecureTransport and the **Logged In** domain is set as an Address Book source, all members of the same LDAP server will be displayed as Address Book entries.

Assuming that account settings are taken into consideration - LDAP users are mapped to an account template which has custom Address Book settings. An LDAP source **Logged In (current domain)** is assigned to the account template. The LDAP user which is mapped to the account template can share folders with all other users and groups defined in the same LDAP domain.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If the total number of resolved collaborators exceeds the value of the <code>AddressBook.Limit.AdHoc.Recipients</code> configuration option, the share operation will fail and an error message will be displayed to the user stating the reason for the failure.         </td>
      </tr>
</table>

## Sending and AdHoc package through REST API

The end-user REST API is able to identify Address Book entries by their IDs. When sending a message through REST API recipients can be: user entry IDs, group entry IDs, and email addresses. Email addresses will be filtered out if they are not part of the Address Book and the user is not allowed collaboration with external users. The list of user’s available contacts is displayed by making a REST call to `/addressBook`.

**Create message draft:**

     POST/api/v1.4/mailbox/messagesPOST DATA:to=petya@sofia-pso.tumbleweed.com&cc=<group_entry_id>&bcc=<user_entry_id>&subject=from+api&message=sample+message&security=ANONYMOUS_LINK&question=+What+is+the+name+of+your+best+friend+from+childhood%3F+&answer=&expiration=86400RESPONSE:http://10.232.3.211:8080/api/v1.4/mailbox/messages200 OK
    Headers
    Response body{
     "info": "Draft was successfully created",
     "messageId": "6a5467d4a084445687b1cdc0cd11f3a3"
    }

Consider the following use case:

A user creates a draft and specifies an email address in the **To** recipient category, an Address Book entry ID in **CC** and an Address Book group ID in **BCC**. When the user sends the message the following happens:

-   If the email address specified in **To** does not belong to any entry of the current user’s Address Book, the message will be sent to that email address only if the **Allow collaboration** option is enabled for this user.
-   The group ID specified in **CC** will be searched in user’s Address Book and if it is found, it will be resolved to all users email addresses that belong to this group.
-   The user ID specified in **BCC** will be searched in user’s Address Book and if it is found, it will be resolved to corresponding entry email address.
-   The message will be sent to all resolved email addresses.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If the total number of resolved collaborators exceeds the value of the <code>AddressBook.Limit.AdHoc.Recipients</code> configuration option, the share operation will fail and an error message will be displayed to the user stating the reason for the failure.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If <strong>Allow Collaboration</strong> is turned off and the user tries to send mail to an external user, the user will be removed from recipients list and a warning message will be displayed in the server log.         </td>
      </tr>
</table>

## Sharing a folder through REST API

When sharing a folder through REST API collaborators can be user entry IDs, group entry IDS, and email addresses. Email addresses will be filtered out if they are not part of the Address Book and the user is not allowed collaboration with external users. The list of user’s available contacts is displayed by making a REST call to `/addressBook`.

Example request for sharing folder (`sharedFolder`) with an Address Book user entry:

    PUT/api/v1.4/shares/sharedFolderDATA:‘{
     "users": [
      "<user_entry_id>"
     ],
     "shareRights": 7,
    "notifications": 1,
    "ownerNotifications": 1,
    "showCollaboratorsToAll": true
    }’

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Only collaborators’ email addresses will be listed when getting sharing metadata for the specified folder, display names will not be showed even if collaborators are part of the Address Book.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If the total number of resolved collaborators exceeds the value of the <code>AddressBook.Limit.AdHoc.Recipients</code> configuration option, the share operation will fail and an error message will be displayed to the user stating the reason for the failure.         </td>
      </tr>
</table>
