{
    "title": "Post registration operations",
    "linkTitle": "Post registration operations ",
    "weight": "200"
}In addition to registration, there are other types of recurring exchanges that occur between Transfer CFT and Central Governance or Flow Manager.

-   Configuration and flow deployment
-   SSL certificate renewal
-   Product updates (Central Governance only)

## Configuration and flow deployment

From Central Governance you can modify Transfer CFT configuration and create flows. Deploying these pushes these modifications (for example, the equivalent of a uconfset command for a configuration change) to the Transfer CFT.

## <span id="SSL"></span>SSL certificate renewal

Certificate and key renewal can refer to business and/or governance certificates. The request is initiated by the Copilot.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The Transfer CFT must be registered.         </td>
      </tr>
   </tbody>
</table>

### Automatic certificate renewal

When Copilot is started the certificates expiration dates in the PKI base are checked, and a renewal request is scheduled. The request schedule is dependent on the value set in the UCONF parameter cg.renewal\_period, where the default value is 60 days. This represents the number of days before the certificate renewal process occurs relative to the expiration date. Each certificate has a defined expiration date which may differ, and renewal occurs independent of one another.

Example

If uconf cg.renewal\_period is set to 60 days, the renewal procedure executes 60 days before the certificate expiration.

### Manual certificate renewal

To force a certificate renewal, execute the following commands. To force an immediate renewal, use a date that occurred in the past.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The datetime used for the renewal is in UTC and not local time.         </td>
      </tr>
   </tbody>
</table>

#### Set the following parameter to renew the governance certificate

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTUTIL UCONFSET id=cg.certificate.governance.renewal_datetime, value=YYYYMMDDHHMMSS</p>         </td>
      </tr>
   </tbody>
</table>

#### Set the following parameter to renew the business certificate

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTUTIL UCONFSET id=cg.certificate.business.renewal_datetime, value=YYYYMMDDHHMMSS</p>         </td>
      </tr>
   </tbody>
</table>

Where YYYYMMDDHHMMSS is the date and time of the renewal. For example, August 7 2019, 12:30 has the value 20190807123000.

#### <span id="Change"></span>Change the private key length

You can configure the key length for either a governance or business certificate from the default value of 2048 to 4096 either when you install Transfer CFT, or post-installation if you have a Transfer CFT that is already registered with Central Governance or Flow Manager.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Caution  </strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" data-valign="top">If you modify the key length of the governance certificate and you use access tokens, please refer to the <a href="../c_intro_userinterfaces/web_copilot_ui/cftssl/access_token">Access Token</a> and <a href="../app_integration_intro/using_apis/api_intro/api_authentication">Bearer authentication</a> sections for details before proceeding.         </td>
      </tr>
   </tbody>
</table>

1.  Modify the UCONF parameters:  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>CFTUTIL uconfset id=cg.certificate.governance.key_len, value=4096</p>
                <p>CFTUTIL uconfset id=cg.certificate.business.key_len, value=4096</p>         </td>
          </tr>
       </tbody>
    </table>
2.  Trigger a certificate renewal, for example by setting the UCONF `cg.certificate.<type>.renewal_datetime` parameter to a date that has passed (example, "20200101000000").
3.  Perform a Transfer CFT and a Copilot restart.
4.  To perform a check:  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>PKIUTIL LISTPKI TYPE=USER, CONTENT=FULL | grep "Private Key type"         </td>
          </tr>
       </tbody>
    </table>

      
    The result should be: `Private Key type  RSA      =  4096 bits`

## Product updates

Central Governance can apply updates, including service packs, patches, and version upgrades, remotely to registered Transfer CFTs. Download the update package from the [Axway support website](https://support.axway.com/), and upload it to Central Governance. Please refer to [Manage product updates](https://docs.axway.com/bundle/CentralGovernance_113_UsersGuide_allOS_en_HTML5/page/Content/updates/t_update_crud.htm) for details.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Available on Unix and Windows, though this service is not available for multi-node.         </td>
      </tr>
   </tbody>
</table>
