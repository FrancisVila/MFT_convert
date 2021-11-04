{
    "title": "Message Of The Day ",
    "linkTitle": "Message Of The Day",
    "weight": "240"
}You can configure a Message Of The Day (MOTD) pop-up window that displays after the user logs in. MOTD is a server-controlled feature; it can be disabled from <span class="mc-variable SecureTransport_Variables.st_web_client variable">ST Web Client</span>.

To setup a message, follow the steps described in the *Configure HTTP server messages* section of the *<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's guide*.

To disable MOTD, even if it is enabled from the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> server, edit the `stwebclient.config.json` file and add the following:


    {
    "features": {
      ....
         "messageOfTheDay": {
            "enabled": false
         }
      ....
     }
    }                       
