{
    "title": "Disable the SecureTransport login",
    "linkTitle": "Disable the SecureTransport login",
    "weight": "170"
}Web clients that have logged on through the SiteMinder SSO portal should not log on again to the SecureTransport login page. Therefore, it is necessary to disable the SecureTransport login page for these clients.

1.  Select **Operations > Server Configuration**.  
    The *Server Configuration* page is displayed.
2.  Search for the `Http.FdxAuthReply` parameter.
3.  Change the value to `PREAUTH`.
4.  Restart the HTTP server and the TM Server.
