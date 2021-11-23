{
    "title": "Configuring protocols",
    "linkTitle": "Configuring protocols",
    "weight": "150"
}{{< Gateway/componentlongname  >}}: Configuration

This topic describes the **Internet protocols** and <span style="font-weight: bold;">Legacy protocols</span> parameters of the configuration menu. These are the parameters that you can set to enable Gateway to communicate using different protocols.

[Activating/deactivating protocols](#Activating_deactivating)

[Internet protocols](#Internet_protocols)

[Legacy protocols](#Legacy_protocols)

[SecureRelay access policy](#SecureRelay_access_policy)

<span id="Activating_deactivating"></span>

## Activating/deactivating protocols

In the configuration menu:

-   To enable a protocol in Gateway, click <span style="font-weight: bold;">Activate</span>.
-   If you no longer want to use a protocol, click <span style="font-weight: bold;">Deactivate</span> to disable it.

<span id="Internet_protocols"></span>

## Connectivity &gt; Internet protocols

To configure a file transfer protocol, select the desired protocol in the left (tree view) pane, then complete the parameter fields in the right pane.

<span id="olh_connectivity_internet_ftp"></span>

### Connectivity &gt; Internet protocols &gt; FTP

1.  Select the required [SecureRelay access policy](#SecureRelay_access_policy).
2.  Specify the ports to use in server mode for this protocol. See [TCP/IP parameters](../config_tcp_ip_paras).
3.  Click <span style="font-weight: bold;">Options...</span> to access <span style="font-style: italic;">[FTP options](../config_ftp_options)</span>.
4.  (optional) Specify the <span style="font-weight: bold;">Listen port range in client active mode</span> in the <span style="font-weight: bold;">Min</span> and <span style="font-weight: bold;">Max</span> fields.
5.  Click <span style="font-weight: bold;">Activate</span> to enable this protocol.
6.  Click <span style="font-weight: bold;">OK</span> or <span style="font-weight: bold;">Apply</span>.

<span id="olh_connectivity_internet_http"></span>

### Connectivity &gt; Internet protocols &gt; HTTP

1.  Select the required [SecureRelay access policy](#SecureRelay_access_policy).
2.  Specify the ports to use for this protocol. See [TCP/IP parameters](../config_tcp_ip_paras).
3.  Click <span style="font-weight: bold;">Options...</span> to access <span style="font-style: italic;">[HTTP options](../config_http_options)</span>.
4.  Click <span style="font-weight: bold;">Activate</span> to enable this protocol.
5.  Click <span style="font-weight: bold;">OK</span> or <span style="font-weight: bold;">Apply</span>.

<span id="olh_connectivity_internet_sftp"></span>

### Connectivity &gt; Internet protocols &gt; SFTP

1.  Select the required [SecureRelay access policy](#SecureRelay_access_policy).
2.  Specify the ports to use for this protocol. See [TCP/IP parameters](../config_tcp_ip_paras).
3.  Click <span style="font-weight: bold;">Advanced...</span> to access <span style="font-style: italic;">[TCP advanced options](../config_tcp_adv_options)</span>.
4.  Click <span style="font-weight: bold;">Activate</span> to enable this protocol.
5.  Click <span style="font-weight: bold;">OK</span> or <span style="font-weight: bold;">Apply</span>.

<span id="olh_connectivity_internet_mail_smtp"></span>

### Connectivity &gt; Internet protocols &gt; Mail &gt; SMTP

1.  Use the following parameters to configure Gateway for sending electronic mail to a mail server using SMTP.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Add Gateway parameters to subject field</p>         </td>
         <td><p>Select this option to add specific Gateway parameters to the <span style="font-style: italic;">Subject</span> field as the default behavior.</p>         </td>
      </tr>
      <tr>
         <td><p>Gateway subject delimiter</p>         </td>
         <td><p>Specify the delimiter character to use for Gateway parameters in the subject field.</p>
<p>For example: <span class="code" style="font-weight: bold;">//XFB</span></p>         </td>
      </tr>
      <tr>
         <td><p>Default SMTP site</p>         </td>
         <td><p>Select the default SMTP Site to use.</p>         </td>
      </tr>
      <tr>
         <td><p>Use S/MIME</p>         </td>
         <td><p>Select this option to apply S/MIME security functions to SMTP transactions.</p>         </td>
      </tr>
      <tr>
         <td><p>Use SecureRelay</p>         </td>
         <td><p>Select this option to use Secure Relay with this protocol.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">Advanced...</span> to access <span style="font-style: italic;">[TCP advanced options](../config_tcp_adv_options)</span>.
2.  Click <span style="font-weight: bold;">Activate</span> to enable this protocol.
3.  Click <span style="font-weight: bold;">OK</span> or <span style="font-weight: bold;">Apply</span>.

<span id="olh_connectivity_internet_mail_pop3"></span>

### Connectivity &gt; Internet protocols &gt; Mail &gt; POP3

1.  Use the following parameters to configure Gateway for the retrieval of electronic mail from a mail server using POP3.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Gateway subject delimiter</p>         </td>
         <td><p>Specify the delimiter character to use for Gateway parameters in the subject field.</p>
<p>For example: <span class="code" style="font-weight: bold;"> //XFB</span></p>         </td>
      </tr>
      <tr>
         <td><p>Use S/MIME</p>         </td>
         <td><p>Select this option to apply S/MIME security functions to POP3 transactions.</p>         </td>
      </tr>
      <tr>
         <td><p>Use SecureRelay</p>         </td>
         <td><p>Select this option to use Secure Relay with this protocol.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">Advanced...</span> to access <span style="font-style: italic;">[TCP advanced options](../config_tcp_adv_options)</span>.
2.  Click <span style="font-weight: bold;">Activate</span> to enable this protocol.
3.  Click <span style="font-weight: bold;">OK</span> or <span style="font-weight: bold;">Apply</span>.

<span id="olh_connectivity_internet_ediint_as1_smtp"></span>

### Connectivity &gt; Internet protocols &gt; EDIInt &gt; AS1 &gt; SMTP

1.  Use the following parameters to configure Gateway for sending electronic mail to a mail server using EDIINT AS1 SMTP.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Use SecureRelay</p>         </td>
         <td><p>Select this option to use Secure Relay with this protocol.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">Advanced...</span> to access <span style="font-style: italic;">[TCP advanced options](../config_tcp_adv_options)</span>.
2.  Click <span style="font-weight: bold;">Activate</span> to enable this protocol.
3.  Click <span style="font-weight: bold;">OK</span> or <span style="font-weight: bold;">Apply</span>.

<span id="olh_connectivity_internet_ediint_as1_pop3"></span>

### Connectivity &gt; Internet protocols &gt; EDIInt &gt; AS1 &gt; POP3

1.  Use the following parameters to configure Gateway for the retrieval of electronic mail from a mail server using EDIINT AS1 POP3.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Use SecureRelay</p>         </td>
         <td><p>Select this option to use Secure Relay with this protocol.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">Advanced...</span> to access <span style="font-style: italic;">[TCP advanced options](../config_tcp_adv_options)</span>.
2.  Click <span style="font-weight: bold;">Activate</span> to enable this protocol.
3.  Click <span style="font-weight: bold;">OK</span> or <span style="font-weight: bold;">Apply</span>.

<span id="olh_connectivity_internet_ediint_as2"></span>

### Connectivity &gt; Internet protocols &gt; EDIInt &gt; AS2

1.  Select the required [SecureRelay access policy](#SecureRelay_access_policy).
2.  Specify the ports to use for this protocol. See [TCP/IP parameters](../config_tcp_ip_paras).
3.  Click <span style="font-weight: bold;">Options...</span> to access <span style="font-style: italic;">[HTTP options](../config_http_options)</span>.
4.  Click <span style="font-weight: bold;">Activate</span> to enable this protocol.
5.  Click <span style="font-weight: bold;">OK</span> or <span style="font-weight: bold;">Apply</span>.

<span id="olh_connectivity_internet_ediint_as3"></span>

### Connectivity &gt; Internet protocols &gt; EDIInt &gt; AS3

1.  Select the required [SecureRelay access policy](#SecureRelay_access_policy).
2.  Specify the ports to use in server mode for this protocol. See [TCP/IP parameters](../config_tcp_ip_paras).
3.  Click <span style="font-weight: bold;">Options...</span> to access <span style="font-style: italic;">[FTP options](../config_ftp_options)</span>.
4.  (optional) Specify the <span style="font-weight: bold;">Listen port range in client active mode</span> in the <span style="font-weight: bold;">Min</span> and <span style="font-weight: bold;">Max</span> fields.
5.  Click <span style="font-weight: bold;">Activate</span> to enable this protocol.
6.  Click <span style="font-weight: bold;">OK</span> or <span style="font-weight: bold;">Apply</span>.

<span id="olh_connectivity_internet_rosettanet_http"></span>

### Connectivity &gt; Internet protocols &gt; RosettaNet &gt; HTTP

1.  Select the required [SecureRelay access policy](#SecureRelay_access_policy).
2.  Specify the ports to use for this protocol. See [TCP/IP parameters](../config_tcp_ip_paras).
3.  Click <span style="font-weight: bold;">Options...</span> to access <span style="font-style: italic;">[HTTP options](../config_http_options)</span>.
4.  Click <span style="font-weight: bold;">Activate</span> to enable this protocol.
5.  Click <span style="font-weight: bold;">OK</span> or <span style="font-weight: bold;">Apply</span>.

<span id="olh_connectivity_internet_rosettanet_mail_smtp"></span>

### Connectivity &gt; Internet protocols &gt; RosettaNet &gt; MAIL &gt; SMTP

1.  Use the following parameters to configure Gateway for sending electronic mail to a mail server using RosettaNet SMTP.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Use SecureRelay</p>         </td>
         <td><p>Select this option to use Secure Relay with this protocol.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">Advanced...</span> to access <span style="font-style: italic;">[TCP advanced options](../config_tcp_adv_options)</span>.
2.  Click <span style="font-weight: bold;">Activate</span> to enable this protocol.
3.  Click <span style="font-weight: bold;">OK</span> or <span style="font-weight: bold;">Apply</span>.

<span id="olh_connectivity_internet_rosettanet_mail_pop3"></span>

### Connectivity &gt; Internet protocols &gt; RosettaNet &gt; MAIL &gt; POP3

1.  Use the following parameters to configure Gateway for the retrieval of electronic mail from a mail server using RosettaNet POP3.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Use SecureRelay</p>         </td>
         <td><p>Select this option to use Secure Relay with this protocol.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">Advanced...</span> to access <span style="font-style: italic;">[TCP advanced options](../config_tcp_adv_options)</span>.
2.  Click <span style="font-weight: bold;">Activate</span> to enable this protocol.
3.  Click <span style="font-weight: bold;">OK</span> or <span style="font-weight: bold;">Apply</span>.

 

<span id="Legacy_protocols"></span>

## Connectivity &gt; Legacy protocols

To configure a file transfer protocol, select the desired protocol in the left (tree view) pane, then complete the parameter fields in the right pane.

<span id="olh_connectivity_legacy_pesite_tcp"></span>

### Connectivity &gt; Legacy protocols &gt; PeSIT E &gt; TCP

1.  Select the required [SecureRelay access policy](#SecureRelay_access_policy).
2.  Specify the ports to use for this protocol. See [TCP/IP parameters](../config_tcp_ip_paras).
3.  Click <span style="font-weight: bold;">Advanced...</span> to access <span style="font-style: italic;">[TCP advanced options](../config_tcp_adv_options)</span>.
4.  Click <span style="font-weight: bold;">Activate</span> to enable this protocol.
5.  Click <span style="font-weight: bold;">OK</span> or <span style="font-weight: bold;">Apply</span>.

<span id="olh_connectivity_legacy_pesite_sna"></span>

### Connectivity &gt; Legacy protocols &gt; PeSIT E &gt; SNA

Refer to [Configuring protocols: SNA LU 6.2](../config_sna_lu_6_2).

<span id="olh_connectivity_legacy_pesitd_tcp"></span>

### Connectivity &gt; Legacy protocols &gt; PeSIT D &gt; TCP

Refer to [Connectivity &gt; Legacy protocols &gt; PeSIT E &gt; TCP](#olh_connectivity_legacy_pesite_tcp).

<span id="olh_connectivity_legacy_pesitd_sna"></span>

### Connectivity &gt; Legacy protocols &gt; PeSIT D &gt; SNA

Refer to [Configuring protocols: SNA LU 6.2](../config_sna_lu_6_2).

 

<span id="olh_connectivity_legacy_odette_tcp"></span>

### Connectivity &gt; Legacy protocols &gt; OFTP (Odette) &gt; TCP

Refer to [Connectivity &gt; Legacy protocols &gt; PeSIT E &gt; TCP](#olh_connectivity_legacy_pesite_tcp).

<span id="olh_connectivity_legacy_pel_tcp"></span>

### Connectivity &gt; Legacy protocols &gt; PEL &gt; TCP

Refer to [Connectivity &gt; Legacy protocols &gt; PeSIT E &gt; TCP](#olh_connectivity_legacy_pesite_tcp).

<span id="olh_connectivity_legacy_pel_sna"></span>

### Connectivity &gt; Legacy protocols &gt; PEL &gt; SNA

Refer to [Configuring protocols: SNA LU 6.2](../config_sna_lu_6_2).

 

<span id="SecureRelay_access_policy"></span>

## SecureRelay access policy

For each protocol that you use for exchanges with your Internet partners, specify the type of access that is allowed for connections to Gateway.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>SecureRelay access policy</p>         </td>
         <td><p>Select the required access policy:</p>
<ul>
<li><span style="font-weight: bold;">SecureRelay is not used</span>: only direct access (via the Gateway port specified in the <span style="font-style: italic;">Gateway port</span> column).</li>
<li><strong>Through SecureRelay only</strong>: access through Secure Relay (via the Gateway port specified in the <span style="font-style: italic;">SecureRelay port</span> column).</li>
<li><span style="font-weight: bold;">Through SecureRelay and directly</span>: both direct access and access through Secure Relay.<br />
If you select this mode you can specify a supplementary access port number for incoming connections to the Secure Relay Router Agent.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span style="font-weight: bold;">Note:</span> Before changing the <span style="font-weight: bold;">SecureRelay access policy</span> for a given protocol, first delete any ports that were previously defined for that protocol.

Related topics

[Configuration: Procedure](../../config_procedure)

[About <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> protocols](../../../protocols_about)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
