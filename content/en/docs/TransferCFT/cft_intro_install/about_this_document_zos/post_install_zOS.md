{
    "title": "Verify your installation",
    "linkTitle": "Verify your installation",
    "weight": "150"
}See the installation if you encounter problems when starting Transfer CFT.

## Installed directories

Once you install the product, the following subdirectories are available:

-   Bin: Contains the installation procedures. This directory is unique to Axway. This directory also contains trace files after installation.
-   Install: Contains the Transfer CFT product and the configuration file for silent installation.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>File Name</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>silent_install.conf         </td>
         <td>File to customize for silent installation.         </td>
      </tr>
      <tr class="even">
         <td>Transfer_CFT_mvs_adrdssu.bin         </td>
         <td>Compressed Transfer CFT files in ADRDSSU format.
            <p>Name: distlib.UPLIB(CFT332A)</p>         </td>
      </tr>
      <tr class="odd">
         <td>Transfer_CFT_mvs_xmit.bin         </td>
         <td>            <p>Transfer CFT files in double XMIT format.</p>
            <p>Name: distlib.UPLIB(CFT332X)</p>         </td>
      </tr>
      <tr class="even">
         <td>Transfer_CFT_mvs_adrdssu_J1IDIST.txt         </td>
         <td>            <p>JCL that executes the extraction (next step).</p>
            <p>Name: distlib.UPLIB(J1IDISTA)</p>         </td>
      </tr>
      <tr class="odd">
         <td>Transfer_CFT_mvs_xmit_J1IDIST.txt         </td>
         <td>            <p>JCL that executes the extraction (next step).</p>
            <p>Name: distlib.UPLIB(J1IDISTX)</p>         </td>
      </tr>
      <tr class="even">
         <td>Transfer_CFT_mvs_J2IICFT.txt         </td>
         <td>            <p>JCL that installs Transfer CFT instance environment.</p>
            <p>Name: distlib.UPLIB(J2IICFT)mode</p>         </td>
      </tr>
   </tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The act of installing Transfer CFT creates a distribution environment that contains product binaries and templates. Do no store any personal files in this environment, or modify existing files in this environment, as they are erased during updates.         </td>
      </tr>
   </tbody>
</table>

-   EULA.html: License agreement (html format)
-   EULA.txt: License agreement (text format)
-   setup.sh: Installation script for UNIX/Linux
-   setup.bat: Installation script for Windows
