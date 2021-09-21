{
    "title": "Message Of The Day",
    "linkTitle": "Message Of The Day",
    "weight": "240"
}You can configure a Message Of The Day (MOTD) pop-up window that displays after the user logs in. MOTD is a server-controlled feature; it can be disabled from ST Web Client.

To setup a message, follow the steps described in the *Configure HTTP server messages* section of the *SecureTransport Administrator's guide*.

To disable MOTD, even if it is enabled from the SecureTransport server, edit the `stwebclient.config.json` file and add the following:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">{
"features": {
  ....
     "messageOfTheDay": {
        "enabled": false
     }
  ....
 }
}						</pre>
         </td>
      </tr>
   </tbody>
</table>
