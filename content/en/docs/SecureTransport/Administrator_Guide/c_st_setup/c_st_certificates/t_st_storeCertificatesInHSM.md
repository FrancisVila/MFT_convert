{
    "title": "Store certificates in a hardware security module",
    "linkTitle": "Store certificates in a hardware security module",
    "weight": "180"
}You can store the certificates for the FTPS and HTTPS protocols in the HSM key storage provider or security world of a Thales nShield hardware security module (HSM). You can use any Thales nShield HSM that supports the nCipherKM JAC/JCE Java API. You must obtain the API and install it on the SecureTransport system.

The following topics provide the how-to instructions for storing certificates in a hardware security module:

-   [Install and configure the HSM](#install)
-   [Generate and sign an HSM certificate](#generate)
-   [Use an HSM certificate for FTPS or HTTPS](#use)

## <span id="Install"></span>Install and configure the HSM

SecureTransport maintains a keystore that stores references to the certificates stored in the HSM. Before you configure the HSM, decide on a location for the SecureTransport keystore file, for example, `<FILEDRIVEHOME>/lib/certs/hsm.keystore`.

1.  Install the nShield hardware.
2.  Install the nShield software, including the JCA/JCE cryptography service provider (CSP) on the system where the FTP Server and the HTTP Server run. Note the following values:
    -   `<NFAST_HOME>`, the path name of the installation directory of the nFast client, `/opt/nfast` by default
    -   The keystore passphrase
3.  Make sure that `nonpriv_port` is set to `9000` and `priv_port` is set to `9001` in the hard server configuration file, `<NFAST_HOME>/kmdata/config/config`.
4.  Copy the `nCipherKM.jar` file from `<NFAST_HOME>/java/classes` to `<FILEDRIVEHOME>/jre/lib/ext`.
5.  Run `<FILEDRIVEHOME>/jre/bin/java com.ncipher.provider.InstallationTest`.  
    The output include a list of installed providers. Ignore the statement that the nCipher provides is not correctly installed. The provider is installed at run time.

## <span id="Generate"></span>Generate and sign an HSM certificate

This procedure uses the following placeholders:

-   `<alias>` – the SSL key alias for FTPS or HTTPS, for example `ftpd` or `httpd`
-   `<cert_file>` is the file name of the PEM-format certificate file, for example, `ftpd.pem` or `httpd.pem`
-   `<CSR_file>` – the file name of the CSR request file, for example, `ftpd.req` or `httpd.req`
-   `<FILEDRIVEHOME>` – SecureTransport installation directory, for example, `/opt/TMWD/SecureTransport`
-   `<key_size>` – the key size, for example, `1024`, `2048`, `3072`, or `4096`
-   `<keystore_passphrase>` – the passphrase for the HSM keystore
-   `<keystore_path>` – the path to the SecureTransport HSM keystore
-   `<validity>` – the validity of the certificate in days

1.  Make the SecureTransport installation directory the current working directory using the following command.  
    

        cd <FILEDRIVEHOME>

2.  Generate a key using the following command.  
    

        jre/bin/keytool -genkey -keyalg RSA -keysize <key_size> \
            -keystore <keystore_path> -storetype nCipher.sworld \
            -providername nCipherKM \
            -providerclass com.ncipher.provider.km.nCipherKM \
            -alias <alias> -storepass <keystore_passphrase>

3.  Generate a certificate signing request (CSR) using the following command.  
    

        jre/bin/keytool -certreq -keystore <keystore_path> \
            -storetype nCipher.sworld -providername nCipherKM \
            -providerclass com.ncipher.provider.km.nCipherKM \
            -alias <alias> -file <CSR_file> -storepass <keystore_passphrase>

4.  Sign certificate and create the PEM-format certificate file using the following command.  
    

        bin/openssl x509 -req -in <CSR_file> -days <validity> \
            -CA lib/certs/db/ca-crt.pem -CAkey lib/certs/db/ca-key.pem \
            -CAserial lib/certs/db/serial -out <cert_file>

5.  Append the public part of the internal CA to the certificate file using the following command. This is required so that SecureTransport can build the certificate chain.  
    

        cat lib/certs/db/ca-crt.pem >> <cert_file>

6.  Import the signed certificate into the HSM device using the following command.  
    

        jre/bin/keytool -importcert -keystore <keystore_path> \
            -storetype nCipher.sworld -providername nCipherKM \
            -providerclass com.ncipher.provider.km.nCipherKM 
            -storepass <keystore_passphrase> -alias <alias> -file <cert_file>

## <span id="Use"></span>Use an HSM certificate for FTPS or HTTPS

1.  Specify the HSM for SecureTransport by setting the following server configuration
    parameters:
    -   Set `Hsm.keystorePath` to the location of the
        SecureTransport HSM keystore relative to `<FILEDRIVEHOME>`.
    -   (Optional) Set `Hsm.keystorePassword` to the keystore passphrase.
    -   If you do not store the passphrase as a server configuration parameter, you must enter it each time you start a protocol server that uses an HSM certificate. If you do not type the passphrase in the time allotted, the protocol server does not start.
2.  Enable HSM for the protocol servers by setting the following server configuration parameters:
    -   Set `Ftp.Hsm.enabled` to `true` to enable HSM for the FTP Server
    -   Set `Http.Hsm.enabled` to `true` to enable HSM for the HTTP Server
3.  Create a local certificate with the same alias as the HSM certificate you created, for example, `ftpd` or `httpd`. See [Generate a self-issued server certificate](../t_st_localcertificatesandcsrs). SecureTransport does not use this certificate, but you must have a certificate with the correct alias to reference the HSM certificate.
4.  Set the SSL key aliases for the protocol servers. See [Manage the FTP server](../../../operations_menu/extended_server_control/ext_servercontrol-add-ftp) and [Manage the HTTP server](../../../operations_menu/extended_server_control/ext_servercontrol-add-http).
5.  Restart the protocol servers. See [Start and stop servers](t_st_mange_server-ops.htm#start).

 

**Related topics:**

-   [Certificate types](../r_st_certificate_types)
-   [Certificate Management page](../c_st_certificate_management_page)
-   [Repository encryption certificate](../t_st_repository_encryption_certificate)
-   [Manage local certificates and certificate signing requests](../t_st_localcertificatesandcsrs)
-   [Manage trusted CAs](../t_st_trustedcas)
-   [Manage the internal CA](../t_st_internalca)
-   [Change the certificate keystore password](../t_st_certificatekeystorepasswordca)
-   [Certificates to generate during initial setup](../r_st_certificatestogenerate)