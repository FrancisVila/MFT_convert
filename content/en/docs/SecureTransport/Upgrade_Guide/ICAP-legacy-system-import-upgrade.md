{
    "title": "ICAP\u00a0legacy system import and upgrade",
    "linkTitle": "ICAP\u00a0legacy system import and upgrade",
    "weight": "110"
}Mapping between old ICAP options and new ICAP server during legacy system import and upgrade from 5.3.6 GA to 5.4:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <tbody>
      <tr>
         <td><strong>ICAP Server</strong>
         </td>
         <td> <strong>Old Configuration option</strong>         </td>
      </tr>
      <tr>
         <td><code>icapServer.connectionTimeout</code>
         </td>
         <td><code>icap.First/SecondServer.ConnectTimeout</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.enabledCiphers</code>
         </td>
         <td><code>icap.First/SecondServer.EnabledCipherSuites</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.enabledProtocols</code>
         </td>
         <td><code>icap.First/SecondServer.EnabledProtocols</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.fipsEnabled</code>
         </td>
         <td><code>icap.First/SecondServer.enableFipsMode</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.scanWithoutBu</code>
         </td>
         <td><code>icap.First/SecondServer.enableScanForAccountsWithoutBusinessUnit</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.useSecure</code>
         </td>
         <td><code>icap.First/SecondServer.enableSecureConnection</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.ignoredFileTypes</code>
         </td>
         <td><code> icap.First/SecondServer.IgnoredFileTypes</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.mailAddressesOnIcapError</code>
         </td>
         <td><code>icap.First/SecondServer.mailtoAddressesForMailsIfIcapErrors</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.mailAddressesOnIcapDenied</code>
         </td>
         <td><code> icap.First/SecondServer.mailtoAddressesForMailsIfTransferDeniedByIcap</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.maxSize</code>
         </td>
         <td><code>icap.First/SecondServer.MsgMaxSize</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.previewSize</code>
         </td>
         <td><code>icap.First/SecondServer.PreviewSize</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.readTimeout</code>
         </td>
         <td><code>icap.First/SecondServer.ReadTimeout</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.enabled</code>
         </td>
         <td><code>icap.First/SecondServer.ScanEnabled</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.sendEmptyPreview</code>
         </td>
         <td><code>icap.First/SecondServer.sendEmptyPreview</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.notifyOnIcapErrors</code>
         </td>
         <td><code> icap.First/SecondServer.sendMailsIfIcapErrors</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.notifyOnIcapDenied</code>
         </td>
         <td><code>icap.First/SecondServer.sendMailsIfTransferDeniedByIcap</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.denyOnConnectionError</code>
         </td>
         <td><code>icap.First/SecondServer.stopTransfersIfIcapErrors</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.stopModifyOrNotHandled</code>
         </td>
         <td><code>icap.First/SecondServer.stopTransfersIfIcapResultModifyOrNotHandled</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.treatModifyAsBlock</code>
         </td>
         <td><code>icap.First/SecondServer.treatModifyAsBlock</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.url</code>
         </td>
         <td><code>icap.First/SecondServer.Url</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.certVerify</code>
         </td>
         <td><code> icap.First/SecondServer.verifyCertificate</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.id</code>
         </td>
         <td>runtime generated value         </td>
      </tr>
      <tr>
         <td><code>icapServer.enableWinNtFormat</code>
         </td>
         <td><code> false (0)</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.headersMapping</code>
         </td>
         <td><code>NULL</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.name</code>
         </td>
         <td> Name mapping (ex. <code>i_cap.FirstServer.Url_ FirstServer</code>)         </td>
      </tr>
      <tr>
         <td><code>icapServer.scanOnlyIfPartnerRecipient</code>
         </td>
         <td><code>false (0)</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.scanPolicyExpression</code>
         </td>
         <td><code> NULL</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.type</code>
         </td>
         <td><code>INCOMING</code>
         </td>
      </tr>
      <tr>
         <td><code>icapServer.customAttributesId</code>
         </td>
         <td><code>NULL</code>
         </td>
      </tr>
   </tbody>
</table>

**On legacy system import:**

-   If the value of configuration option `FirstServer.Url_` is not empty, the new ICAP server entity with name `FirstServer  _` will be created, if an ICAP server
    with the same name exists - the legacy system import will fail.
-   If the value of configuration option `SecondServer.Url_` is not empty, the new ICAP server entity with name `SecondServer_` will be created, if an ICAP server
    with same name exist - the legacy system import will fail.

**On upgrade from 5.3.6 GA:**

-   If the value of configuration option `icap.FirstServer.Url` is not empty, the new ICAP server entity with name `FirstServer` will be created.
-   If the value of configuration option `icap.SecondServer.Url` is not empty, the new ICAP server entity with name `SecondServer` will be created.
