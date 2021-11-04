{
    "title": "Start the installation",
    "linkTitle": "4. Perform a standard installation",
    "weight": "160"
}<span id="Make"></span>

## Make the file executable

Before executing the scripts in this section, run the change mode command:

chmod +x Transfer\_CFT\_<span class="mc-variable axway_variables.Release_Number variable">3.9</span>\_Install\_&lt;OS>\_&lt;BN>.run

## Install

Use the following command to begin the Transfer CFT installation in graphical mode:


    ./Transfer_CFT_3.7_<Install>_<OS>_<BN>.run

The installation wizard displays. After completing each screen, click **Next** to continue. Click **Cancel** at any time to end the installation setup.

Use the following command to install Transfer CFT in text mode. The screen text is similar to the graphical mode prompts below.


    ./Transfer_CFT_3.7_<Install>_<OS>_<BN>.run --mode text

Use the following command to install Transfer CFT in silent mode.


    ./Transfer_CFT_3.7_<Install>_<OS>_<BN>.run --mode unattended --conf-file initialize.properties

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>You cannot install <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> if you have a profile already loaded.         </td>
      </tr>
   </tbody>
</table>

<table>
   <th>
      <tr>
<th>Screen         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Welcome         </td>
         <td>Welcome to Transfer CFT landing page.         </td>
      </tr>
      <tr>
         <td>License agreement         </td>
         <td>Select the check-box "<span class="code">I accept...</span>" to continue with the installation.         </td>
      </tr>
      <tr>
         <td>Installation architecture         </td>
         <td><p>Select to install on a single machine, a Cluster - first host, or cluster - additional host.</p>
<ul>
<li>Single - Installs a single instance of Transfer CFT on a machine.</li>
<li>Cluster - Installs Transfer CFT on several machines. Select this option if you want to install Transfer CFT in multi-host/multi-node or in active/passive mode.</li>
</ul>
<ul>
<li>Cluster - First host: Install on a first machine before adding additional machines (nodes). You must install on a first node before you can select the option to install on additional nodes.</li>
<li>Cluster - Additional host: After installing on the first machine, you can select this option to install on an additional machine(s).</li>
</ul>
<ul>
<li>If you are performing a cluster installation and you enable the multi-node option in the configuration file, this creates an active/active Transfer CFT installation. Otherwise, the installation is active/passive.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>          </td>
      </tr>
      <tr>
         <td>Installation Directory         </td>
         <td>Specify the directory where you want to install Transfer
CFT. This is the directory where the Transfer CFT product files are installed.
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Directory paths cannot contain spaces.         </td>
      </tr>
   </tbody>
</table>         </td>
      </tr>
      <tr>
         <td>Configuration filename         </td>
         <td><p>Enter the path, or navigate, to the configuration file (initialize.properties file) containing details for the Transfer CFT installation. This file defines settings such as hostname, license key, governance options, and so on.</p>
<p>If you do not specify a file, you can continue with the installation, but the installation procedure does not create the runtime directory. (Run the <span class="code">initialize </span>command post installation if you opt to create the runtime directory at a later date.)</p>         </td>
      </tr>
      <tr>
         <td>Generate Encryption Key         </td>
         <td><p>Enter your password and reenter it to confirm.</p>         </td>
      </tr>
      <tr>
         <td><p>Ready to install</p>         </td>
         <td><p>Click <span class="bold_in_para">Next</span>to complete the installation process, or <span class="bold_in_para">Back</span>to review or modify installation options.</p>         </td>
      </tr>
   </tbody>
</table>

 