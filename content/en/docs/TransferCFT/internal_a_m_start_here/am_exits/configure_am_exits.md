{
    "title": "Configuring the exit",
    "linkTitle": "Configuring the exit",
    "weight": "210"
}This section describes how to configure access management when not using Central Governance.

To enable an Access Management exit, set the uconf parameters described in this page.

From the Administration pane in the graphical user interface, select Unified Configuration. The Unified Configuration window is displayed.

Double-click in a Unified Configuration window field to begin editing parameters.

Configure the AM exit using the parameters in the following table.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
               <li>Access Management exit parameters               </li>
</th>
         <th>Value </th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>am.exit.libpath         </td>
         <td>          </td>
         <td>The absolute path of the dynamic library.         </td>
      </tr>
      <tr>
         <td>am.exit.check_login         </td>
         <td>Yes/No         </td>
         <td>Indicate if the login must be checked through the AM exit.         </td>
      </tr>
      <tr>
         <td>am.exit.check_permissions         </td>
         <td>Yes/No         </td>
         <td>Indicate if permissions must be checked though the AM exit.         </td>
      </tr>
      <tr>
         <td>am.exit.custom.tracelevel.value         </td>
         <td>Default: 1         </td>
         <td>
            <p>Trace level where:</p>
            <ul>
               <li>1=ERR               </li>
               <li>2=WRN               </li>
               <li>3=INF               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>am.exit.custom.rbac_fname.value         </td>
         <td>          </td>
         <td>Path to the RBAC flat file used by the Access Management exit sample.         </td>
      </tr>
      <tr>
         <td>am.exit.custom.ldap_host.value         </td>
         <td>          </td>
         <td>LDAP server hostname/IP address that is used by the Access Management exit sample.         </td>
      </tr>
      <tr>
         <td>am.exit.custom.ldap_port.value         </td>
         <td>          </td>
         <td>LDAP server port that is used by the Access Management exit sample.         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When the AM exit is enabled these conditions apply:         </td>
      </tr>
</table>

-   uconf:am.exit.check\_login=No: the native authentication procedure is still performed
-   uconf:am.exit.check\_permissions=No: all privileges are granted for the current user

Set the type parameter: am.type = exit

1.  **Important**: Remember that the am.type is the last parameter to set when activating an AM exit and the first to unset when deactivating it.
2.  Restart the Transfer CFT server and Transfer CFT UI (Copilot) server.

Example Access Management exit configuration

1.  Using command line set the am.type to none.  
    **CFTUTIL UCONFSET ID=am.type, VALUE=none**
2.  Configure the library location and the Access Management exit usage.  
    CFTUTIL UCONFSET ID=am.exit.libpath, VALUE=&lt;location\_of\_dynamic\_library>  
    CFTUTIL UCONFSET ID=am.exit.check\_login, VALUE=Yes  
    CFTUTIL UCONFSET ID=am.exit.check\_permissions, VALUE=Yes
3.  Enable the Access Management exit.  
    **CFTUTIL UCONFSET ID=am.type, VALUE=exit**

### Using the custom AM exit sample

This section presents parameters that you may need to set if you are creating an EXIT based on the examldap.c sample. The examldap.c sample is built with the OpenLDAP library, which Axway does not deliver. To use, compile this library and add it to the LD\_LIBRARY\_PATH.

-   am.exit.custom.ldap\_base: The top level of the LDAP directory tree is the base, referred to as the "base DN". Enter the base (DN) to authenticate on the connected LDAP server, which defines which LDAP tree node to use as the root node. Example: dc=example,dc=com
-   am.exit.custom.ldap\_login\_dn\_format: The user DN format used to search for a user DN on the LDAP server.   
    For example, if a user is identified by cn=theUser,ou=people,dc=example,dc=com, set am.exit.custom.ldap\_login\_dn\_format to "cn=%s,ou=people,dc=example,dc=com"
-   am.exit.custom.ldap\_get\_roles\_filter: The filter used to retrieve the groups that a given user belongs to.   
    For example, if the filter "(&(objectClass=group)(member=cn=theuser,ou=people,dc=example,dc=com))" returns the list of groups for the user "theUser", set am.exit.custom.ldap\_get\_roles\_filter to "(&(objectClass=group)(member=cn=%s,ou=people,dc=example,dc=com))"

Related topics

[About Access Management exits](..//transfercft/internal_a_m_start_here/am_exits)
