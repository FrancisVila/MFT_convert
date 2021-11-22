{
    "title": "SiteMinder integration configuration",
    "linkTitle": "SiteMinder integration configuration",
    "weight": "250"
}CA SiteMinder is a third-party application that controls user access to secured applications and provides a Single Sign-On (SSO) portal. A SSO portal is a Web gateway or proxy that enables users to access multiple secured Web applications using a single user name and password they provide once at the start of the user session.

SecureTransport can be integrated into a SiteMinder SSO environment and use SiteMinder to SSO authenticate and authorize resource access using only HTTP or HTTPS.

> **Note:**
>
> Before configuring SiteMinder settings, be sure to read SiteMinder integration.

Before using {{< SecureTransport/componentshortname  >}} with SiteMinder, you must configure the SiteMinder settings using the {{< SecureTransport/componentshortname  >}} Administration Tool.

> **Note:**
>
> If SecureTransport is deployed in a secure perimeter network (DMZ) configuration, configure the SiteMinder settings on SecureTransport Server as described in this topic. The SiteMinder Settings page is not available on SecureTransport Edge.

1.  Select **Authentication > SiteMinder Settings**.  
    The *CA SiteMinder Setting* page is displayed.
2.  Provide the information as described in the following table:  
    <table>
       <thead>
          <tr>
    <th class="HeadE-Column1-Header1">Name         </th>
    <th class="HeadE-Column1-Header1">Description         </th>
    <th class="HeadD-Column1-Header1">Required/ optional         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td>IP Address         </td>
             <td>The network address of the SiteMinder Policy Server.         </td>
             <td>Required         </td>
          </tr>
          <tr>
             <td>Administrator Username         </td>
             <td>The user name used to connect to the SiteMinder database.         </td>
             <td>Optional         </td>
          </tr>
          <tr>
             <td>Administrator Password         </td>
             <td><p>If a password is required, select Use Password and enter it in the field provided.</p>
    <blockquote>
    <p><strong>Note:</strong></p>
    <p>Exported configuration from SecureTransport 4.x.y systems does not include the SiteMinder administrator password.</p>
    </blockquote>         </td>
             <td>Optional         </td>
          </tr>
          <tr>
             <td>Authorization Port         </td>
             <td>The authorization port for the SiteMinder Policy Server.         </td>
             <td>Required         </td>
          </tr>
          <tr>
             <td>Authentication Port         </td>
             <td>The authentication port for the SiteMinder Policy Server.         </td>
             <td>Required         </td>
          </tr>
          <tr>
             <td>Accounting Port         </td>
             <td>The accounting port for the SiteMinder Policy Server.         </td>
             <td>Required         </td>
          </tr>
          <tr>
             <td>LDAP User Directory         </td>
             <td>Name of the SiteMinder user directory used to retrieve the home folder, user ID, and group ID.         </td>
             <td>Optional         </td>
          </tr>
          <tr>
             <td>Agent Name         </td>
             <td>The name for the SiteMinder agent that {{< SecureTransport/componentshortname  >}} should use when connecting to the SiteMinder Policy Server.         </td>
             <td>Required         </td>
          </tr>
          <tr>
             <td>Agent Type         </td>
             <td>For SiteMinder protocol version 4 the shared secret used to communicate with the SiteMinder Policy Server. For version 5, the path to <code>SmHost.conf</code>.         </td>
             <td>Required         </td>
          </tr>
          <tr>
             <td>Shared Secret         </td>
             <td>The password for the SiteMinder agent that {{< SecureTransport/componentshortname  >}} uses to connect to the Policy Server.         </td>
             <td>Required         </td>
          </tr>
          <tr>
             <td>Maximum Connections         </td>
             <td>The maximum number of SiteMinder connections that {{< SecureTransport/componentshortname  >}} can have open simultaneously. This does not limit the number of users who can log in to the {{< SecureTransport/componentshortname  >}} Server using the Site Minder SSO portal.         </td>
             <td>Required         </td>
          </tr>
          <tr>
             <td>Connection Timeout         </td>
             <td>The amount of time (in seconds) that a SiteMinder connection can be idle before it is closed. The default is 30 seconds. This is independent of user session timeout.         </td>
             <td>Required         </td>
          </tr>
          <tr>
             <td>File Storage Root Path         </td>
             <td>The segment of the absolute URI that is removed before it is submitted to the SiteMinder Policy Server for authorization. If the entire absolute URI is submitted for authorization, type <code>/</code> in this field.         </td>
             <td>Required         </td>
          </tr>
          <tr>
             <td>SiteMinder Path Prefix         </td>
             <td><p>After the File Storage Root Path is removed, but prior to SiteMinder authorization, this entry is prefixed to the absolute URI. For example, if the absolute URI is <code>/mnt/ab/user1</code>, the File Storage Root Path is <code>/mnt/ab</code>, and the SiteMinder Path Prefix is <code>/root</code>; then <code>/root/user1</code> is sent to SiteMinder for authorization. If this box is left blank, no prefix is applied to the URI prior to authorization.</p>
    <blockquote>
    <p><strong>Note:</strong></p>
    <p>When SiteMinder is enabled, all SecureTransport users must have GET access to the path specified in the SiteMinder Path Prefix to successfully log in. If this setting is left blank, then users must have GET access to /. The SiteMinder administrator must set up the SiteMinder Policy Server accordingly.</p>
    </blockquote>         </td>
             <td>Optional         </td>
          </tr>
          <tr>
             <td>Default Home Folder         </td>
             <td><p>The absolute URI of the default home folder of the local user.</p>
    <p>The default home folder is used when a home folder is not supplied by the SiteMinder Policy Server.</p>
    <p><strong>Requirements:</strong> </p>
    <ul>
    <li>The folder must be created manually on the machine.</li>
    <li>On Windows, the folder should not use shared storage.</li>
    <li>On Linux, the permissions of the folder must be set to “777” on all nodes in the cluster.</li>
    </ul>         </td>
             <td>Required         </td>
          </tr>
          <tr>
             <td>Default Local User ID         </td>
             <td><p>The numeric user ID (UID) of a user that has full read/write access to the directory specified as the File Storage Root Path and its subdirectories. This default is used only if a UID is not supplied by SiteMinder.</p>
    <blockquote>
    <p><strong>Note:</strong></p>
    <p>On Windows, type the name of the respective virtual user. Windows does not support UIDs.</p>
    </blockquote>         </td>
             <td>Required         </td>
          </tr>
          <tr>
             <td>Default Local Group ID         </td>
             <td>The numeric group ID (GID) of a user that has full read/write access to the directory specified in the File Storage Root Path and its subdirectories. If no UID or GID are supplied by SiteMinder, these defaults are used for all file operations (including ownership of new files) performed by {{< SecureTransport/componentshortname  >}} for users authenticated by SiteMinder.         </td>
             <td>Required         </td>
          </tr>
          <tr>
             <td>Explicitly uses SiteMinder Attributes         </td>
             <td><p>When selected, SecureTransport uses the values specified in the <em>User Attribute Names</em> section.</p>
    <p>If not selected, and</p>
    <ul>
    <li>if the user is assigned to an account template, the User ID, Group ID, and Home Folder are determined from the template.</li>
    <li>if the user is not assigned to an account template, the default home folder, local user ID, and local group ID are used.</li>
    </ul>
    <p>The state of the checkbox has no effect on SiteMinder users mapped as virtual users.</p>         </td>
             <td>Optional         </td>
          </tr>
          <tr>
             <td>Home Folder Attribute         </td>
             <td><p>SiteMinder returns information about the user as name=value pairs. The attributes define the name part of the pair which must be added manually.</p>
    <p>In <code>Home Folder Attribute</code>, you should provide the name of the SiteMinder attribute which value is the absolute URI of the user's home folder.</p>
    <p><strong>Requirements:</strong> </p>
    <ul>
    <li>The folder must be created manually on the machine.</li>
    <li>On Windows, the folder should not use shared storage.</li>
    <li>On Linux, the permissions of the folder must be set to “777” on all nodes in the cluster.</li>
    </ul>
    <blockquote>
    <p><strong>Note:</strong></p>
    <p>When changing Home Folder Attribute, the Transaction Manager should be restarted in order for the changes to be applied.</p>
    </blockquote>
    <blockquote>
    <p><strong>Note:</strong></p>
    <p>If Home Folder Attribute, Group ID Attribute and User ID Attribute are left blank, and the attributes therefore not defined, the default Home Folder, Local User ID, and Local Group ID are used.</p>
    </blockquote>         </td>
             <td>Optional         </td>
          </tr>
          <tr>
             <td>User ID Attribute         </td>
             <td>Optional         </td>
          </tr>
          <tr>
             <td>Group ID Attribute         </td>
             <td>Optional         </td>
          </tr>
       </tbody>
    </table>
3.  Click **Update SiteMinder Settings**.  
    To use one or two more SiteMinder servers for failover, specify server configuration parameters that correspond to the fields described above. The names of the parameters for the second server start with `Siteminder.PolicyServers.Second.PolicyServer`. The names for the third server start with `Siteminder.PolicyServers.Third.PolicyServer`. The final parts of the names are given in the following table:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Sever configuration parameter         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Enable SiteMinder Module         </td>
         <td><code>enable</code>         </td>
      </tr>
      <tr>
         <td>IP Address         </td>
         <td><code>host</code>         </td>
      </tr>
      <tr>
         <td>Administrator Username         </td>
         <td><code>adminUsername</code>         </td>
      </tr>
      <tr>
         <td>Administrator Password         </td>
         <td><code>adminPassword</code>         </td>
      </tr>
      <tr>
         <td>Authorization Port         </td>
         <td><code>authorizationPort</code>         </td>
      </tr>
      <tr>
         <td>Authentication Port         </td>
         <td><code>authenticationPort</code>         </td>
      </tr>
      <tr>
         <td>LDAP User Directory         </td>
         <td><code>ldapUserDirectory</code>         </td>
      </tr>
      <tr>
         <td>Maximum Connections         </td>
         <td><code>maxConnections</code>         </td>
      </tr>
      <tr>
         <td>Connection Timeout         </td>
         <td><code>timeout</code>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> If more than one SiteMinder server is configured in a server that is upgraded from SecureTransport 4.x.y or in configuration that is imported from a SecureTransport 4.x.y server, set the Siteminder.PolicyServers.Second.PolicyServer.enable and the Siteminder.PolicyServers.Third.PolicyServer.enable system configuration parameters to true as required.

There are also parameters for `minConnections` and `connectionsStep` which are not set in the *CA SiteMinder Setting* page.
