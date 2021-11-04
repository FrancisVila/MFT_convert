{
    "title": "Installer reference",
    "linkTitle": "Axway Installer reference",
    "weight": "80"
}This section provides information about the Axway Installer.

## About Axway Installer

The Axway Installer is an installation program for uniform and consistent installation of Axway products. The installer is used to install, configure, update, and uninstall <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>.

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> <span class="mc-variable axway_variables.Component_Version variable">5.5</span> uses Axway Installer version 4.10.6 SP7.

## Installer modes

The installer has the following installation modes:

-   GUI mode is supported on Windows, UNIX and Linux. However, to use on UNIX platforms, the installer requires an X-Window environment. To use an X-Window distributed environment, you must export the DISPLAY environment variable: export DISPLAY=myhost.mydomain:0.0
-   Console mode displays a series of prompts requiring user responses or actions.

## Installer functions

The installer command files are for invoking installer functions in GUI or console mode.

Before installing, Install is the only available function, invoked with the setup file in the root directory of the installation package.

After installing, the Update, and Uninstall functions are available. The scripts for those functions are in the root installation directory.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Function         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Mode         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">UNIX/Linux         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Windows         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Install         </td>
         <td><p>GUI</p>         </td>
         <td><pre><code>setup.sh</code></pre>         </td>
         <td><pre><code>setup32.exe</code></pre>
<pre><code>setup64.exe</code></pre>         </td>
      </tr>
      <tr>
         <td>Console         </td>
         <td><pre><code>setup.sh –m console</code></pre>         </td>
         <td><pre><code>setup32 –m console</code></pre>
<pre><code>setup64 –m console</code></pre>         </td>
      </tr>
      <tr>
         <td>Update         </td>
         <td><p>GUI</p>         </td>
         <td><pre><code>update.sh</code></pre>         </td>
         <td><pre><code>update32.exe</code></pre>
<pre><code>update64.exe</code></pre>         </td>
      </tr>
      <tr>
         <td>Console         </td>
         <td><pre><code>update.sh –m console</code></pre>         </td>
         <td><pre><code>update32 –m console</code></pre>
<pre><code>update64 –m console</code></pre>         </td>
      </tr>
      <tr>
         <td>Uninstall         </td>
         <td><p>GUI</p>         </td>
         <td><pre><code>uninstall.sh</code></pre>         </td>
         <td><pre><code>uninstall32.exe</code></pre>
<pre><code>uninstall64.exe</code></pre>         </td>
      </tr>
      <tr>
         <td>Console         </td>
         <td><pre><code>uninstall.sh –m console</code></pre>         </td>
         <td><pre><code>uninstall32.exe –m console</code></pre>
<pre><code>uninstall64.exe –m console</code></pre>         </td>
      </tr>
   </tbody>
</table>

The Configure function enables you to change settings that were applied during installation.

The Update function enables you to apply or remove service packs and patches.

The following sections provide more details on how the installer functions are used with <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>.

-   <a href="install" class="MCXref xref">Install product</a>
-   <a href="update" class="MCXref xref">Update product</a>
-   <a href="remove" class="MCXref xref">Remove updates</a>
-   <a href="uninstall" class="MCXref xref">Uninstall product</a>

## Display command

The `display `command lists information about all installed products. The command is named *display.bat* on Windows and *display.sh* on UNIX and Linux. Run it from the root installation directory.

If you enter the command without parameters, the command lists:

-   All products and versions that are installed
-   All the service packs that have been applied

Use the `name` parameter to display the installation history of a single product. For example:

`display -n <product name>`

## Installed directories

The Axway Installer creates the following sub-directories:

-   **Configuration**  
    Includes the configuration file for each installed product
-   **Documentation**  
    User documentation
-   **Installer**  
    Files used by the installer
-   **Java**  
    The deployed JRE used by the installer and Axway products
-   **SilentFile**  
    Includes the silent file for each installed product
-   **synInstall**  
    Installer internal files that are used to manage the installed infrastructure
-   **Tools**  
    Tools used by the installer to manage infrastructure instances. You can use some of these tools. For example, XDBM and SilentFileEditor.

## Hostname

Hostname corresponds to the object assigned to a physical server. In the installer, hostname is required for the following reasons:

-   In a page where you configure which network interface the product is going to listen for an incoming connection. In this case, enter one of the following values:
    -   Hostname
    -   Fully qualified domain name
    -   IP address of the machine
    -   Specific string (0.0.0.0 or \*) indicating that you want the product to listen on all network interfaces if your machine has more than one
-   In a page where you configure how your product is going to connect to another product. In this case, it is strongly recommended to use either the fully qualified name or the IP address of the remote machine.
