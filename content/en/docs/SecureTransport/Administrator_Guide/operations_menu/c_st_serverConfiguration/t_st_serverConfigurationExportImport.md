{
    "title": "Export and import server configuration",
    "linkTitle": "Export and import server configuration",
    "weight": "190"
}{{< SecureTransport/componentshortname  >}}{{< SecureTransport/releasenumber  >}} supports import from the following releases, patched to the latest patch or service pack – 5.4, 5.3.6, 5.3.5, 5.3.3, 5.3.1, 5.3.0, and 5.2.1. The system configuration can be imported from export files produced by the same {{< SecureTransport/componentshortname  >}} deployment only.

> **Note:**
>
> When you import a server configuration, the process overwrites the current configuration. If an improper configuration file is imported (for example, a blank file or potentially an export from another server), no error message is displayed and the configuration files are overwritten. Use system export with caution.

> **Note:**
>
> System import settings are deployment specific and import and export are to be used for restoration of the environment only, not for the migration or automation of environment deployments.

You can export and import server configuration information in a ZIP file.

> **Note:**
>
> SecureTransport does not support exporting the server configuration from one Enterprise Cluster (EC) and importing the server configuration into another EC cluster.

Because {{< SecureTransport/componentshortname  >}} copies shared server configuration parameters to every node in a cluster upon import, you only import the shared server configuration once for the whole cluster.

The compressed `export_configuration.zip` file includes the files from the &lt;FILEDRIVEHOME> directory plus XML files that record system the configuration parameters stored in the database (including those set on the *Server Configuration* page and elsewhere in the Administration Tool), the holiday schedule, the local certificates, certificate signing requests, and trusted CAs.

> **Note:**
>
> Database settings like port, password, and so forth are not intended to be exported because database settings are node specific.

You can export the server configuration files using the *Import or Export Server Configuration* page or command line utility. Use the command line utility to customize which folders and files will be exported. For more information, see <a href="#Export" class="MCXref xref">Export server configuration files from the command line</a> and <a href="#Import" class="MCXref xref">Import server configuration files from the command line</a>.

Any administrator with import and export configuration privileges can access the *Import or Export Server Configuration* page to import or export the server configuration information. Any administrator who can access the server can use the command line to import or export server information.

You must supply a password that {{< SecureTransport/componentshortname  >}} uses to encrypt sensitive information such as private keys and custom attributes during the export process. When you import the server configuration information, you must type the password to import the server configuration files and decrypt the sensitive information.

The imported files overwrite the existing files, the database is updated with the parameter values from the imported files, the imported files are modified to support changes made to {{< SecureTransport/componentshortname  >}}, and the importer adds any new properties needed for the features introduced in the current version of {{< SecureTransport/componentshortname  >}}. At the same time, the importer preserves any custom changes you have made to the imported files, applying them to the current version of {{< SecureTransport/componentshortname  >}}.

The following topics provide how-to instructions for importing and exporting the server configuration, certificates, and messages:

-   <a href="#Export_limit" class="MCXref xref">Export user limit messages</a>
-   <a href="#Export_CA" class="MCXref xref">Export and import Internal CA files</a>
-   <a href="#Export_conf" class="MCXref xref">Export server configuration using the Administration Tool</a>
-   <a href="#Export" class="MCXref xref">Export server configuration files from the command line</a>
-   <a href="#Import_conf" class="MCXref xref">Import server configuration files using the Administration Tool</a>
-   <a href="#Import" class="MCXref xref">Import server configuration files from the command line</a>

**Related topics:**

-   <a href="../c_st_editable_server_configuration_parameters" class="MCXref xref">Editable server configuration parameters</a>
-   <a href="../c_st_local_server_configuration_parameters" class="MCXref xref">Local server configuration parameters</a>
-   <a href="../t_st_serverconfigurationparameters" class="MCXref xref">View and change server configuration parameters</a>
-   <a href="../t_st_serverconfigurationfiles" class="MCXref xref">Update configuration files</a>

<span id="Export_limit"></span>

## Export user limit messages

To export messages defined on the *Limit User Access* page for successful import, add lines for all files that match `lib/msgs/msg.*Class*.*` pattern to `<FILEDRIVEHOME>/conf/export.conf` before exporting.

<span id="Export_CA"></span>

## Export and import Internal CA files

For {{< SecureTransport/componentshortname  >}} 5.0 and later, the Internal CA certificate is exported with system export and with account export. In both cases, the private key for the CA is not exported. You cannot use an imported Internal CA to sign additional certificates without the correct private key. To preserve the Internal CA private key, configure server export and import to include the private key. Perform the following procedures before you export the system configuration files. For more information on exporting and importing accounts, see <a href="../../../c_st_advancedaccountadministration/c_st_accountimportandexport#Advanced_Accounts_2036285406_1153799" class="MCXref xref">Account export and import</a>. For more information about exporting and importing the Internal CA, see <a href="../../../c_st_setup/c_st_certificates/t_st_internalca#top" class="MCXref xref">Manage the internal CA</a>.

### Export the Internal CA with the private key

1.  Add the following lines to the `<FILEDRIVEHOME>/conf/export.conf` file:  
    `lib/certs/db/ca-crt.pem`  
    `lib/certs/db/ca-key.pem`  
    `lib/certs/db/index`  
    `lib/certs/db/serial`
2.  Export the system configuration.  
    It contains the Internal CA with its private key.

### Import the Internal CA with the private key

1.  Delete the temporary Internal CA generated during installation, so that the Internal CA is not incorrectly imported as CA-old.
2.  Import the system configuration.

<span id="Export_conf"></span>

## Export server configuration using the Administration Tool

You can export and download server configuration using the {{< SecureTransport/componentshortname  >}} Administration Tool. The ZIP file is also automatically backed up on the server as `<FILEDRIVEHOME>/var/tmp/export_configuration.zip`. You cannot specify the file name and location on the server, and the back up file overwrites any existing back up file.

When you export the server configuration from the Administration Tool, {{< SecureTransport/componentshortname  >}} uses the file `<FILEDRIVEHOME>/conf/export.conf` to read the list of configuration files to be exported. In addition, the files in the `<FILEDRIVEHOME>/brules/local/wptdocuments` directory are always included.

You can control the file name and location, and the list of files to be exported by using the command line tool to export your server configuration files. For more information, see <a href="#Export" class="MCXref xref">Export server configuration files from the command line</a>.

1.  On the *Server Configuration* page, click **Import/Export Server Configuration**.  
    The *Import or Export Server Configuration* page is displayed.
2.  Select **Export Server Configuration**.
3.  Type the file password in the **Password** and **Re-enter Password** fields.
4.  Click **Export**. The *Export Complete* prompt is displayed. The ZIP file is save as `<FILEDRIVEHOME>/var/tmp/export_configuration.zip`.
5.  To download the ZIP file to your local computer, click **Download Exported Configuration**. The *File Download* dialog box is displayed.
6.  Click **Save** to save the file to a new location or click **Open** to view the contents of the ZIP file.  
    To save the file, select the location for the exported server configuration data and click **Save**. You are returned to the Import or Export Server Configuration window.  
    If you clicked **Open**, the ZIP file attempts to open and display the contents of the file in a new window.  
    If you do not want to download the ZIP file, click **Cancel** to return to the *Import or Export Server Configuration* page.

<span id="Export"></span>

## Export server configuration files from the command line

You can export sever configuration information using a command line tool. When you are using the tool to export a server configuration, you must specify the file name and location that contains the exported configuration.

You can also specify which files you want to export by creating a list file with a `.conf` extension. This file contains the list of configuration files you want to export. This is useful when you have customized {{< SecureTransport/componentshortname  >}} and need to export additional files to those listed in the default export list. The default export list is located in `<FILEDRIVEHOME>/conf/export.conf`. Do not modify this file, but create a file with a new name if you need to make a new export list.

{{< SecureTransport/componentshortname  >}} provides a script called `system_export` that you can run from the command line to export the server configuration information to a ZIP file. The script has the following options:

-   `-exf=<export_file>` where `<export_file>` is the file name and location of the ZIP file. You must specify the file name.
-   `-ex1=<export_list>` where `<export_list>` is the file containing a list of all files to be exported. The `<export_list>` file name is relative to &lt;`FILEDRIVEHOME>`. The default is `conf/export.conf`.
-   `-help` displays the command format and options.

> **Note:**
>
> If you run system\_export without specifying any options, the help message is displayed.

During the export process, you are prompted for an export password. Later, when you import the exported configuration from the command line, you must use the same password for the import process. The following steps illustrate an example sever configuration export:

1.  Change to the `<FILEDRIVEHOME>/bin` directory.  
    If you installed {{< SecureTransport/componentshortname >}} on Windows, you can run the command without changing to the `/bin` directory.
2.  Type one of the following commands:
    -   `./system_export -exf=<export_file>` for UNIX-based systems
    -   `system_export -exf=<export_file>` for Windows

      
    where `<export_file>` is the name and location of the ZIP file you are creating.
3.  When prompted, type a password for the exported information.
4.  Confirm the password by typing it again when prompted.  
    The exported file is created in the specified location.

<span id="Import_conf"></span>

## Import server configuration files using the Administration Tool

You can import server configuration information for a cluster or only the local server configuration information for a single server using the Administration Tool. You must know the password entered during the server configuration export process.

1.  On the *Server Configuration* page, click **Import/Export Server Configuration**.  
    The *Import or Export Server Configuration* page is displayed.
2.  Select **Import Server Configuration**.
3.  Select the **Configuration File** by clicking **Choose File**. The file must be in the zip format.
4.  Type the **Password** to use to encrypt sensitive information in the file. You must use the password specified when the file was exported.
5.  Select the options:
    1.  Select **Cancel Import on Error** to stop the import process if any error is encountered. This option is selected by default. If the import process is stopped, no changes are made to the server. If you clear this option and the password does not match, the import completes with a warning that information from the zip archive could not be decrypted.
    2.  Select **Continue on Version Mismatch** to import server configuration from a different version of {{< SecureTransport/componentshortname >}}.
    3.  Select **Import local configuration data only** to exclude cluster configuration data, for example, when you are importing configuration data into a {{< SecureTransport/componentshortname >}} Server that is in an existing cluster. This option is not available if **Continue on Version Mismatch** is selected.
6.  Click **Import**.  
    The *Import Complete* message is displayed and the server configuration import is successful. If you did not select **Import local configuration data only**, the imported cluster configuration data is propagated to all servers in the cluster.

> **Note:**
>
> When you import a server configuration, the process overwrites the current configuration. If an improper configuration file is imported (for example, an empty file), no error message is displayed and the configuration files are overwritten.

<span id="Import"></span>

## Import server configuration files from the command line

> **Note:**
>
> Before server configuration import from the command line, all services except the Administration Tool service should be stopped.

You can import server configuration information from the command line.

{{< SecureTransport/componentshortname  >}} provides a command named `system_import` that can be run from the command line to import information from the ZIP file. The command requires that the Administration Tool service is running on the {{< SecureTransport/componentshortname  >}} server where you run the command.

In a Standard Cluster (SC), run the `system_import` command on the primary server. When the import completes, the updates are automatically synchronized to the other servers in the Standard Cluster or Enterprise Cluster. The script comes with the following options:

-   `-exf=<export_file>` where `<export_file>` is the file name and location of the ZIP file. You must specify the file name.
-   `-coe=<tr>` where when set to `true`, the import stops if an error occurs and no changes are made to the server ("cancel on error"). If set to `false` the import continues if an error occurs. The default setting is `true`. If set this option to false and the password does not match, the import completes with a warning that information from the zip archive could not be decrypted.
-   `-ivm=<tr>` where when set to `true`, the import continues even if there is a version mismatch. Setting this option to `false` stops the import if there is a version mismatch. The default setting is `false`.
-   `-ilo` means import only local configuration parameters. This options requires `-ivm=false`.
-   `-help` displays the command format and options.

> **Note:**
>
> If you run system\_import without specifying any options, the help message is displayed.

1.  Change to the `<FILEDRIVEHOME>/bin` directory.  
    If you installed {{< SecureTransport/componentshortname >}} on Windows, you can run the command without changing to the `/bin` directory.
2.  Type one of the following commands:

-   `./system_import -exf=<export_file>` for UNIX-based systems  
    `system_import -exf=<export_file>` for Windows

where `<export_file>` is the file name and location of the ZIP file. You must specify the file name.

When prompted, type the password for the ZIP file. You must type the password created when the file was exported.  
The server configuration information is imported into {{< SecureTransport/componentshortname  >}}.

> **Note:**
>
> When you import a server configuration, the process overwrites the current configuration. If an improper configuration file is imported (for example, a blank file), no error message is displayed and the configuration files are overwritten.If you import the wrong configuration, and then immediately try to import the correct one, the command displays an error message regarding the database password. You must restart SecureTransport after each system import.
