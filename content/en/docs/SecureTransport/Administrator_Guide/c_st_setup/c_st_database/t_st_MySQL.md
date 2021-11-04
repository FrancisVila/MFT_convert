{
    "title": "Change the embedded database configuration",
    "linkTitle": "Change the embedded database configuration",
    "weight": "170"
}<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> administrators with database reconfiguration permissions can change the embedded database settings and restart the database service using the Administration Tool or Admin REST API.

In the Administration tool, go to **Setup &gt; Database Settings**. From this page you can:

-   change the database port
-   change the database connection
-   secure the connection to the database
-   check and extend the validity of a certificate
    for connection to the embedded MariaDB database

Make sure you change the settings separately, as described in the following subtopics.

> **Note:**
>
> The MySQL/MariaDB configuration is stored in the &lt;FILEDRIVEHOME>/conf/internaldb.conf file.

Make sure you change the settings separately, as described in the following subtopics.

## Change the embedded database port

1.  Go to the *Database settings* page.  
2.  Under *Standard Clustering - MariaDB / MySQL Local Database*, type the new port number in the **Port** field.
3.  Click **Save**.
4.  Click **Restart Database Now**.
5.  After the database restart, restart all <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> services.

## Change the embedded database password

> **Note:**
>
> After installation, the embedded database password is tumbleweed. For better security, change it as described in the following procedure.

1.  Go to the *Database settings* page.
2.  Under *Standard Clustering - MariaDB / MySQL Local Database*, type the new password in both the **Password** and **Retype Password** fields.
3.  Click **Save**.
4.  Restart all <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> services.

## Secure the connection to the embedded MariaDB database

Proceed as follows to encrypt the connection between SecureTransport and the database server.

1.  Go to the *Database settings* page.

2.  Check the **Use Secure Connection** checkbox.

3.  Supply the certificates: **Certificate Authority File**, **Server Private Key File**, and **Server Certificate File**.  
    Those certificates can be either generated by <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> or manually imported.  

    -   If you want SecureTransport to automatically generate the certificates, leave the three certificate fields empty. The required files will be created when you click the **SAVE** button. Note that the validity period of self-signed certificates is 365 days.
    -   If you have used an external mechanism to generate the certificates, import the required files into <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> using the dedicated **Browse** buttons. All files must be in PEM format.

    <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> stores those files in the `<FDH>/lib/certs/db` directory.

    If you're switching back to a secure configuration, you might have previously used or generated certificates in the above specified directory that are still valid. In this case, click the **SAVE** button. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> will check the certificates for validity and, if all of them are valid, will reuse them. If there is an invalid certificate, all certificates will be automatically generated upon saving the database configuration.

4.  Restart all <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> services through their scripts for the changes to take effect.

### Check or extend the validity of certificates

By default, self-signed certificates generated by <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> are valid for 365 days. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> checks the certificates for expiry at midnight, and sends a warning message (in the Server Log under WARN logging level) 7 days before the certificate expiration date. If you do not generate new certificates on time, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> will automatically regenerate the expiring certificates on the day of expiration at 12 am.

All services need to be manually restarted before the new certificates are applied. There will be log a message under ERROR logging level for the required service restart.

-   To check the validity of the certificates present in the `<FDH>/lib/certs/db` directory, from the **Actions** drop-down, select **Check Certificates Validity**. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> shows the number of days left until the certificates expire. If your certificates have different expiry dates, then it shows the minimum number of days until one of the certificates expires.

<!-- -->

-   To extend the validity period of self-signed certificates generated using the Database settings' **Generate Certificates** button, from the **Actions** drop-down, select **Generate Certificates** and edit the value to the desired number of days. Then, click **Generate**.

**Related topics:**

-   <a href="../t_st_database" class="MCXref xref">Migrate from embedded database to external Oracle database</a>
-   <a href="../t_st_separate_databases" class="MCXref xref">Direct log data to separate Oracle databases</a>
-   <a href="../t_st_oracle" class="MCXref xref">Change the Oracle database configuration</a>
-   <a href="../t_st_sqlserver" class="MCXref xref">Change the external Microsoft SQL Server database</a>