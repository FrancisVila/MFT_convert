{
    "title": "Install a certificate on the server",
    "linkTitle": "Install a certificate on the server",
    "weight": "180"
}The certificates used by the Transfer CFT Copilot server to authenticate itself are defined in UCONF using the parameters described in the following tables.

The examples provided in this section use sample certificates that are supplied in product. Do not use these certificates in production; you should instead use your own certificates.

**Example 1**

This example uses a single PKCS#12 certificate.

<table align="left" cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Parameter</p>
</th>
         <th>
            <p>Value</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>copilot.ssl.SslCertFile</p>
            <p> </p>
         </td>
         <td>
            <p>conf/pki/MFT_Demonstration_User_Certificate.p12</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>copilot.ssl.SslCertPassword</p>
            <p> </p>
         </td>
         <td>
            <p>Certificate password (“user” for the sample above)</p>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>copilot.ssl.SslKeyFile</p>
            <p> </p>
         </td>
         <td>
            <p>Not used</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>copilot.ssl.SslKeyPassword</p>
            <p> </p>
         </td>
         <td>
            <p>Not used</p>
         </td>
      </tr>
   </tbody>
</table>

**Example 2**

This example uses a DER certificate with the private key in a separate DER file.

<table align="center" cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Parameter</p>
</th>
         <th>
            <p>Value</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>copilot.ssl.SslCertFile</p>
            <p> </p>
         </td>
         <td>
            <p>conf/pki /MFT_Demonstration_User_Certificate.der</p>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>copilot.ssl.SslCertPassword</p>
            <p> </p>
         </td>
         <td>
            <p>Not used</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>copilot.ssl.SslKeyFile</p>
            <p> </p>
         </td>
         <td>
            <p>conf/pki /MFT_Demonstration_User_Certificatek.der</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>copilot.ssl.SslKeyPassword</p>
            <p> </p>
         </td>
         <td>
            <p>Key file password (no password with sample file above)</p>
         </td>
      </tr>
   </tbody>
</table>

### Additional https parameters

There are two additional UCONF parameters to use for https connections:

<table align="center" cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Parameter</p>
</th>
         <th>
            <p>Value</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>copilot.http.onlyssl </p>
         </td>
         <td>
            <ul>
               <li>No: Default value.               </li>
               <li>Yes: Restricts access to the Copilot server to HTTPS secured connections only.               </li>
            </ul>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>copilot.ssl.SslCipherSuites</p>
            <p> </p>
         </td>
         <td>
            <p>A comma separated list of cipher suites accepted by the Copilot server.</p>
            <ul>
               <li>“47, 10, 9, 2”: Default value.               </li>
            </ul>
            <p> </p>
            <p>List of supported cipher suites:</p>
            <ul>
               <li>1 = RSA_WITH_NULL_MD5               </li>
               <li>2 = RSA_WITH_NULL_SHA               </li>
               <li>4 = RSA_WITH_RC4_MD5               </li>
               <li>5 = RSA_WITH_RC4_SHA               </li>
               <li>9 = RSA_WITH_DES_CBC_SHA1               </li>
               <li>10 = RSA_WITH_3DES_EDE_CBC_SHA               </li>
               <li>47 = RSA_WITH_AES_128_CBC_SHA               </li>
               <li>53 = RSA_WITH_AES_256_CBC_SHA               </li>
               <li>59 = RSA_WITH_NULL_SHA256               </li>
               <li><span>60 = RSA_WITH_AES_128_CBC_SHA</span><span>2</span><span>56</span>
               </li>
               <li><span>61 = RSA_WITH_AES_256_CBC_SHA</span><span>2</span><span>56</span>
               </li>
            </ul>
         </td>
      </tr>
   </tbody>
</table>

## Installing a certificate on the client side

**Windows**

On Windows, there are two ways to install a certificate on the client side: use the Windows certificate, or the Java keystore.

UNIX

On Linux, the Java keystore is the only option.

**Example**

In this section and the example below, we use the sample certificate delivered with Transfer CFT and located at:

&lt;CFTDIRRUNTIME>/conf/pki/Axway\_MFT\_Demonstration\_Root\_Certificate.der

### Installing a certificate in the Windows keystore

1.  In Windows Explorer, navigate to the certificate Axway\_MFT\_Demonstration\_Root\_Certificate.der and right-click.
2.  Select the “Install certificate” option.
3.  Follow the screen instructions. Windows automatically imports the certificate into its keystore, in the Intermediate certificate authorities folder.

Alternative method

1.  In Internet Explorer, select Tools > Internet Options.
2.  In the Content tab select the Certificate button.
3.  Select Import, which starts the Certificate Import Wizard.
4.  Click Next, and Browse to the Axway\_MFT\_Demonstration\_Root\_Certificate.der.
5.  Follow the screen instructions. Windows imports the certificate into its keystore.

### Installing a certificate in the Java keystore

The Java keystore is a file located at &lt;installation directory>/jre/lib/security/cacerts. The default password for this keystore is “changeit”.

Use the keytool command as follows to import the Axway\_MFT\_Demonstration\_Root\_Certificate.der certificate into the Java keystore:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>keytool –importcert</p>
            <p>   -trustcacerts</p>
            <p>   -alias AXWMFTCA</p>
            <p>   -file Axway_MFT_Demonstration_Root_Certificate.der</p>
            <p>   -storepass changeit-keystore &lt;keystore&gt;</p>
         </td>
      </tr>
   </tbody>
</table>

### Specify the keystore to use on the client side by customizing html files

The html files used by the Transfer CFT Copilot server to be accessed by a browser are:

-   runtime/wwwroot/admin.html
-   runtime/wwwroot/index.html

These files contain a parameter SSL\_KEYSTORE, which are modifiable. The default value for this parameter is “Windows”, and the only other possible value is “” (empty string).

The following table shows used keystore depending on the SSL\_KEYSTORE value and operating system.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>SSL_KEYSTORE value</p>
</th>
         <th>
            <p>Windows</p>
</th>
         <th>
            <p>Linux</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>“Windows”</p>
         </td>
         <td>
            <p>Windows keystore</p>
         </td>
         <td>
            <p>Java keystore</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>“” (empty string)</p>
         </td>
         <td>
            <p>Java keystore</p>
         </td>
         <td>
            <p>Java keystore</p>
         </td>
      </tr>
   </tbody>
</table>

## Connect to Copilot through an SSL connection

Restart the Transfer CFT Copilot server and your browser, and connect to the following URL:

https://&lt;copilot\_server\_hostaddr>:&lt;uconf:copilot.general.serverport>
