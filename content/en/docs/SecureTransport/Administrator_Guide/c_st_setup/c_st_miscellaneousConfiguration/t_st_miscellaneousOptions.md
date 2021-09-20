{
    "title": "Miscellaneous options",
    "linkTitle": "Miscellaneous options",
    "weight": "270"
}This topic describes how to configure the miscellaneous setup options.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">As of <span>SecureTransport</span> 5.3.3, Java Applet and ActiveX are no longer available or supported.         </td>
      </tr>
</table>

The following topics provide how-to instructions for configuring the miscellaneous options:

-   [Set the administrator’s email](#set2)
-   [Set usage monitor options](#set)
-   [Enable or disable reverse DNS lookups](#enable)
-   [Set the session timeout](#set3)
-   [Select a default HTML template](#select)
-   [Limit FTP login failures](#limit)

**Related topics:**

-   [SMTP configuration](../t_st_smtpconfiguration)
-   [FTP and HTTP server suspend options](../t_st_ftphttpservershutdownoptions)
-   [Password policy](../t_st_passwordpolicy)

## <span id="Set2"></span>Set the administrator’s email

The administrator e-mail is the email address for the system administrator of the FTP server. This address (if specified) is used in several server response messages and is available (%E macro) for run-time messages. Administrator email is available for the FTP server only.

1.  Select **Setup > Miscellaneous** and view the *Miscellaneous Options* pane.
2.  Enter an e-mail address in the **Administrator Email** field.
3.  Click **Apply**.

## <span id="Set"></span>Set usage monitor options

The Server Usage Monitor can be configured to monitor several different aspects of the server or cluster nodes. You can also turn it off entirely.

Each of the monitoring options requires additional CPU resources per server process to compute and track the enabled measurements. To improve server performance, disable all unnecessary monitoring functions. The usage monitor is available for the FTP, SSH and HTTP(S) servers only.

The possible option settings are as follows:

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Option</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Enable all monitoring functions         </td>
         <td>Enables all monitoring functions         </td>
      </tr>
      <tr>
         <td>Enable monitor - Measure bandwidth         </td>
         <td>Keeps track of the instantaneous transfer rate of each FTP server process running         </td>
      </tr>
      <tr>
         <td>Enable monitor - Display user commands         </td>
         <td>Keeps track of which FTP command a user is currently executing         </td>
      </tr>
      <tr>
         <td>Enable monitor - No bandwidth/commands         </td>
         <td>Displays process information per FTP server connection         </td>
      </tr>
      <tr>
         <td>Disable monitor         </td>
         <td>Disables all FTP, SSH and HTTP(S) monitoring         </td>
      </tr>
   </tbody>
</table>

1.  Select **Setup > Miscellaneous** and view the *Miscellaneous Options* pane.
2.  In the **Usage Monitor Options** field, select a monitoring option or disable monitoring.
3.  Click **Apply**.

## <span id="Enable"></span>Enable or disable reverse DNS lookups

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">This procedure has been replaced by the <code>Server.ReverseDNSLookups</code> server configuration parameter. Edit the <code>Server.ReverseDNSLookups</code> server configuration parameter to enable or disable reverse DNS lookups.         </td>
      </tr>
</table>

Reverse DNS lookups are used to resolve an IP address into a fully qualified domain name. The domain name is used for logging purposes and for applying access rules that specify a host name (instead of an IP address).

In cases where the DNS server is under heavy load, this can significantly affect the startup time of an FTP, HTTP, or SSH session. If the fully qualified domain name is not needed in the log files, it is best to turn off this feature.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">This feature is available for the FTP, HTTP, and SSH servers.         </td>
      </tr>
</table>

1.  Select **Setup > Miscellaneous** and view the *Miscellaneous Options* pane.
2.  In the **Reverse DNS Lookups** field, choose to enable or disable reverse DNS lookups.
3.  Click **Apply**.

To disable reverse DNS lookups for the Administration Tool server, see [DNS settings](../../../c_st_troubleshootcommonproblems/t_st_performanceissues/t_st_dns_settings).

## <span id="Set3"></span>Set the session timeout

You can set a session timeout for SecureTransport so that users are automatically logged out if they are inactive for the specified duration. SecureTransport uses separate values for the session timeout for the SecureTransport Edge and SecureTransport Server. For example, when logged into the SecureTransport Edge, the Edge session timeout value is applied and when logged into the SecureTransport Server, the Server value is applied.

1.  Select **Setup > Miscellaneous** and view the *Miscellaneous Options* pane.
2.  Enter the number of seconds (60 seconds minimum) in the **Session Timeout** field to specify the session timeout duration.
3.  Click **Apply**.

## <span id="Select"></span>Select a default HTML template

SecureTransport provides several different templates that change the look and feel of the web client user interface. The available options include: SecureTransport Legacy Client, Axway Jelly Ball 9, Axway Box and Stripe in Blue, and ST Web Client. If you configure a user account to use the default HTML template, it uses the one you configure here. For more information about the web clients, refer to the *SecureTransport Web Client User’s Guide*.

### Select a default HTML template for web client users

1.  Select **Setup > Miscellaneous** and view the *Miscellaneous Options* pane.
2.  Select one of the templates from the **HTML Template** field. There are four choices that ship with SecureTransport: SecureTransport Legacy Client, Axway Jelly Ball 9, Axway Box and Stripe in Blue, and ST Web Client.
3.  Click **Apply**.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The login page of the HTML template you specify here is displayed when the user first accesses this <span>SecureTransport</span> Server. The rest of template is used if the user is configured to use the default HTML template. To set the HTML template for business unit, see <a href="t_st_businessunits.htm#create">Create or edit a business unit</a>. To set the HTML template for an individual user, see <a href="../../../accounts/useraccounts/t_st_create_user_account">Create a user account</a>.         </td>
      </tr>
</table>

### Use the HTML templates in a new locale

You can adapt a HTML template to a different locale by copying the existing template files and editing them. You also need to create a file for each locale named `skin.conf` that contains the descriptive information for the HTML Template. The SecureTransport Legacy Client template resides in `<FILEDRIVEHOME>/share/ftdocs/html/C`. In SecureTransport, `C` is the default locale.

This configuration is not applicable to the ST Web Client.

You need to create a locale folder for the files in the following location: `<FILEDRIVEHOME>/share/ftdocs/html/skin/<SKIN_NAME>/<LOCALE>/` where `<SKIN_NAME>` is the name of the template you want to use and `<LOCALE>` is the name of the new locale.

#### Create a locale folder

1.  Copy the files you want to modify from `<FILEDRIVEHOME>/share/ftdocs/html/C`. The files for the default template are in the locale directory C. To use one of the other template styles, copy the files from `<FILEDRIVEHOME>/share/ftdocs/html/skin/jb9` or `<FILEDRIVEHOME>/share/ftdocs/html/skin/sm6`.
2.  Create a directory based on the new locale: `<FILEDRIVEHOME>/share/ftdocs/html/skin/<SKIN_NAME>/<LOCALE>/` and paste the copied files into the new directory.
3.  Create the file `skin.conf` using a text editor. The contents of `skin.conf` are:  
    `description "<SkinTitle>"`  
    `icons-access "public"`
      
    where `<SkinTitle>` is the name of the HTML templates you are modifying. You can use any name.
4.  Select **Operations > Server Configuration**.  
    The *Server Configuration* page is displayed.
5.  Search for the `Admin.Locale` parameter and change its value to the new locale.
6.  Restart all servers in the cluster.

### Modify the HTML files

1.  Edit the copied HTML files. You can translate or modify the files.  
    For additional information about editing the HTML pages and the default locale, see [Customize a web client](../../../operations_menu/c_st_standardbrowserclient).
2.  Select **Setup > Miscellaneous** and view the *Miscellaneous Options* pane.
3.  Select one of the templates from the **HTML Template** field and click **Apply**.

## <span id="Limit"></span>Limit FTP login failures

You can limit the number of consecutive failed login attempts before the FTP Server terminates a user connection. Limiting the number of consecutive failed login attempts provides added security.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If you only translate the templates, you can use an existing skin name when you create the new directory, just create a locale subdirectory. If you change the file content, use a new skin name. Do not overwrite the original HTML templates.         </td>
      </tr>
</table>

1.  Select **Setup > Miscellaneous** and view the *Miscellaneous Options* pane.
2.  In the **Disconnect after \_\_\_\_ failed login attempts field**, type a value greater than zero to identify the number of failed login attempts you want to allow before disconnecting the user.
3.  Click **Apply**.
