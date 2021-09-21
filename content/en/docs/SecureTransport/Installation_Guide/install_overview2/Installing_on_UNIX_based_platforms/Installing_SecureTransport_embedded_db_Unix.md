{
    "title": "Install SecureTransport on Unix with the embedded database",
    "linkTitle": "Install SecureTransport on Unix with the embedded database",
    "weight": "100"
}Use this installation procedure to install SecureTransport on UNIX-based platforms where the installation will use the embedded database server:

-   Stand-alone SecureTransport Server
-   SecureTransport Server in a Standard Cluster
-   SecureTransport Edge

Check the pre-installation information and prerequisites before you install.

This procedure assumes that SecureTransport is not installed on the system. Only one instance of SecureTransport Server or SecureTransport Edge is supported in a production environment. To upgrade an existing installation, refer to the *SecureTransport Upgrade Guide*.

Log in to the system as the user who will run SecureTransport.

Download the SecureTransport install package for your operating system:  
`SecureTransport_5.5_Install_<OS>-<processor>_<BuildNumber>.zip`
  
where the placeholders represent the following:

-   `<OS>` is the operating system: `aix` (for IBM AIX), `linux` (for Linux)
-   `<processor>` is the type of processor running the operating system: `power-64` or `x86-64`.
-   `<BuildNumber>` is the actual build number listed in the installer executable file.

Copy the install package into a temporary directory and navigate to that temporary directory.

Extract the installation files using the following commands:

<table cellspacing="0">   <col/>   <tbody>      <tr>         <td>            <p>unzip SecureTransport_5.5_Install_&lt;OS&gt;-&lt;processor&gt;_<code>&lt;BuildNumber&gt;</code>.zip<br/></p>         </td>      </tr>   </tbody></table>

Enter the following commands to run the Axway Installer:

<table cellspacing="0">   <col/>   <tbody>      <tr>         <td>./setup.sh -m console         </td>      </tr>   </tbody></table>

  
The installer initializes and displays a welcome message and a prompt.

Press Enter.  
The installer will display the license agreement page by page.
After each one there is a **Press ENTER to continue** prompt.
After all license agreement pages are displayed, the installer displays the license agreement and the following prompt (for accepting or rejecting the license agreement):

<table cellspacing="0">   <col/>   <tbody>      <tr>         <td>            <p>[1] I accept the terms of the license agreement.<br>[2] I do not accept the terms of the license agreement.</br></p>            <p><br>Enter a number [1-2] to select an option or (Previous, Quit).<br>:&gt;2</br></br></p>         </td>      </tr>   </tbody></table>

Enter 1 to accept the license agreement. Enter 2 to reject the license agreement and cancel the installation.

On the prompt for Installation directory, specify an installation location for Axway installer:  


<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>----------------------------------------
							<br>Installation directory<br/>----------------------------------------<br/>Specify the directory where you want to install the products and documentation.<br/>1: Installation Directory:           /&lt;userHome&gt;/Axway</br></p>
            <p>
<br/>Enter 1 to select an option or (Next, Previous, Quit).<br/>:&gt;Next</p>
         </td>
      </tr>
   </tbody>
</table>

  


-   To accept the default installation directory, press Enter. The default installation directory for Axway Installer is `/<userHome>/Axway` , where `<userHome>` represents the home directory of the user running the installation.
-   To change the installation location, enter 1 and then enter the absolute path to your desired installation directory.

  
In this directory, the Axway installer files are deployed. It is used as the parent directory in the default SecureTransport installation location which you specify at a later step (10).  


<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><span>SecureTransport</span> should not share the same installer directory with another Axway products.         </td>
      </tr>
</table>

Choose the installation type. Press Enter to accept the default, SecureTransport Server.
  


<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>----------------------------------------<br>Modules<br>----------------------------------------<br>Select the modules you want to install, then type Next to continue the
							configuration.<br><br/>Axway SecureTransport V<span>5.5</span>:<br/>1 :[x] Server<br/>2 :[ ] Edge<br/>3 :[ ] ServerDocker<br/>4 :[ ] EdgeDocker</br></br></br></br></p>
            <p>
<br/>Enter a number[1-4] (Next, Previous, Quit)<br/>:&gt;Next</p>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The <code>EdgeDocker</code> and <code>ServerDocker</code> modules  are used <b>ONLY</b> in the docker image build process and are not supported for other purposes. For more information, refer to the <span>SecureTransport</span> Containerized Deployment Guide.         </td>
      </tr>
</table>

Specify an installation directory for SecureTransport:  


<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>----------------------------------------<br>Installation directory<br/>----------------------------------------<br/>To specify the directory where the product is installed, type the path directly,
							or press Enter to select the displayed default.<br/>1: Select the installation directory for SecureTransport:<br/>&lt;AxwayHome&gt;/SecureTransport</br></p>
            <p>
<br/>Press 1 to change the selected option or (Next, Previous, Quit).<br/>:&gt;Next</p>
         </td>
      </tr>
   </tbody>
</table>

-   To accept the default location, press Enter. The default SecureTransport installation folder is `<AxwayHome>/SecureTransport`, where `<AxwayHome>` is the directory you specified in step 8.
-   To change the SecureTransport installation location, enter 1 and enter the absolute path to your desired installation directory.

Consider the following:

-   Do not use the directory where you copied the installer files.
-   All SecureTransport Servers in a cluster must use the same installation directory.
-   The name of the SecureTransport installation directory cannot contain space characters, the tab character, or the `~` character. For example, `/root/Axway/STServer` is valid, but `/root/Axway/ST   Server` is not.

This installation directory is referred to as `<FILEDRIVEHOME>` throughout this document and other SecureTransport documents.

On the database selection prompt, press Enter to accept the default, the embedded database.
  


<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>----------------------------------------<br/></p>
            <p> </p>
            <p>Database settings<br/>----------------------------------------<br/>[1] Embedded Database (MariaDB)<br/><![CDATA[ ]]><i>or [1] Embedded Database (MySQL)</i><br/>[2] External Oracle Database<br/>[3] External Microsoft SQL Server Database <br/>[4] External PostgreSQL Database</p>
            <p> </p>
            <p>Enter a number [1-4] to select an option or (Previous, Quit).<br/>:&gt;1</p>
         </td>
      </tr>
   </tbody>
</table>

  


<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">For installation using an external database, see <a href="../installing_securetransport_server_external_db_unix">Install SecureTransport Server on Unix with an external database</a>.         </td>
      </tr>
</table>

The following step depends on whether you are using MySQL or MariaDB  
**On MySQL**, the installer displays the following dialog:

<table cellspacing="0">   <col/>   <tbody>      <tr>         <td>            <p>----------------------------------------<br/></p>            <p>Database settings<br>----------------------------------------<br/></br></p>            <p>Provide the settings for the MySQL database:</p>            <p>1: Port:  33060<br/></p>            <p> </p>            <p>Press 1 to change the selected option or (Next, Previous, Quit).<br/>:&gt;Next</p>         </td>      </tr>   </tbody></table>

  


The information required is:

-   **Port:** select a new port number for the embedded database installed by SecureTransport or accept the default setting.  

  
**On MariaDB**, provide answers to the following dialog:

<table cellspacing="0">   <col/>   <tbody>      <tr>         <td>            <p>----------------------------------------</p>            <p>Provide the settings for the MariaDB database:</p>            <p>1: Port:                             33060</p>            <p>2: Use secure connection:            true</p>            <p>3: Certificate Authority File Path:</p>            <p>4: Server Private key File Path:</p>            <p>5: Server Certificate File Path:</p>            <p> </p>            <p>Enter a number [1-5] to select an option or (Next, Previous, Quit).</p>            <p>:&gt;Next</p>         </td>      </tr>   </tbody></table>

  
The information required is:

-   **Port**: select a new port number for the embedded database installed by SecureTransport, or accept the default setting.
-   **Use secure connection**: When selected, the database connection will be established over a secure connection. The default value is: true.
-   **Certificate Authority File Path**: The absolute file path to the CA certificate in PEM format, used to create and sign the Server Private key and Server Certificate files.  
    Only applicable when 'Use secure connection' is set to `true`.
-   **Server Private key File Path**: A private key in PEM format, used by the MariaDB Server.  
    Applicable only when 'Use secure connection' is set to `true`.
-   **Server Certificate File Path**: an X.509 certificate in PEM format used by the MariaDB Server.  
    Applicable only when 'Use secure connection' is set to `true`.

Note: All certificates need to be regenerated and DB configuration updated prior to certificates' expiration.  
  

The installer displays the default SecureTransport ports, nightly log rotation, and import secret file configuration:

<table cellspacing="0">   <col/>   <tbody>      <tr>         <td>----------------------------------------<br/>Configuration<br/>----------------------------------------<br/>  Select the options that you want to enable:<br/>  SecureTransport Ports<br/>1: SSL Admin UI Port:           444<br/>2: Tomcat Shutdown Port:        8005<br/>3: Enable Nightly Log Rotation: true<br/>  Import Secret File<br/>To synchronize the configuration of this ST Server with another ST Server you
								must import the same secret file (located on the remote ST Server at:
								&lt;installation path&gt;/bin/taeh). Otherwise, leave the field empty
								to generate a new secret file.<br/>4: Secret File Path:<br/><br/>          

							Enter a number [1-4] to select an option or (Next, Previous, Quit).<br/>:&gt;Next         </td>      </tr>   </tbody></table>

Accept or modify the default configuration.  
The information required is:

-   **SSL Admin UI Port** – The port used to connect to the Administration Tool. When you install SecureTransport as a non-root user, the default value for Admin port number is 8444.
-   **Tomcat Shutdown Port** – The port used to shut down the Tomcat server
-   **Enable Nightly Log Rotation** – Select if you want the system to perform automatic backup and purging of log files on a nightly basis. When this feature is enabled, SecureTransport Server backups log files, generated on the respective day, and creates a new one for the subsequent day. The server takes a back up and creates a new log file at 23:59 or 00:00 hours, depending on the log file type. This option is enabled by default. You can enable or disable the nightly log rotation after installation. For more information, see the <span cshid="admin" data-version="5.3.5">*SecureTransport Administrator's Guide*</span>, Server Log Rotation Scheduling.
-   **Secret File Path** – The path to the secret file you copied from another SecureTransport Server installation to this system, if blank, the installer creates a secret file (See [Secret file](../../../prereqs_overview/secret_file).)

  
When you have modified these values as required for your installation, press Enter.  
The installer prepares the installation execution and displays its last prompt:

<table cellspacing="0">   <col/>   <tbody>      <tr>         <td>            <p>----------------------------------------<br>Installation execution<br>----------------------------------------<br>All selected products are ready to install. Type Next to start installing. If
							not, type Previous to make changes.</br></br></br></p>            <p><br/>Enter (Next, Previous, Quit).<br/>&gt;Next</p>         </td>      </tr>   </tbody></table>

Press Enter to start the installation.  
The installer displays progress messages as it completes the installation tasks. When the installation is complete, a success message is displayed.

Press Enter to exit the installer or select update mode to apply patches or service packs without leaving the installer.

The installer also creates a log file, `<AxwayHome>/install.log`.

After successfully installing SecureTransport, you must perform a number of post-installation steps, such as applying your SecureTransport licenses, and enabling, configuring, and starting the SecureTransport services. For more information, see the <span cshid="gs" data-version="5.3.5">*SecureTransport Getting Started Guide*</span>.

**Related topics:**

-   [Install SecureTransport Server on Unix with an external database](../installing_securetransport_server_external_db_unix)
-   [Run SecureTransport as a service on UNIX-based platforms after non-root installation](../running_st_as_service_unix)
