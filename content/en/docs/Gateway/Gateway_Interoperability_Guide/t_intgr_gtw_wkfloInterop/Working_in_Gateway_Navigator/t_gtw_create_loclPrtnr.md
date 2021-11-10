{
    "title": "Creating a Local Trading Partner",
    "linkTitle": "Creating a Local Trading Partner object",
    "weight": "130"
}[About the Gateway Local Partner object](#About)

[Gateway GUI procedure](#Gateway_gui)

[Gateway command line procedure](#Gateway_commandline)

<span id="About"></span>

## About the Gateway Local Partner object

In the Local Trading Partner object you specify local identification information.

You use this information to communicate with remote partners.

<span id="Gateway_gui"></span>

## Gateway GUI procedure

In the left pane of the Gateway Navigator main window, click to expand the **Partner Management** node.

Right-click the **Trading Partners** sub-node and from the context menu select **New**.

From the context menu, select the type of partner.

View available partner types

-   SMIME partner
-   AS1 partner
-   AS2 partner
-   AS3 partner
-   RosettaNet partner
-   SWIFTNet partner
-   OFTP partner (for OFTP R2.0 security services)

When you select a partner type, Gateway displays the *Local Trading Partner* properties window. The parameters displayed depend on the type of partner (protocol).

Complete the fields of the Trading Partner window.

View fields for S/MIME, AS1, AS2, AS3, RosettaNet and OFTP

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Definition</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Identification criteria</p>         </td>
      </tr>
      <tr>
         <td><p>Alias</p>         </td>
         <td><p>Enter a name for the Trading Partner object to use for local identification operations. The name must be unique.</p>
<p>Gateway stores this alias as part of the data of each Transfer Request. You can use the alias as a substitute for the partner name parameter when depositing Transfer Requests.</p>         </td>
      </tr>
      <tr>
         <td><p>Format</p>         </td>
         <td><p>This field displays the protocol format that you selected when creating the new Trading Partner</p>         </td>
      </tr>
      <tr>
         <td><p>Local Partner</p>         </td>
         <td><p>Select this option (local Trading Partner object).</p>         </td>
      </tr>
      <tr>
         <td><p>Name/Email</p>         </td>
         <td><p>For S/MIME or AS1, enter an email address.</p>
<p>For other protocols, enter a unique name for the Trading Partner object.</p>
<p>Maximum: 128 characters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Comments</strong></p>         </td>
         <td><p>Optional</p>
<p>Enter a free-text description of the Trading Partner object.<br />
Maximum: 80 alphanumeric characters.<br />
This description is included in the displayed list of available Trading Partners.</p>         </td>
      </tr>
      <tr>
         <td><p>Certificate/Key</p>
<p>The fields displayed depend on the type of partner and the selected options.</p>         </td>
      </tr>
      <tr>
         <td><p>Use dual certificates</p>         </td>
         <td><p>Click this button to toggle between the use of single or dual certificates. The effect of this button varies according to the context:</p>
<p>If you are creating a <span style="font-weight: bold;font-style: italic;">local</span> partner and you...</p>
<ul>
<li>select <strong>Use dual certificates</strong>:<br />
A signing certificate is used to sign what is sent, and an encryption certificate is used to decrypt what is received.</li>
<li>do <span style="font-weight: bold;font-style: italic;">not</span> select <strong>Use dual certificates</strong>:<br />
A single certificate is used to sign what is sent, and is used to decrypt what is received.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Certificate:<br />
Type</p>         </td>
         <td><p>This field is visible when you do not select the Use dual certificates button.</p>
<p>Select a single certificate type to handle both outgoing and incoming messages:</p>
<ul>
<li>None</li>
<li>Secs alias<span style="font-weight: normal;">: local Axway Gateway PKI</span></li>
<li>PassPort PS entity<span style="font-weight: normal;">: for use with the PassPort PS server. Refer to the Axway PassPort documentation for details.</span></li>
<li>PassPort PS certificate<span style="font-weight: normal;">: for use with the PassPort PS server. Refer to the Axway PassPort documentation for details.</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Certificate:<br />
Name</p>         </td>
         <td><p>This field is visible when you do <strong>not</strong> select the Use dual certificates button.</p>
<p>Enter the name of the certificate to be used to handle both outgoing and incoming messages.</p>         </td>
      </tr>
      <tr>
         <td><p>Certificate:<br />
Key password</p>         </td>
         <td><p>This field is visible when you do <strong>not</strong> select the Use dual certificates button.</p>
<p>Enter the password of the certificate key to be used to handle both outgoing and incoming messages.</p>
<p>This parameter is not available if you select <strong>SECS ALIAS</strong> as the <span style="font-style: italic;">Certificate Type.</span></p>         </td>
      </tr>
      <tr>
         <td><p>Signing algo</p>         </td>
         <td><p>This field is visible when you select any option other than <strong>none</strong> from the Certificate: Type field.</p>
<p>Select the algorithm to use for signing:</p>
<ul>
<li>SHA1 with RSA <span style="font-weight: normal;">(default)</span></li>
<li>MD5 with RSA</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Use multiple certificates</p>         </td>
         <td><p>Only if you are using PassPort PS</p>
<p>Select this option to use multiple certificates.</p>
<p>Refer to the Axway PassPort documentation for details.</p>         </td>
      </tr>
      <tr>
         <td><p>Advanced parameters...:<br />
Local file location for encoding/decoding</p>
<p>Click the <strong>Advanced...</strong> button to display the following two fields.</p>
<p>These fields enable you to specify the directory and name format of the file where transfers are processed for encoding (outgoing files) and decoding (incoming files).</p>
<p>You may want to specify a secure directory for this file, keeping in mind that the files that are decoded in this directory can be read by malicious intruders.</p>
<p>If you do not specify a directory, Gateway creates the files in<span style="font-family: monospace;"> &lt;Gateway install directory&gt;\runtime\tmp</span></p>         </td>
      </tr>
      <tr>
         <td><p>Directory path</p>         </td>
         <td><p>Enter the local physical path of the directory where transferred files are encoded and decoded.</p>         </td>
      </tr>
      <tr>
         <td><p>File name pattern</p>         </td>
         <td><p>Enter a specific file name format to enable you to identify the transferred file in the specified out directory.</p>         </td>
      </tr>
   </tbody>
</table>

Click **OK**.  
Gateway creates a new Trading Partner object with the specified characteristics.

<span id="Gateway_commandline"></span>

## Gateway command line procedure

To create a Local Trading Partner object via the command line, use the `peladm create_tradepart` command.

For details of command line use, refer to the Axway Gateway online documentation.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
