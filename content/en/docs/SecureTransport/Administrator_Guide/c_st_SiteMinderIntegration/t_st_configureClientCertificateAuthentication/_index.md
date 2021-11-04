{
    "title": "Configure client certificate authentication settings",
    "linkTitle": "Configure client certificate authentication settings",
    "weight": "170"
}Instead of logging on through the SSO portal, web clients and command line clients can log on to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> directly and request authentication using a client certificate. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> then presents the client certificate to SiteMinder for authentication. To configure <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> to perform client certificate authentication using SiteMinder, complete these steps:

1.  Import into <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> the trusted Certificate Authority (CA) certificates for the client certificates to be authenticated. Client certificates are authenticated using indirect trust. For instructions on importing trusted CA certificates, refer to <a href="../../c_st_setup/c_st_certificates/t_st_trustedcas#Import" class="MCXref xref">Import a trusted CA certificate</a>.
2.  Restart the SSH Server.
3.  Bounce the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Servers.
