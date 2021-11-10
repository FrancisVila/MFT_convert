{
    "title": "Available resources, actions and privileges",
    "linkTitle": "Available resources, actions and privileges",
    "weight": "80"
}The following is a list of available resources in Gateway. Included for each object are associated actions, attributes, and a description.

## Generic resources

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Resource         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadD-Column1-Header1">Resource actions         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Sites Objects         </td>
         <td>In Gateway, to define the parameters of a file transfer, you require a description of the partner for the file exchange. You specify the characteristics of partner sites in Site objects.         </td>
         <td><ul>
<li>Read</li>
<li>Write</li>
<li>Update</li>
<li>Delete</li>
<li>Admin</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Applications Objects         </td>
         <td>When you define a File Transfer Request you can provide certain file system attributes via the Application object         </td>
         <td><ul>
<li>Read</li>
<li>Write</li>
<li>Update</li>
<li>Delete</li>
<li>Admin</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Transfers Objects         </td>
         <td>Gateway provides a set of objects that enable you to create and define the characteristics of a Transfer.         </td>
         <td><ul>
<li>Read</li>
<li>Write</li>
<li>Update</li>
<li>Delete</li>
<li>Admin</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Models Objects         </td>
         <td>Gateway Model objects enable you to group sets of attributes for the creation of Transfer Requests, Decision Rules, Axway Messaging connector objects         </td>
         <td><ul>
<li>Read</li>
<li>Write</li>
<li>Update</li>
<li>Delete</li>
<li>Admin</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Diffusion lists Objects         </td>
         <td>Gateway enables you to create lists of computers that you want to use as destinations for a given type of file.         </td>
         <td><ul>
<li>Read</li>
<li>Write</li>
<li>Update</li>
<li>Delete</li>
<li>Admin</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Users Objects         </td>
         <td>You define each Gateway User by specifying a unique name, an access password and the name of the Profile object with which the User is associated. All Users, apart from the Administrator, must be associated with a specific Profile. All Users associated with the same Profile have identical rights.         </td>
         <td><ul>
<li>Read</li>
<li>Write</li>
<li>Update</li>
<li>Delete</li>
<li>Admin</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Profiles Objects         </td>
         <td>The Profile object defines the type of access rights that a user, or a set of users, has to specific objects or files.         </td>
         <td><ul>
<li>Read</li>
<li>Write</li>
<li>Update</li>
<li>Delete</li>
<li>Admin</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Log Objects         </td>
         <td>The Log file contains a trace of all significant events relating to transfer monitor activities and to the transfers performed.         </td>
         <td><ul>
<li>Read</li>
<li>Write</li>
<li>Update</li>
<li>Delete</li>
<li>Admin</li>
</ul>         </td>
      </tr>
      <tr>
         <td>CGates Objects         </td>
         <td>CGate and CGateGroup objects are identification filters used internally in server mode at the protocol connection level to control the connections of remote partners.         </td>
         <td><ul>
<li>Read</li>
<li>Write</li>
<li>Update</li>
<li>Delete</li>
<li>Admin</li>
</ul>         </td>
      </tr>
      <tr>
         <td>VFD Objects         </td>
         <td>The Virtual File Directory (VFD) is a virtual device that enables you to provide an administrator-controlled view of data organization to specific users via a file directory tree. The VFD comprises directories and files.         </td>
         <td><ul>
<li>Read</li>
<li>Write</li>
<li>Update</li>
<li>Delete</li>
<li>Admin</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Rule Tables Objects         </td>
         <td>A Rule Table object is an ordered list that contains one or more Decision Rules.         </td>
         <td><ul>
<li>Read</li>
<li>Write</li>
<li>Update</li>
<li>Delete</li>
<li>Admin</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Decision Rules Objects         </td>
         <td>In a Decision Rule object, you define one or more events that you want to trigger a specific action.         </td>
         <td><ul>
<li>Read</li>
<li>Write</li>
<li>Update</li>
<li>Delete</li>
<li>Admin</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Proxies Objects         </td>
         <td>In Gateway, you use the Proxy object exclusively in client mode for contacting a proxy server. The protocol settings of a Proxy object define the TCP address and access port for the connection server and the set of connection parameters (for example, the user name and corresponding password).         </td>
         <td><ul>
<li>Read</li>
<li>Write</li>
<li>Update</li>
<li>Delete</li>
<li>Admin</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Trading Partners Objects         </td>
         <td>Provide the information to Gateway necessary for compression, signature, encryption and encapsulation operations you create a Trading Partner object.         </td>
         <td><ul>
<li>Read</li>
<li>Write</li>
<li>Update</li>
<li>Delete</li>
<li>Admin</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Transfer Security Objects         </td>
         <td>Gateway integrates a set of objects that you can use to manage your transfer security requirements: Certificates and keys, Network Profiles, TLS Security Profiles, SSH Security Profiles.         </td>
         <td><ul>
<li>Read</li>
<li>Write</li>
<li>Update</li>
<li>Delete</li>
<li>Admin</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Connections Objects         </td>
         <td>A Connection object contains information describing a protocol session.         </td>
         <td><ul>
<li>Read</li>
<li>Write</li>
<li>Update</li>
<li>Delete</li>
<li>Admin</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Connected Users Objects         </td>
         <td>A Connected User is a virtual object that is identified with the Site used for these connections. All information that single connections carry is accumulated at the Connected User level.         </td>
         <td><ul>
<li>Read</li>
<li>Write</li>
<li>Update</li>
<li>Delete</li>
<li>Admin</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Mailbox         </td>
         <td>Each time Gateway processes a Transfer Request it creates a record of the Request and stores it in the Mailbox.         </td>
         <td><ul>
<li>View</li>
<li>Manage</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Security Certificate object         </td>
         <td>enables you to import a certificate from a file into the local database         </td>
         <td><ul>
<li>Import</li>
<li>Display</li>
<li>Modify</li>
<li>Export</li>
<li>Delete</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Key Object         </td>
         <td>Piece of information used for cryptographic operations         </td>
         <td><ul>
<li>Import</li>
<li>Display</li>
<li>Rename</li>
<li>Delete
Enable/Disable</li>
</ul>         </td>
      </tr>
      <tr>
         <td>User Exits         </td>
         <td>The exits are triggered by different types of Gateway processing event. They enable you to integrate your own custom processing routines with Gateway standard processing activity.         </td>
         <td><ul>
<li>Create</li>
<li>Delete</li>
<li>View</li>
<li>Modify</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Security Profile Object         </td>
         <td>Gateway uses the Security Profile object to establish security for both incoming and outgoing connections.         </td>
         <td><ul>
<li>Create</li>
<li>Delete</li>
<li>View</li>
<li>Modify</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Network Profile         </td>
         <td>Network Profiles associate an incoming network connection request with a Security Profile.         </td>
         <td><ul>
<li>Create</li>
<li>Delete</li>
<li>View</li>
<li>Modify</li>
<li>Filter</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Statistics file         </td>
         <td>Formatted text file that contains records of terminated transfers.         </td>
         <td><ul>
<li>Archive</li>
<li>Suspend</li>
<li>Resume
 </li>
</ul>         </td>
      </tr>
      <tr>
         <td>Audit Objects         </td>
         <td>The Audit file contains a trace of actions performed by users on the <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> configuration (global and objects configuration).         </td>
         <td><ul>
<li>Read</li>
<li>Admin</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Configuration         </td>
         <td><span class="mc-variable suite_variables.GatewayName variable">Gateway</span> configuration objects         </td>
         <td><ul>
<li>Read</li>
<li>Admin</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
