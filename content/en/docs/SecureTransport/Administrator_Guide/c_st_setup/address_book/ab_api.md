{
    "title": "Address Book REST API",
    "linkTitle": "Address Book REST API",
    "weight": "360"
}This topic provides Address Book administrator and end user REST API examples and provides REST API support information for Address Book recipients.

## Administrator REST API

The Address Book functionality introduces the following REST API endpoints which allow configuring and assigning address book data sources on all configuration levels:

-   Address Book Global Registry REST API  
    **GET** `/addressBookSources` - Lists all available Address Book data sources.  
    **GET** `/addressBookSources/<ABSourceId>` - Gets an Address Book data source.  
    **POST** `/addressBookSources/<ABSourceId>` - Modifies properties: enabled, group.
-   Business Unit Address Book REST API  
    **GET** `/businessUnit/<name>/addressBookSources` - Gets list of the assigned Address Book sources  
    **PUT** `/businessUnit/<name>/addressBookSources/` - &lt;set of Address Book entries in the body> - replaces all assigned to a business unit.  
    **GET** `/businessUnit/<name>/addressBookSources/<ABSourceId>` - Gets an Address Book source assigned to a business unit.  
    **POST** `/businessUnit/<name>/addressBookSources/<ABSourceId>` - Assigns and updates an Address Book source to a business unit. The body may contain the parent group.  
    **DELETE** `/businessUnit/<name>/addressBookSources/<ABSourceId>` - Removes an Address Book source from those assigned to a business unit.
-   Account Address Book REST API  
    **GET** `/accounts/<name>/addressBookSources/` - Gets list of assigned Address Book sources to an account.  
    **PUT** `/accounts/<name>/addressBookSources/` - &lt;set of Address Book entries in the body> - replaces all assigned.  
    **GET** `/accounts/<name>/addressBookSources/<ABSourceId>` - Gets an Address Book source assigned to an account.  
    **POST** `/accounts/<name>/addressBookSources/<ABSourceId>` - Assigns or updates an Address Book source to an account. The body may contain the parent group property.  
    **DELETE** `/accounts/<name>/addressBookSources/<ABSourceId>` - Removes an Address Book source from the list of assigned sources to an account.  
    **GET** `/accounts/<accountName>/addressBook/contacts` - Get address book contacts of a specified account entity.  
    **POST** `/accounts/<accountName>/addressBook/contacts` - Create address book contacts to a specified account entity.  
    **DELETE** `/accounts/<accountName>/addressBook/contacts/<id>` - Delete an address book contact of an account entity.  
    **PUT** `/accounts/<accountName>/addressBook/contacts/<id>` - Update an address book contact of an account entity.
-   Address Book global settings  
    **GET** `/addressBookSources/settings/` - Gets `AddressBook.AllowCollaboration` and `AddressBook.Enabled` server configurations.  
    **POST** `/addressBookSources/settings/<name>` - Updates `AddressBook.AllowCollaboration` server configuration.

## End User REST API

The following endpoints are exposed for the end user REST API:

-   **GET** `/addressBook` - Lists all available contacts for the given account.

-   **GET**`/addressBook?displayName=test%K&mail=test@axway.com&group=Axway&type=user&orderBy=email&limit=10&offset=0` - Search for all entries matching all parameters together. The search is case sensitive for all sources except for LDAP sources. The logical operation between the parameters is AND.

-   **GET** `/addressBook?searchFor=test&limit=10&offset=0` - Searches all entries which `displayName`, email or group contain the given value. The search is case insensitive. The search phrase is looked up anywhere in the fields `displayName`, email, and group (wildcard search), except for LDAP sources where it is looked up in the beginning of these fields only (wildcard is at the end of the search phrase). The logical operation between the fields is OR.  
    

    <table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter Name</th>
         <th>Description</th>
         <th>Type</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>displayName</code>
         </td>
         <td>Optional. Case sensitive exact search by <code>displayName</code> field.         </td>
         <td>String         </td>
      </tr>
      <tr>
         <td><code>mail</code>
         </td>
         <td>Optional. Case sensitive exact search by <code>mail</code> field.         </td>
         <td>String         </td>
      </tr>
      <tr>
         <td><code>parentGroup</code>
         </td>
         <td>Optional. Case sensitive, exact search by <code>parentGroup</code> field.         </td>
         <td>String         </td>
      </tr>
      <tr>
         <td><code>type</code>
         </td>
         <td>Optional. Case insensitive search by <code>type</code>. The <code>type</code> can be either a user or a group.         </td>
         <td>String         </td>
      </tr>
      <tr>
         <td><code>orderBy</code>
         </td>
         <td>Optional. Specify the sort order of the result. Could be <code>displayName</code> or <code>email</code>.         </td>
         <td>String         </td>
      </tr>
      <tr>
         <td><code>limit</code>
         </td>
         <td>Optional. Page size for pagination. If not specified a default value will be set.         </td>
         <td>Integer         </td>
      </tr>
      <tr>
         <td><code>offset</code>
         </td>
         <td>Optional. Starting index of the pagination. If not specified a default value will be set.         </td>
         <td>Integer         </td>
      </tr>
      <tr>
         <td><code>searchFor</code>
         </td>
         <td>Optional. Case insensitive, wildcard search between <code>group</code>, <code>displayName</code>, and <code>mail</code> parameters.         </td>
         <td>String         </td>
      </tr>
   </tbody>
</table>

-   **GET** `/addressBook/count` - Returns the count of all Address Book entries from all enabled Address Book sources assigned to the current user.

-   **GET** `/addressBook/<id>` - Gets an address book entry by ID.

-   **GET** `/addressBook/myself` - Returns map of Address Book settings with their corresponding values. This includes the following:
    -   `addressBookEnabled` – A flag indicating if Address Book is enabled.
    -   `addressBookCollaborationAllowed` – A flag indicating if collaboration with external recipients is allowed for the given user.
    -   `addressBookMinSearchLength` – Specifies the minimum search string length when performing wildcard search for Address Book entries.
    -   `addressBookMaxDisplayEntries` – Specifies the maximum limit of Address Book entries displayed in a single page.
    -   `addressBookMaxDisplayPages` – Specifies the maximum limit of Address Book pages in a single request.

Address Book entry schema:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>AddressBookEntry {<br>    id: addressBookSourceId:addressBookEntryId,<br>    displayName,<br>    mail,<br>    parentGroup,<br>    type,<br>    customAttr1,<br>    customAttr2,<br>    customAttr3<br>}</br></br></br></br></br></br></br></br></br>         </td>
      </tr>
   </tbody>
</table>

**Note:**

The following methods are also available for the `/addressBook` end user REST resource. They are not implemented in SecureTransport 5.3.6 and earlier.

-   **POST** `/addressBook/` - Creates a new user specific entry. The Address Book provider to which entry will be created will generate `ABEntry` ID. The Address Book source is defined by `parentGroup` property mapping.
-   **PUT** `/addressBook/<id>` - Updates the user specific entry.
-   **DELETE** `/addressBook/<id>` - Deletes the user specific entry.

For each one of them the SecureTransport server returns a response status **403 Forbidden**.

## Support for Address Book recipients

Whenever an Address Book user inputs a group or display name either as an email recipient or shared folder collaborator, SecureTransport is able to resolve the recipients email addresses. If the given group members count exceed a predefined value, an error message is shown to the end user and the operation is aborted. A server configuration option is exposed for setting that value - `AddressBook.Limit.AdHoc.Recipients`.

Whenever an end user sends a mail or shares a folder with group or display name in its recipients list, the REST call includes the Address Book entry IDs which corresponds to the names. If the list of recipients does not include Address Book entries, the REST call contains the actual email addresses. This allows the SecureTransport back end to handle cases with recipients not in the Address Book as well as recipients defined in the Address Book, or to determine if the Address Book is enabled or not.

When the client sends a request with Address Book entry IDs and email addresses, all package recipients are stored in the `.stfs `attributes and later when a list operation is performed the response contains the stored recipients (for example, IDs as well as email addresses). If sharing a folder, the SecureTransport will always return the email addresses.
