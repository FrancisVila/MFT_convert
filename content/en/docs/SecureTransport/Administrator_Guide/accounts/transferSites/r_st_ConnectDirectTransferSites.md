{
    "title": "Connect:Direct transfer sites",
    "linkTitle": "Connect:Direct transfer sites",
    "weight": "190"
}The Connect:Direct transfer sites are not built into {{< SecureTransport/componentshortname  >}}. To be able to create and modify transfer sites that use the Connect:Direct protocol, you need to perform the following tasks:

1.  Install CDJAI (Connect:Direct Application Interface for Java).
2.  Enable file transfers via Connect:Direct.
3.  Set the server configuration options for Connect:Direct file transfers.
4.  Create a Connect:Direct transfer site.

### Install CDJAI

The IBM Sterling Connect:Direct Application Interface for Java enables {{< SecureTransport/securetransportname  >}} to connect to Connect:Direct servers.

To install it, you need the `CDJAI.jar` file, which is provided with the Connect:Direct Java API. Follow the steps:

1.  Stop {{< SecureTransport/componentshortname >}} by running `<FILEDRIVEHOME>/bin/stop_all`.
2.  Copy the `CDJAI.jar` file to the `<FILEDRIVEHOME>/lib/jars/external` directory on the server running {{< SecureTransport/componentshortname >}}.
3.  Edit the
    `<FILEDRIVEHOME>/bin/start_tm_console` file to set the correct path to the `CDJAI.jar` file in the `CLASSPATH` parameter.
4.  If you are using the embedded database, run `<FILEDRIVEHOME>/bin/start_db`.
5.  Start the Administration Tool server by running `<FILEDRIVEHOME>/bin/start_admin`.

The certificate authentication to Connect:Direct servers requires CDJAI version 1.1.00 Fix 000026, as well as SecureTransport 5.5 October 2020 Update or later. If you're running an older CDJAI version, you must replace the jar file following the steps:

1.  Stop all services.
2.  Replace the jar file.
3.  Restart all services.

Next, you need to enable the file transfers via Connect:Direct and set the server configuration options related to them.

### Enable file transfers via Connect:Direct

1.  Log in to the Administration Tool, and go to **Setup > TM Settings**.
2.  Enable the `ConnectDirectTransfer` rules package.

### Set the server configuration options for Connect:Direct file transfers

1.  Go to **Operations > Server Configuration**.

2.  Search for the `ConnectDirectTransferAgent` parameters.

3.  Set `ConnectDirectTransferAgent.transfersFolder` to the full path of the directory for the {{< SecureTransport/componentshortname >}} Server to use for the Connect:Direct transfers. The directory must be shared between the {{< SecureTransport/componentshortname >}} and the Connect:Direct servers, and the path should be the same on both. Verify that {{< SecureTransport/componentshortname >}} has full permissions for the directory.  

    > **Note:**
    >
    > The directory path is not relative to &lt;FILEDRIVEHOME>. Specify a full absolute path from / (root) in UNIX or C:\\ or another volume on Windows.

4.  To manage purging of the Connect:Direct folder, use the `ConnectDirectTransferAgent.transfersFolder.purge` server configuration option. By default, it is set to **true**, which means that the folder used for the Connect:Direct transfers will be purged on Transaction Manager startup. When set to **false**, no purging is performed.

5.  Set `ConnectDirectTransferAgent.commandTimeout` to the interval in seconds that {{< SecureTransport/componentshortname >}} waits before the transfer times out.

6.  Start {{< SecureTransport/componentshortname >}} by running `<FILEDRIVEHOME>/bin/start_all`.

> **Note:**
>
> In order to obtain error messages for failed command execution, SecureTransport executes the SELECT STATISTICS command. The Connect:Direct user must have permissions to select statistics (cmd.selstats:a)

### Create a Connect:Direct transfer site

In the transfer site definition, select Connect:Direct as Transfer Protocol. For more information, see [Manage transfer sites](../t_st_transfersites). To create a Connect:Direct transfer site from a template, see [Use a site template to define a transfer site](../../../c_st_advancedaccountadministration/c_st_sitetemplates/t_st_usesitetemplate).

The following table describes the Connect:Direct protocol options for a transfer site:

<table>
   <thead>
      <tr>
<th colspan="2" class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Transfer Mode         </td>
         <td><p>Sets the file transfer mode. Valid values: ASCII, Binary, and Auto-detect. The default value is Auto-detect, meaning {{< SecureTransport/componentshortname  >}} automatically determines the proper transfer mode based on the file content type. For more information, see <a href="../../../c_st_advancedaccountadministration/c_st_clientinitiatedandserverinitiatedtransfers/c_st_transfer_mode_for_server-initiated_transfers#Advanced_Accounts_2036285406_1242761">Transfer mode for server-initiated transfers</a>.</p>         </td>
      </tr>
      <tr>
         <td><strong>Site Settings</strong>         </td>
      </tr>
      <tr>
         <td>Local server name         </td>
         <td>Specifies the domain name or IP address of the local server. You cannot enter spaces-only values in this field. For more information, see <a href="../../useraccounts/t_st_create_user_account#Spaces">Spaces in required fields</a>.         </td>
      </tr>
      <tr>
         <td>Local server port         </td>
         <td>Specifies the port assigned to the local server. You cannot enter spaces-only values in this field.         </td>
      </tr>
      <tr>
         <td><strong>Site Login Credentials</strong>         </td>
      </tr>
      <tr>
         <td>Local server user name         </td>
         <td>The username used to log in to the local server.         </td>
      </tr>
      <tr>
         <td>Select the authentication method         </td>
         <td><ul>
<li>Password authentication<br />
If the local server uses a password, select <strong>Use Password</strong> and enter the password in the field.</li>
</ul>
<ul>
<li>Certificate authentication<br />
To configure a {{< SecureTransport/componentshortname  >}} transfer site to connect to a Connect:Direct server by using a certificate:<br />
</li>
</ul>
<ol>
<li><p>Exchange the CA certificates between the SecureTransport and the Connect:Direct server: the trusted root certificate file of the Connect:Direct server should be exported, and imported as a trusted CA in {{< SecureTransport/componentshortname  >}}; the trusted root certificate file of the {{< SecureTransport/componentshortname  >}} server should be exported, and imported on the Connect:Direct server.</p></li>
<li><p>Generate a local or a private <a href="../../../c_st_setup/c_st_certificates/r_st_certificate_types">certificate</a> in {{< SecureTransport/componentshortname  >}} whose common name field matches the Connect:Direct local user that is going to be used to log in to the Connect:Direct server.</p></li>
<li>Import the certificate in the Connect:Direct server.</li>
<li>In the transfer site configuration, select the <strong>Use Certificate</strong> checkbox and specify the <strong>Certificate Alias</strong> used for connecting to the Connect:Direct server. You can either select the private certificate you generated at <em>Step 2</em> from the drop down or import a certificate.</li>
</ol>
<p>When certificate authentication is enabled, the connection uses the default TLS 1.2 protocol and compatible ciphers.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>After reverting the SecureTransport October 2020 Update, the Connect:Direct certificate-based authentication feature will not work, although the certificate placeholder remains visible on the transfer site definition page for sites created using a site template.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><strong>Send Options</strong>         </td>
      </tr>
      <tr>
         <td>Send Script         </td>
         <td><p>Specifies the Connect:Direct process to execute when uploading a file to a remote site. You must provide a script for either the Send Options or the Receive Options. This field must contain a valid Connect:Direct process language script. You can use expression language variables such as <code>${stenv.target}</code> in the script. For example, you can use the script field to execute a copy command. The remote server you are calling must be identified by its alias in the script.</p>
<p>To correctly identify the file name in a script you must use the variable <code>${cd_transfer_file}</code>. The variable is required because the file names might not be known at the time you write the script.</p>
<p>When creating an upload script you must use <code>${cd_transfer_file}</code> instead of the file name of the file being uploaded.</p>
<p>You cannot enter spaces-only values in this field.</p>         </td>
      </tr>
      <tr>
         <td><strong>Receive Options</strong>         </td>
      </tr>
      <tr>
         <td>Receive Script         </td>
         <td><p>Specifies the Connect:Direct process to execute when downloading a file from a remote site. You must provide a script for either the Send Options or the Receive Options. This field must contain a valid Connect:Direct process language script. You can use expression language variables such as <code>${stenv.target}</code> in the script. For example, you can use the script field to execute a copy command. The remote server you are calling must be identified by its alias in the script.</p>
<p>To correctly identify the file name in a script you must use the variable <code>${cd_transfer_file}</code>. The variable is required because the file names might not be known at the time you write the script.</p>
<p>When creating a download script you must use <code>${cd_transfer_file}</code> to specify the directory where downloaded files are saved. When downloading a single file, use <code>${cd_transfer_file}&lt;path_separator&gt;&lt;file_name&gt;</code>. For example, <code>${cd_transfer_file}/xls_sheet.xls</code>.</p>
<p>You cannot enter spaces-only values in this field.</p>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> The Send Script and Receive Script accept regular expressions. For more information on writing Connect:Direct scripts, refer to the Connect:Direct documentation.

You can use a site template to define a Connect:Direct transfer site. For more information, see [Site templates](../../../c_st_advancedaccountadministration/c_st_sitetemplates#Advanced_Accounts_2036285406_1131467).

**Related topics:**

-   [AS2 transfer sites](../r_st_as2transfersites)
-   [File services interface transfer sites](../r_st_fileservicesinterfaceprotocoltransfersites)
-   [Folder Monitor transfer sites](../r_st_foldermonitortransfersites)
-   [FTP(S) transfer sites](../transfersites-ftp)
-   [Generic HTTP transfer sites](../transfersites-generichttp)
-   [HTTP(S) transfer sites](../transfersites-http)
-   [PeSIT transfer sites](../transfersites-pesit)
-   [SSH transfer sites](../transfersites-ssh)
-   [System to Human transfer sites](../transfersites-s2h)
-   [Manage transfer sites](../t_st_transfersites)
