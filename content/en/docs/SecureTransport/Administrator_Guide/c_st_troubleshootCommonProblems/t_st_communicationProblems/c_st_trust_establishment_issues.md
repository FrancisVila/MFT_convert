{
    "title": "Trust establishment issues",
    "linkTitle": "Trust establishment issues",
    "weight": "250"
}If the certificates are not configured correctly for both the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server and the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge, trust might not be properly established between the two systems. Try the following procedures to verify your trust settings.

-   To establish trust between <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server and <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge, you need to exchange Trusted CA certificates. Exchanging certificates consists of:  
    -   Saving the CA certificate for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server to a file on a local system and importing the file to the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge using the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administration Tool.
    -   Saving the CA certificate for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge to a file on a local system and importing the file to the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server using the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administration Tool.

To export or import a CA certificate, see <a href="../../../c_st_setup/c_st_certificates/t_st_trustedcas#top" class="MCXref xref">Manage trusted CAs</a>.

**Related topics:**

-   <a href="../c_st_clocks_out_of_sync" class="MCXref xref">Clocks out of sync</a>
-   <a href="../c_st_connectivity" class="MCXref xref">Connectivity</a>

## Common certificate errors

If certificates are not correctly imported or the certificate has expired, you might see ERROR-level entries regarding SSL handshaking in the server log on the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server such as:

`com.valicert.brules.eventmonitor - SSL handshake failed`

Specific issues that can cause an error include:

-   <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server CA certificate is not imported into Edge.
-   <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge CA certificate is not imported into Server.
-   <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server CA certificate is expired.
-   <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge CA certificate is expired.
-   <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server certificate is expired.
-   <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge certificate is expired.

Use **Setup &gt; Certificates** to view the certificates and monitor expiration dates on a regular basis.
