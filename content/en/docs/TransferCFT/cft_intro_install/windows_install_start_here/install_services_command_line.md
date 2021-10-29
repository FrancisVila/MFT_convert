{
    "title": "Install services in command line",
    "linkTitle": "Install services in command line",
    "weight": "140"
}After adding a Windows service in command line, the default system user is the user that started the service. To define a specific user, you must edit the service properties in the Services page.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">If you plan to integrate Transfer CFT with <span>Central Governance</span> and also plan to use Service mode, please refer to the additional instructions in <a href="post_install_transfercft">Service mode set up when using Central Governance</a>.         </td>
      </tr>
   </tbody>
</table>

Windows only

## Install services

### Transfer CFT services

1.  To install the Transfer CFT service, access the Transfer CFT directory:

    cd %TransferCFT\_directory%

2.  Enter the following:

    cscript /nologo home\\bin\\cftsrvin.vbs n=CFT36

    Where n= &lt;CFT plus the current version of Transfer CFT&gt;

### Copilot services

From the Transfer CFT home directory, run:

copsrv.exe -install &lt;service\_name> &lt;displayname> &lt;cftdirruntime>

**Example**

For Transfer CFT version 3.9 Copilot you would enter:

c:\\CFT36\\Transfer\_CFT\\home\\bin>copsrv.exe -install CFT\_Copilot36 CFT\_Copilot36 c:\\CFT36\\Transfer\_CFT\\runtime

### Activate services

Using CFTUTIL activate the services for both Transfer CFT and Copilot with the uconf service configuration parameters.

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>uconfset id=cft.nt.service_name, value=CFT36</p>
            <p>uconfset id=cft.nt.service_mode, value=yes</p>
            <p>uconfset id=copilot.nt.service_name, value=CFT_Copilot36</p>
            <p>uconfset id=copilot.nt.service_mode, value=yes</p>         </td>
      </tr>
   </tbody>
</table>

## <span id="Service"></span>
