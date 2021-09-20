{
    "title": "Metadata file",
    "linkTitle": "Metadata file",
    "weight": "240"
}The metadata file is an XML file that contains a `Transfer` element. The elements in the following table must be included in the `Transfer` element unless noted as optional:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Element</th>
         <th>Description</th>
         <th>Valid values</th>
         <th>Notes</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>SourceFileLocation</code>
         </td>
         <td>Path to the transferred file         </td>
         <td>Full path name or path relative to <code>RemoteSharePath</code>         </td>
         <td>See <a href="../c_st_location_of_transferred_file">Location of the transferred file</a>.         </td>
      </tr>
      <tr>
         <td><code>RemoteSharePath</code>
         </td>
         <td>Path to the shared directory on the remote system         </td>
         <td>Full path name         </td>
         <td>Optional. <span>SecureTransport</span> uses this to determine the location of the transferred file. See <a href="../c_st_location_of_transferred_file">Location of the transferred file</a>.         </td>
      </tr>
      <tr>
         <td><code>LocalSharePath</code>
         </td>
         <td>Path to the shared directory on the <span>SecureTransport</span> system         </td>
         <td>Full path name         </td>
         <td>
            <p>Optional.</p>
            <p>Optional for transfers to <span>SecureTransport</span>. <span>SecureTransport</span> uses this to determine the location of the transferred file. See <a href="../c_st_location_of_transferred_file">Location of the transferred file</a>.</p>
         </td>
      </tr>
      <tr>
         <td><code>CycleID</code>
         </td>
         <td>Processing cycle identifier for the file transfer         </td>
         <td>Any valid cycle ID         </td>
         <td><span>SecureTransport</span> uses this cycle ID in events reported to <span>Axway</span> Sentinel.         </td>
      </tr>
      <tr>
         <td><code>Protocol</code>
         </td>
         <td>Name of a file services interface protocol         </td>
         <td>Any protocol defined in the file services interface protocol registry         </td>
         <td><span>SecureTransport</span> displays the corresponding display name in Protocol column of the <em>File Tracking</em> page and in events it sends to <span>Axway</span> Sentinel.         </td>
      </tr>
      <tr>
         <td><code>Mode</code>
         </td>
         <td>File transfer mode         </td>
         <td><code>A</code> for ASCII or <code>I</code> for binary         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>Recipients</code>
         </td>
         <td>Container for <code>Recipient</code> elements         </td>
         <td>N/A         </td>
         <td>Optional. Contains any number of <code>Recipient</code> elements.         </td>
      </tr>
      <tr>
         <td><code>Recipient</code>
         </td>
         <td>A recipient for the file         </td>
         <td>N/A         </td>
         <td>Optional. Contains a <code>Name</code> element and, optionally, a <code>Path</code> element         </td>
      </tr>
      <tr>
         <td><code>Name</code>
         </td>
         <td>Login name of a <span>SecureTransport</span> account to receive the file         </td>
         <td>Any existing account login name         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>Path</code>
         </td>
         <td>Path to the directory where <span>SecureTransport</span> copies the file, relative to the account home folder         </td>
         <td>Path to any directory in the home folder of the named account         </td>
         <td>Optional. The default is the home folder of the account.         </td>
      </tr>
      <tr>
         <td><code>Parameters</code>
         </td>
         <td>Container for <code>Parameter</code> elements         </td>
         <td>N/A         </td>
         <td>Optional. Contains any number of <code>Parameter</code> elements.         </td>
      </tr>
      <tr>
         <td><code>Parameter</code>
         </td>
         <td>A parameter         </td>
         <td>N/A         </td>
         <td>Optional. Contains a <code>Key</code> element and, optionally, a <code>Value</code> element.         </td>
      </tr>
      <tr>
         <td><code>Key</code>
         </td>
         <td>Key ID for the parameter         </td>
         <td>Any string         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>Value</code>
         </td>
         <td>Value of the parameter         </td>
         <td>Any string         </td>
         <td>Optional.         </td>
      </tr>
   </tbody>
</table>

The following is an example of a metadata file:

    <?xml version="1.0" encoding="UTF-8"?>
    <Transfer>
       <SourceFileLocation>/opt/shared/incoming/report-20110704
          </SourceFileLocation>
       <CycleId>2162164</CycleId>
       <Protocol>T3Direct</Protocol>
       <Mode>I</Mode>
       <Recipients>
          <Recipient>
             <Name>acctng</Name>
             <Path>/incoming/reports</Path>
          </Recipient> 
             <Recipient>
             <Name>audit</Name>
          <Path>/incoming/check</Path>
          </Recipient>
       </Recipients>
       <Parameters>
          <Parameter>
             <Key>status</Key>
             <Value>complete</Value>
          </Parameter>
       </Parameters>
    </Transfer>

**Related topic:**

-   [Location of the transferred file](../c_st_location_of_transferred_file)
