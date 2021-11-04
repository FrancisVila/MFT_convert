{
    "title": "Exchange CA certificates",
    "linkTitle": "Exchange CA certificates",
    "weight": "110"
}The Setup step 7 pertains only to a two-tier architecture, where both a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge and <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server are being configured.

In a two-tier deployment, the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge and <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server authenticate each other through the use of certificates. These certificates have already been created and specified in previous steps. In this step, a trust relationship between the two servers must be set up. This setup involves exchanging certificates between <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge and <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server.

To complete this step, you must be able to access both the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server and <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge Administration Tool. Use a separate browser window to open each Administration Tool.

> **Note:**
>
> When you log in to the Administration Tool using the admin account, you can access this page by selecting Setup &gt; Certificates &gt; Trusted CAs.

<img src="/Images/SecureTransport/exchange_certificates.png" class="maxWidth" alt="Exchange Certificates - Trusted CA Certificates" />

## Export the SecureTransport Server or Edge CA certificate

Use the following steps to export the CA certificate from the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server or Edge.

1.  Go to **Configure > 7-Exchange Certs**.
2.  From the list of trusted CAs, click the alias that matches the CA certificate set up for the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server or Edge in **Configure > 2-Generate CA**.  
    The *View Certificate* dialog box is displayed.  
    <img src="/Images/SecureTransport/view_certificate.png" class="mediumWidth" alt="View Certificate - Exchange Certificates Export" />
3.  Click **Export** in the *View Certificate* dialog box.
4.  Save the file to a location in the local system.
5.  Click **Close**.

If necessary, you can import the CA certificate file to Edge (or <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server, where applicable).

## Import the SecureTransport Server or Edge CA certificate

A X509 certificate can be imported as a trusted CA in the form of a X509 DER or PEM encoded file. Make sure the certificate is valid and configured to validate certificates before you import it. The CA attribute in the X509v3 extension section of the certificate must be true.

> **Note:**
>
> SecureTransport protocol servers and services do not require restart after importing, overwriting, or deleting a trusted CA.

Use the following steps to import the CA certificate from the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server to the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge or vice versa.

1.  Go to **Configure > 7-Exchange Certs**.
2.  Click **Import**. The *Import Certificate* dialog box is displayed.  
    <img src="/Images/SecureTransport/importCAcertificate.png" class="mediumWidth" alt="Import CA Certificate" />
3.  Enter an **Alias** for the imported certificate. Ensure the alias is unique and different from any other trusted CA aliases
4.  To import the certificate file:
    1.  Select **Import certificate from file** and click **Browse** to locate the file on your local system.
    2.  Or select **Paste certificate in space below** to copy and paste the certificate contents.
    3.  Click **Import** to import the certificate to the Edge server.
5.  Click **Close** in the *Import Certificate* dialog box.  
    The newly imported certificate appears in the **Trusted CA Certificates** list.

 

The following topics provide how-to instructions for importing and exporting <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> Server and Edge CAs:

-   <a href="#" class="MCXref xref">Export the SecureTransport Server CA certificate</a> - Provides how-to instructions for exporting the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server CA certificate.
-   <a href="#" class="MCXref xref">Import the SecureTransport Server CA certificate</a> - Provides how-to instructions for importing the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server CA certificate.
-   <a href="#" class="MCXref xref">Export the SecureTransport Edge CA certificate</a> - Provides how-to instructions for exporting the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge CA certificate.
-   <a href="#" class="MCXref xref">Import the SecureTransport Edge CA certificate</a> - Provides how-to instructions for importing the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge CA certificate.
