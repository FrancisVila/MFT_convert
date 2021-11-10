{
    "title": "SFTP security",
    "linkTitle": "SFTP security",
    "weight": "250"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

SSH Software provides a secure logon and encrypts the data transfer connection.

SFTP connects to, and communicates exclusively with, the SSH node. No identification is transmitted in SFTP because the authentication of the connecting parties takes place between the SSH nodes.

The connection and data transfer are only secure if solely accredited clients (by certificate or password) are allowed to connect. Bear in mind that if you allow trivial passwords, security is limited.

See the *Security Guide &gt; Security: [SSH protocol](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/SSH/ssh_protocol_about.htm)* for further information (requires login).

## Defending against hammer attacks

A hammer attack can occur when a user floods the server with requests until it can no longer respond to any other users.

### Transfer quotas

Gateway provides Transfer quotas as a way of guarding against hammer attacks on the SFTP protocol. You can configure them either using the exit routine <span style="font-weight: bold;">ExitProtocolConnection</span> or the Gateway Site, CGate, and CGateGroup objects.

Gateway provides four quota parameters for you to set transfer upload or download limits within a designated time period.

The following table describes transfer quota fields. By default, the fields are set to 0, which is equivalent to deactivating the quota restriction.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Transfer quota</p>         </th>
<th class="HeadE-Column1-Header1"><p>Definition</p>         </th>
<th class="HeadD-Column1-Header1"><p>Defense if exceeded</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>max_upload_rate</p>         </td>
         <td><p>Upload quota in KB per minute.</p>         </td>
         <td><p> </p>
<p>All fields refuse the client the right to transfer in the appropriate direction (upload or download) until it returns within the quota limit.</p>         </td>
      </tr>
      <tr>
         <td><p>max_download_rate</p>         </td>
         <td><p>Download quota in KB per minute.</p>         </td>
      </tr>
      <tr>
         <td><p>max_upload_requests_rate</p>         </td>
         <td><p>Maximum number of upload-type transfers that can be requested per minute.</p>         </td>
      </tr>
      <tr>
         <td><p>max_download_requests_rate</p>         </td>
         <td><p>Maximum number of download-type transfers that can be requested per minute.</p>         </td>
      </tr>
   </tbody>
</table>

#### Quota window size

The Gateway SFTP server manages client consumption of these transfer credits for all quotas in one sliding window. The window size is set in the configuration menu **Quota window size** field (specified in minutes). The default is 0, that is, all defenses are disabled irrespective of the quota limits already set.

##### Example

If, for example, the following elements are set:

• **Quota window size** = 10 minutes

• **max\_upload\_requests\_rate** = 8 uploads per minute

Then the Gateway SFTP server verifies that the client does not exceed 80 uploads in any 10-minute interval. If the client sends a request that exceeds this limit, the server automatically activates the defenses, refusing all client new transfer requests. These defenses remain active for the number of minutes necessary for the volume of uploads over the preceding 10-minute period to return within the quota limit.

##### Monitoring User quotas

In the Gateway GUI, you can track user and quota consumption via the **Connected User record**. The interface displays:

• Number of uploads and downloads

• Volume of data transferred

• Percentage of <span class="code" style="font-weight: bold;">max\_upload\_rate </span>and <span class="code" style="font-weight: bold;">max\_download\_rate </span>quotas used

• Percentage of <span class="code" style="font-weight: bold;">max\_upload\_requests\_rate </span>and <span class="code" style="font-weight: bold;">max\_download\_requests\_rate </span>quotas used

Gateway also provides the online command <span class="code" style="font-weight: bold;">pelctl reset\_connected\_user </span>to:

• Reset recorded consumption to zero

• Delete the connection if it is no longer active

This command therefore serves as a mechanism to authorize a client to reconnect after being suspended.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
