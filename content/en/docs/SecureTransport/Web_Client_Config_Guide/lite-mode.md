{
    "title": "Lite mode",
    "linkTitle": "Lite mode",
    "weight": "150"
}Lite mode is a lightweight version of the ST Web Client. It offers all basic functionality you would expect from the Web Client in a simplistic view.

Because of this, certain features and views in the Lite mode are disabled. For example, in Lite mode you can have only All files view, while the Mailbox view is disabled. As a result, the Address book feature is disabled and you cannot access your contacts.

Other disabled features include the File sharing action, Transfer queue, navigation tabs, ASCII transfer mode, and some Accessibility shortcuts. Also, in Lite mode only the basic navigation with breadcrumbs is available. These changes also apply to the mobile view.

To enable Lite mode, add the following key to the custom `stwebclient.config.json` configuration file.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">{
 ...
 "liteMode": {
    "enabled": true
 }     </pre>
         </td>
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
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">
<note>When you enable Lite mode, it overrides the settings of certain features and views, regardless of their configuration in the <code>stwebclient.config.json</code> file.</note>
         </td>
      </tr>
</table>
