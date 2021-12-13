{
    "title": "Configuring Copilot with HTTPS",
    "linkTitle": "Install a certificate on the server",
    "weight": "310"
}The certificates used by the Transfer CFT Copilot server to authenticate itself are defined in UCONF using the parameters described in the following tables.

The examples provided in this section use sample certificates that are supplied in product. Do not use these certificates  in production; you should instead use your own certificates.

**Example 1**

This example uses a single PKCS#12 certificate.


|  Parameter  |  Value  |
| --- | --- |
|  copilot.ssl.SslCertFile<br/>  |  conf/pki/MFT_Demonstration_User_Certificate.p12  |
|  copilot.ssl.SslCertPassword<br/>  |  Certificate password (“user” for the sample above)<br/>  |
|  copilot.ssl.SslKeyFile<br/>  |  Not used  |
|  copilot.ssl.SslKeyPassword<br/>  |  Not used  |


**Example 2**

This example uses  a DER certificate with the private key in a separate DER file.


|  Parameter  |  Value  |
| --- | --- |
|  copilot.ssl.SslCertFile<br/>  |  conf/pki /MFT_Demonstration_User_Certificate.der<br/>  |
|  copilot.ssl.SslCertPassword<br/>  |  Not used  |
|  copilot.ssl.SslKeyFile<br/>  |  conf/pki /MFT_Demonstration_User_Certificatek.der  |
|  copilot.ssl.SslKeyPassword<br/>  |  Key file password (no password with sample file above)  |


### Additional https parameters

There are two additional UCONF parameters to use for https connections:


|  Parameter  |  Value  |
| --- | --- |
|  copilot.http.onlyssl  |  <li>No: Default value.<br/> • Yes: Restricts access to the Copilot server to HTTPS secured connections only.<br/>  |
|  copilot.ssl.SslCipherSuites<br/>  |  A comma separated list of cipher suites accepted by the Copilot server.<br/> • “47, 10, 9, 2”: Default value.<br/> <br/>List of supported cipher suites:<br/> • 1 = RSA_WITH_NULL_MD5<br/> • 2 = RSA_WITH_NULL_SHA<br/> • 4 = RSA_WITH_RC4_MD5<br/> • 5 = RSA_WITH_RC4_SHA<br/> • 9 = RSA_WITH_DES_CBC_SHA1<br/> • 10 = RSA_WITH_3DES_EDE_CBC_SHA<br/> • 47 = RSA_WITH_AES_128_CBC_SHA<br/> • 53 = RSA_WITH_AES_256_CBC_SHA<br/> • 59 = RSA_WITH_NULL_SHA256<br/> • <br/> • </li>  |


## Installing a certificate on the client side

**Windows**

On Windows, there are two ways to install a certificate on the client side: use the Windows certificate, or the Java keystore.

UNIX

On Linux, the Java keystore is the only option.

**Example**

In this section and the example below, we use the sample certificate delivered with {{< TransferCFT/componentshortname  >}} and located at:

&lt;CFTDIRRUNTIME>/conf/pki/Axway\_MFT\_Demonstration\_Root\_Certificate.der

### Installing a certificate in the Windows keystore

1.  In Windows Explorer, navigate to the certificate `Axway_MFT_Demonstration_Root_Certificate.der` and right-click.
2.  Select the “Install certificate” option.
3.  Follow the screen instructions. Windows automatically imports the certificate into its keystore, in the `Intermediate certificate authorities` folder.

Alternative method

1.  In Internet Explorer, select **Tools > Internet Options.**
2.  In the **Content** tab select the **Certificate** button.
3.  Select **Import,** which starts the **Certificate Import Wizard**.
4.  Click **Next**, and **Browse** to the` Axway_MFT_Demonstration_Root_Certificate.der`.
5.  Follow the screen instructions. Windows imports the certificate into its keystore.

### Installing a certificate in the Java keystore

The Java keystore is a file located at` <installation directory>/jre/lib/security/cacerts`. The default password for this keystore is “changeit”.

Use the keytool command as follows to import the Axway\_MFT\_Demonstration\_Root\_Certificate.der certificate into the Java keystore:

```
keytool –importcert
   -trustcacerts
   -alias AXWMFTCA
   -file Axway_MFT_Demonstration_Root_Certificate.der
   -storepass changeit-keystore <keystore>
```

### Specify the keystore to use on the client side by customizing html files

The html files used by the Transfer CFT Copilot server to be accessed by a browser are:

-   runtime/wwwroot/admin.html
-   `runtime/wwwroot/index.html`

These files contain a parameter SSL\_KEYSTORE, which are modifiable. The default value for this parameter is “Windows”, and the only other possible value is “” (empty string).

The following table shows used keystore  depending on the SSL\_KEYSTORE value and operating system.


|  SSL_KEYSTORE value  |  Windows  |  Linux  |
| --- | --- | --- |
|  “Windows”  |  Windows keystore  |  Java keystore  |
|  “” (empty string)  |  Java keystore  |  Java keystore  |


## Connect to Copilot through an SSL connection

Restart the Transfer CFT Copilot server and your browser, and connect to the following URL:

`https://<copilot_server_hostaddr>:<uconf:copilot.general.serverport>`