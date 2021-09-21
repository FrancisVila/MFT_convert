{
    "title": "Install SecureTransport Server on Windows with the embedded database",
    "linkTitle": "Install SecureTransport Server on Windows with the embedded database",
    "weight": "110"
}Use this procedure to install SecureTransport on Windows in all cases where it uses the embedded database server:

-   Stand-alone SecureTransport Server
-   SecureTransport Server in a Standard Cluster
-   SecureTransport Edge  

Before you install SecureTransport, check the pre-installation information and prerequisites.

This procedure assumes that SecureTransport is not installed on the system. Only one instance of SecureTransport Server or SecureTransport Edge is supported in a production environment. To upgrade an existing installation, refer to the *SecureTransport Upgrade Guide*.

During the installation, do not close any console windows that are opened.

1.  Download the SecureTransport installation package for Windows from [Axway Support.](https://support.axway.com/)  
    The name of the package is `SecureTransport_5.5_Install_win-x86-64_<BuildNumber>.zip`.

2.  Extract the zip file into a directory on the same drive where you are going to install SecureTransport. The name of the extracted folder is `SecureTransport_5.5_Install_win-x86-64`.

3.  In the extracted folder, run the `setup64.exe` executable to begin the installation process.

4.  The installer loads and displays the *Welcome* page. Click **Next** to proceed.

5.  Read and accept the terms of the license agreement to continue.
      
    (Optional) Click **Print** to print out a copy of the license agreement.

6.  Specify the **Installation Directory** to which the installer files to be deployed. It must reside on the same drive as the installation files. You can enter a custom location by using its absolute path.  

    <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The directory path must not contain the tilde (~) character. Also, we recommend using a directory path without special characters and spaces.          </td>      </tr></table>

      
      
    
    This is the location where the installer installs its files, including files required to update and uninstall
    SecureTransport 5.5. It is also used as a parent directory of the SecureTransport default installation location.   
    Click **Next** to continue.

7.  Select the module or modules to install, **Server** or **Edge** and click **Next**.

8.  Specify a location to install SecureTransport. By default, SecureTransport is installed in a sub-directory of the Axway Installer installation directory (specified at step 6). You can either accept the default or specify a new location following the requirements:   
    
    -   The SecureTransport installation directory must be specified using an absolute path. It must not contain the tilde (~) character; letters and digits are acceptable.
    -   It must reside on the same drive as the SecureTransport installation files.
    -   The SecureTransport installation directory and the Axway Installer components must never be in the same directory.

      
    SecureTransport Server is installed in the `STServer` sub-directory of the specified installation directory. The SecureTransport installation directory is referred to as `<FILEDRIVEHOME>` throughout the product documentation.  
    Click **Next** to continue.

9.  If you selected **Edge**, the installer displays another *Database settings* page. Continue with step 11.

10. If you selected **Server**, to install SecureTransport Server in a Standard Cluster or as a stand-alone Server using an embedded database, select **Embedded Database (*MariaDB or MySQL*)** and click **Next**.

11. Set the port for the embedded database, and click **Next**.

12. Accept or modify the configuration settings.
    -   **SSL Admin UI Port** – default 444
    -   **Tomcat Shutdown Port** – default 8005
    -   **Enable Nightly Log Rotation** – Select if you want the system to perform automatic backup and purging of log files on a nightly basis. When this feature is enabled, SecureTransport Server backups log files, generated on the respective day, and creates a new one for the subsequent day. The server takes a back up and creates a new log file at 23:59 or 00:00 hours, depending on the log file type. This option is enabled by default. You can enable or disable the nightly log rotation after installation - see the <span cshid="admin" data-version="5.3.5">*SecureTransport Administrator's Guide*</span> for more information.
    -   **Secret File Path**– The path to the `taeh` secret file you copied to this system. If blank, the installer creates a new secret file.
    -   If you are installing the first server in a cluster, you can specify a secret file or have the installer create one. Before you install SecureTransport on the other cluster nodes, you must copy the secret file to those systems.
    -   If you are installing the second or a subsequent server in the cluster, you must use the secret file you copied from the first server. See [Secret file](../../../prereqs_overview/secret_file).

      
    Click **Next** to continue.

13. On the *Ready to install* page, click **Install** to start the installation.   
    The installation process can take several minutes to complete.

14. When the installation is complete, the installer displays the *Installation completed* page. Click **Next** to see summary information about your SecureTransport installation.

15. Click **Finish** to exit the installer.  
    You can click **Update** to install patches or service packs without leaving the installer. Refer to the Readme files for the patches or service packs.

The installer also creates a log file, `<AxwayHome>/install.log`.

After successfully installing SecureTransport, you must perform several post-installation steps, such as updating your SecureTransport license, enabling, configuring, and starting the SecureTransport services. For more information, see the <span cshid="gs" data-version="5.3.5">*SecureTransport Getting Started Guide*</span>.

**Related topics:**

-   [Install SecureTransport Server on Windows with an external database](../install_on_windows_with_external_database)
-   [Cancel the Windows installation](../cancel_windows_installation)
