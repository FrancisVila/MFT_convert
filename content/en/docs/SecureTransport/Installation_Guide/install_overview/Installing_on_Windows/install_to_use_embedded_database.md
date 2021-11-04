{
    "title": "Install SecureTransport on Windows with the embedded database",
    "linkTitle": "Install SecureTransport Server on Windows with the embedded database",
    "weight": "110"
}Use this procedure to install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> on Windows in all cases where it uses the embedded database server:

-   Stand-alone <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server
-   <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server in a Standard Cluster
-   <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge  

Before you install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, check the pre-installation information and prerequisites.

This procedure assumes that <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> is not installed on the system. Only one instance of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server or <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge is supported in a production environment. To upgrade an existing installation, refer to the *<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Upgrade Guide*.

During the installation, do not close any console windows that are opened.

1.  Download the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation package for Windows from [Axway Support.](https://support.axway.com/)  
    The name of the package is `SecureTransport_5.5_Install_win-x86-64_<BuildNumber>.zip`.

2.  Extract the zip file into a directory on the same drive where you are going to install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>. The name of the extracted folder is `SecureTransport_5.5_Install_win-x86-64`.

3.  In the extracted folder, run the `setup64.exe` executable to begin the installation process.

4.  The installer loads and displays the *Welcome* page. Click **Next** to proceed.

5.  Read and accept the terms of the license agreement to continue.  
    (Optional) Click **Print** to print out a copy of the license agreement.

6.  Specify the **Installation Directory** to which the installer files to be deployed. It must reside on the same drive as the installation files. You can enter a custom location by using its absolute path.  

    > **Note:**
    >
    > The directory path must not contain the tilde (~) character. Also, we recommend using a directory path without special characters and spaces.

      
      
    This is the location where the installer installs its files, including files required to update and uninstall
    <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> <span class="mc-variable axway_variables.Component_Version variable">5.5</span>. It is also used as a parent directory of the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> default installation location.  
    Click **Next** to continue.

7.  Select the module or modules to install, **Server** or **Edge** and click **Next**.

8.  Specify a location to install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>. By default, SecureTransport is installed in a sub-directory of the Axway Installer installation directory (specified at step 6). You can either accept the default or specify a new location following the requirements:  
    -   The SecureTransport installation directory must be specified using an absolute path. It must not contain the tilde (~) character; letters and digits are acceptable.
    -   It must reside on the same drive as the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation files.
    -   The SecureTransport installation directory and the Axway Installer components must never be in the same directory.

      
    <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server is installed in the `STServer` sub-directory of the specified installation directory. The <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation directory is referred to as `<FILEDRIVEHOME>` throughout the product documentation.  
    Click **Next** to continue.

9.  If you selected **Edge**, the installer displays another *Database settings* page. Continue with step 11.

10. If you selected **Server**, to install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server in a Standard Cluster or as a stand-alone Server using an embedded database, select **Embedded Database (*MariaDB or MySQL*)** and click **Next**.

11. The following step depends on whether you are using MySQL or MariaDB  
    For MySQL, set the port for the embedded database, and click **Next**.  
    For MariaDB, provide answers to the following:  
    -   **Port**: select a new port number for the embedded database installed by SecureTransport, or accept the default setting.
    -   **Use secure connection**: When selected (default), the database connection will be established over a secure connection.
        -   **Auto generate certificates**: When selected, the certificates required for a secure connection to the database will be automatically generated by <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> with a validity period of 365 days. In this case, any value in **Certificate Authority File Path**, **Server Private key File Path** or **Server Certificate File Path** is ignored.
    -   **Certificate Authority File Path**: The absolute file path to the CA certificate in PEM format, used to create and sign the Server Private key and Server Certificate files.  
        Only applicable when **Use secure connection** is enabled and **Auto generate certificates** is disabled.
    -   **Server Private key File Path**: The absolute file path to the private key in PEM format, used by the MariaDB Server.  
        Only applicable when **Use secure connection** is enabled and **Auto generate certificates** is disabled.
    -   **Server Certificate File Path**: The absolute file path to the X.509 certificate in PEM format used by the MariaDB Server.  
        Only applicable when **Use secure connection** is enabled and **Auto generate certificates** is disabled.

12. Accept or modify the configuration settings.
    -   **SSL Admin UI Port** – default 444
    -   **Tomcat Shutdown Port** – default 8005
    -   **Enable Nightly Log Rotation** – Select if you want the system to perform automatic backup and purging of log files on a nightly basis. When this feature is enabled, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server backups log files, generated on the respective day, and creates a new one for the subsequent day. The server takes a back up and creates a new log file at 23:59 or 00:00 hours, depending on the log file type. This option is enabled by default. You can enable or disable the nightly log rotation after installation - see the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span> for more information.
    -   **Secret File Path**– The path to the `taeh` secret file you copied to this system. If blank, the installer creates a new secret file.
    -   If you are installing the first server in a cluster, you can specify a secret file or have the installer create one. Before you install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> on the other cluster nodes, you must copy the secret file to those systems.
    -   If you are installing the second or a subsequent server in the cluster, you must use the secret file you copied from the first server. See <a href="../../../prereqs_overview/secret_file#beforeinstallst_3365039947_1107715" class="MCXref xref">Secret file</a>.

      
    Click **Next** to continue.

13. On the *Ready to install* page, click **Install** to start the installation.  
    The installation process can take several minutes to complete.

14. When the installation is complete, the installer displays the *Installation completed* page. Click **Next** to see summary information about your <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation.

15. Click **Finish** to exit the installer.  
    You can click **Update** to install patches or service packs without leaving the installer. Refer to the Readme files for the patches or service packs.

The installer also creates a log file, `<AxwayHome>/install.log`.

After successfully installing <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, you must perform several post-installation steps, such as updating your <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> license, enabling, configuring, and starting the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> services. For more information, see the <span class="redirect_st_gs" cshid="gs" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Getting Started Guide*</span>.

**Related topics:**

-   <a href="../install_on_windows_with_external_database" class="MCXref xref">Install SecureTransport Server on Windows with an external database</a>
-   <a href="../cancel_windows_installation" class="MCXref xref">Cancel the Windows installation</a>