{
    "title": "Session management",
    "linkTitle": "Session management",
    "weight": "210"
}Use the `"downloadServerPolling"` section to prevent UI session timeouts when large files are being downloaded.

To enable the download polling:

    {
       ...
       "sessionManagement": {
          downloadServerPolling": {
           "enabled": true
          }
       }
       ...
    }                       

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Download polling depends on transfers API. The <strong>Allow this account to submit transfers using the Transfers RESTful API</strong> option must be enabled for the user.         </td>
      </tr>
</table>
