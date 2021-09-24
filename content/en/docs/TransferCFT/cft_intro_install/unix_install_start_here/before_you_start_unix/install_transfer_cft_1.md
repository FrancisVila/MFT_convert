{
    "title": "4. Perform a standard installation",
    "linkTitle": "4. Perform a standard installation",
    "weight": "160"
}## <span id="Make"></span>Make the file executable

Before executing the scripts in this section, run the change mode command:

chmod +x Transfer\_CFT\_3.9\_Install\_&lt;OS>\_&lt;BN>.run

## Install

Use the following command to begin the Transfer CFT installation in graphical mode:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><span>./Transfer_CFT_3.7_&lt;Install&gt;_&lt;OS&gt;_&lt;BN&gt;.run</span>
         </td>
      </tr>
   </tbody>
</table>

The installation wizard displays. After completing each screen, click **Next** to continue. Click **Cancel** at any time to end the installation setup.

Use the following command to install Transfer CFT in text mode. The screen text is similar to the graphical mode prompts below.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><span>./Transfer_CFT_3.7_&lt;Install&gt;_&lt;OS&gt;_&lt;BN&gt;.run --mode text</span>
         </td>
      </tr>
   </tbody>
</table>

Use the following command to install Transfer CFT in silent mode.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><span>./Transfer_CFT_3.7_&lt;Install&gt;_&lt;OS&gt;_&lt;BN&gt;.run --mode unattended --conf-file initialize.properties</span>
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
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You cannot install <span>Transfer CFT</span> if you have a profile already loaded.         </td>
      </tr>
</table>

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Screen</th>
         <th>Description</th>
      </tr>
   </thead>
      <tr>
         <td>Welcome         </td>
         <td>Welcome to Transfer CFT landing page.         </td>
      </tr>
      <tr>
         <td>License agreement         </td>
         <td>Select the check-box "<span>I accept...</span>" to continue with the installation.          </td>
      </tr>
      <tr>
         <td>Installation architecture         </td>
         <td rowspan="2">
            <p>Select to install on a single machine, a Cluster - first host, or cluster - additional host. </p>
            <ul>
               <li>Single - Installs a single instance of Transfer CFT on a machine.               </li>
               <li>Cluster - Installs Transfer CFT on several machines. Select this option if you want to install Transfer CFT in multi-host/multi-node or in active/passive mode.               </li>
            </ul>
            <ul>
            <ul>
               <li>Cluster - First host: Install on a first machine before adding additional machines (nodes). You must install on a first node before you can select the option to install on additional nodes.               </li>
               <li>Cluster - Additional host: After installing on the first machine, you can select this option to install on an additional machine(s).               </li>
            </ul>
            </ul>
            <ul>
               <li>If you are performing a cluster installation and you enable the multi-node option in the configuration file, this creates an active/active Transfer CFT installation. Otherwise, the installation is active/passive.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>          </td>
      </tr>
      <tr>
         <td>Installation Directory         </td>
         <td>Specify the directory where you want to install Transfer 
CFT. This is the directory where the Transfer CFT product files  are installed.             <p><table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Directory paths cannot contain spaces.         </td>      </tr></table></p>         </td>
      </tr>
      <tr>
         <td>Configuration filename         </td>
         <td>
            <p>Enter the path, or navigate, to the configuration file (initialize.properties file) containing details for the Transfer CFT installation. This file defines settings such as hostname, license key, governance options, and so on. </p>
            <p>If you do not specify a file, you can continue with the installation, but the installation procedure does not create the runtime directory. (Run the <span>initialize </span>command post installation if you opt to create the runtime directory at a later date.)</p>
         </td>
      </tr>
      <tr>
         <td>Generate Encryption Key          </td>
         <td>
            <p>Enter your password and reenter it to confirm. </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Ready to install</p>
         </td>
         <td>
            <p>Click <span>Next</span>to complete the installation process, or <span>Back</span>to review or modify installation options. </p>
         </td>
      </tr>
</table>

 
