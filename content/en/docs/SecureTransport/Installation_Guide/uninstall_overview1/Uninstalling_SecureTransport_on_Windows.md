{
    "title": "Uninstall SecureTransport on Windows",
    "linkTitle": "Uninstall SecureTransport on Windows",
    "weight": "100"
}This section explains how to uninstall SecureTransport from Windows.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When uninstalling <span>SecureTransport</span> in Microsoft Windows environments, <span>Axway</span> registry entries may be left behind. It is safe to manually remove the <span>Axway</span> registry entries  left behind.         </td>
      </tr>
</table>

If registry entries are left behind, run `regedit.exe` to start the Microsoft Windows registry and delete the following registry entries:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>HKEY_LOCAL_MACHINE\SOFTWARE\Axway Software<br/>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\<br/>    Uninstall\Axway_Installer_4.10.6 SecureTransport01         </td>
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
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In a cluster environment, stop all of the protocol servers and services on the node you want to uninstall and remove this node from the cluster before you uninstall it. For details refer to the <span data-cshid="admin" data-version="5.3.5"><em><span>SecureTransport</span> Administrator's Guide</em></span>.         </td>
      </tr>
</table>

1.  Prior to uninstallation, stop all SecureTransport processes and make sure that no SecureTransport files or directories are in use and that the Cygwin console and all Cygwin tools and services installed with your previous SecureTransport installation are closed. If necessary, close the Cygwin console and tools manually.
2.  Select **Start > Programs > Axway Software > Uninstall**.  
    The installer loads and displays the *Welcome* page.
3.  Click **Next** to proceed. The installer displays the *Ready to uninstall* page.
4.  Click **Uninstall** to start the uninstallation. The installer displays a confirmation dialog.
5.  If you have stopped all SecureTransport and related services as described in step 1, click **Yes**. The installer displays the *Uninstall in progress* page which shows the progress of the uninstallation.
6.  When uninstallation is complete, the installer displays the *Uninstall completed* page.
7.  Click **Next**. The installer displays the *Summary* page.
8.  Click **Finish** to close the installer.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can also use the Add/Remove Programs option in the Control Panel to uninstall <span>SecureTransport</span> Server or Edge or navigate to the Axway Installer installation folder and start <code>uninstall64.exe</code>.          </td>
      </tr>
</table>
