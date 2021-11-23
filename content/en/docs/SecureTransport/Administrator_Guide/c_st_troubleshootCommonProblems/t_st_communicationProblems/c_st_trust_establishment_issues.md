{
    "title": "Trust establishment issues",
    "linkTitle": "Trust establishment issues",
    "weight": "250"
}If the certificates are not configured correctly for both the {{< SecureTransport/componentshortname  >}} Server and the {{< SecureTransport/componentshortname  >}} Edge, trust might not be properly established between the two systems. Try the following procedures to verify your trust settings.

-   To establish trust between {{< SecureTransport/componentshortname >}} Server and {{< SecureTransport/componentshortname >}} Edge, you need to exchange Trusted CA certificates. Exchanging certificates consists of:  
    -   Saving the CA certificate for {{< SecureTransport/componentshortname >}} Server to a file on a local system and importing the file to the {{< SecureTransport/componentshortname >}} Edge using the {{< SecureTransport/componentshortname >}} Administration Tool.
    -   Saving the CA certificate for {{< SecureTransport/componentshortname >}} Edge to a file on a local system and importing the file to the {{< SecureTransport/componentshortname >}} Server using the {{< SecureTransport/componentshortname >}} Administration Tool.

To export or import a CA certificate, see [Manage trusted CAs](../../../c_st_setup/c_st_certificates/t_st_trustedcas#top).

**Related topics:**

-   [Clocks out of sync](../c_st_clocks_out_of_sync)
-   [Connectivity](../c_st_connectivity)

## Common certificate errors

If certificates are not correctly imported or the certificate has expired, you might see ERROR-level entries regarding SSL handshaking in the server log on the {{< SecureTransport/componentshortname  >}} Server such as:

`com.valicert.brules.eventmonitor - SSL handshake failed`

Specific issues that can cause an error include:

-   {{< SecureTransport/componentshortname >}} Server CA certificate is not imported into Edge.
-   {{< SecureTransport/componentshortname >}} Edge CA certificate is not imported into Server.
-   {{< SecureTransport/componentshortname >}} Server CA certificate is expired.
-   {{< SecureTransport/componentshortname >}} Edge CA certificate is expired.
-   {{< SecureTransport/componentshortname >}} Server certificate is expired.
-   {{< SecureTransport/componentshortname >}} Edge certificate is expired.

Use **Setup &gt; Certificates** to view the certificates and monitor expiration dates on a regular basis.
