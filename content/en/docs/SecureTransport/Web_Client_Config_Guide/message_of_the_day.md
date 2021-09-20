{
    "title": "Message Of The Day",
    "linkTitle": "Message Of The Day",
    "weight": "240"
}You can configure a Message Of The Day (MOTD) pop-up window that displays after the user logs in. MOTD is a server-controlled feature; it can be disabled from ST Web Client.

To setup a message, follow the steps described in the *Configure HTTP server messages* section of the *SecureTransport Administrator's guide*.

To disable MOTD, even if it is enabled from the SecureTransport server, edit the `stwebclient.config.json` file and add the following:

    {
    "features": {
      ....
         "messageOfTheDay": {
            "enabled": false
         }
      ....
     }
    }                       
