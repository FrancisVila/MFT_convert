{
    "title": "Database settings",
    "linkTitle": "Database settings",
    "weight": "90"
}If you are using the embedded database, select **Configure &gt; 5-Database Settings** to perform the following tasks:

-   Change the port or password for the embedded database for a {{< SecureTransport/componentshortname >}} Edge or a {{< SecureTransport/componentshortname >}} Server

<!-- -->

-   Migrate data from the embedded database to an external database

To change a stand-alone or clustered {{< SecureTransport/componentshortname  >}} Server to different Oracle database or to direct log data to separate external Oracle databases, refer to the .

<img src="/Images/SecureTransport/database_settings.png" class="maxWidth" alt="Database Settings - Configure database settings." />

> **Note:**
>
> When you log in to the Administration Tool using the admin account, you can access this page by selecting Setup &gt; Database Settings.

## Change the embedded database port or password

If this {{< SecureTransport/componentshortname  >}} installation uses the embedded database, the database has the default password `tumbleweed` after installation. To secure the system, change the database password. You can also change the database port.

1.  Select **Configure > 5-Database Settings**.
2.  Under *Standard Clustering - MySQL Local Database* or *Standard Clustering - MariaDB Local Database*, type the new port number in the **Port** field.
3.  Under *Standard Clustering - MySQL Local Database* or *Standard Clustering - MariaDB Local Database*, type the new password in both the **Password** and **Retype Password** fields.
4.  Click **Save**.
5.  If you changed the port, click **Restart Database Now**.
