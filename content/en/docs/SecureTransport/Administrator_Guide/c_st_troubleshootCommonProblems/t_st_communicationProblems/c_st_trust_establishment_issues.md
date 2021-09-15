{
    "title": "Trust establishment issues",
    "linkTitle": "Trust establishment issues",
    "weight": "260"
}If the certificates are not configured correctly for both the SecureTransport Server and the SecureTransport Edge, trust might not be properly established between the two systems. Try the following procedures to verify your trust settings.

-   To establish trust between SecureTransport Server and SecureTransport Edge, you need to exchange Trusted CA certificates. Exchanging certificates consists of:  
    
    -   Saving the CA certificate for SecureTransport Server to a file on a local system and importing the file to the SecureTransport Edge using the SecureTransport Administration Tool.
    -   Saving the CA certificate for SecureTransport Edge to a file on a local system and importing the file to the SecureTransport Server using the SecureTransport Administration Tool.

To export or import a CA certificate, see [Manage trusted CAs](../../../c_st_setup/c_st_certificates/t_st_trustedcas).

**Related topics:**

-   [Clocks out of sync](../c_st_clocks_out_of_sync)
-   [Connectivity](../c_st_connectivity)

## Common certificate errors

If certificates are not correctly imported or the certificate has expired, you might see ERROR-level entries regarding SSL handshaking in the server log on the SecureTransport Server such as:

`com.valicert.brules.eventmonitor - SSL handshake failed`

Specific issues that can cause an error include:

-   SecureTransport Server CA certificate is not imported into Edge.
-   SecureTransport Edge CA certificate is not imported into Server.
-   SecureTransport Server CA certificate is expired.
-   SecureTransport Edge CA certificate is expired.
-   SecureTransport Server certificate is expired.
-   SecureTransport Edge certificate is expired.

Use **Setup &gt; Certificates** to view the certificates and monitor expiration dates on a regular basis.
