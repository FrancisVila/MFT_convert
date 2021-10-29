{
    "title": "Troubleshooting",
    "linkTitle": "Troubleshooting",
    "weight": "210"
}## Using the support tool

To assist Axway Customer Support, the CFTSUPPORT command collects useful information from a Transfer CFT environment including the configuration, Unified Configuration parameters (UCONF), catalog information, log files, and so on. This information is then packaged and stored in a tar file in the specified IFS folder.

Collected information for the Transfer CFT Transfer CFT IBM i platform includes these different CFTPROD/SUPOUT file members:

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>File</th>
         <th>Comment</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>ABOUT         </td>
         <td>About information         </td>
      </tr>
      <tr class="even">
         <td>ALOG         </td>
         <td>Cftlog file         </td>
      </tr>
      <tr class="odd">
         <td>CFTOUTQ         </td>
         <td>List the Transfer CFT Out Queue messages         </td>
      </tr>
      <tr class="even">
         <td>CFTEXT         </td>
         <td>CFT parameter extract         </td>
      </tr>
      <tr class="odd">
         <td>CFTOUT         </td>
         <td>CFT jobs outputs         </td>
      </tr>
      <tr class="even">
         <td>COPJLOG.CSV         </td>
         <td>Primary Copilot QPJOBLOGs         </td>
      </tr>
      <tr class="odd">
         <td>COPJLOG2.CSV         </td>
         <td>Secondary Copilot QPJOBLOGs         </td>
      </tr>
      <tr class="even">
         <td>COPOUT         </td>
         <td>Copilot jobs outputs         </td>
      </tr>
      <tr class="odd">
         <td>COPTRC         </td>
         <td>Copilot traces         </td>
      </tr>
      <tr class="even">
         <td>JLOG.CSV         </td>
         <td>Primary CFT QPJOBLOGs         </td>
      </tr>
      <tr class="odd">
         <td>JLOG2.CSV         </td>
         <td>Secondary CFT QPJOBLOGs         </td>
      </tr>
      <tr class="even">
         <td>LISTCAT         </td>
         <td>Brief listcat         </td>
      </tr>
      <tr class="odd">
         <td>LISTCATD         </td>
         <td>Debug listcat         </td>
      </tr>
      <tr class="even">
         <td>LISTCATF         </td>
         <td>Full listcat         </td>
      </tr>
      <tr class="odd">
         <td>LISTCOM         </td>
         <td>listcom         </td>
      </tr>
      <tr class="even">
         <td>LISTNODE         </td>
         <td>Listnode         </td>
      </tr>
      <tr class="odd">
         <td>LISTPKI         </td>
         <td>Listpki output         </td>
      </tr>
      <tr class="even">
         <td>LISTPKID         </td>
         <td>Listpki debug output         </td>
      </tr>
      <tr class="odd">
         <td>LISTPKIF         </td>
         <td>Listpki full output         </td>
      </tr>
      <tr class="even">
         <td>LISTUCONF         </td>
         <td>Listuconf output         </td>
      </tr>
      <tr class="odd">
         <td>LOG         </td>
         <td>Cftlog file         </td>
      </tr>
      <tr class="even">
         <td>SAVFOUTQ.bin         </td>
         <td>Back up the Transfer CFT Out Queue (in *SAVF format)         </td>
      </tr>
      <tr class="odd">
         <td>WRKACTJOB         </td>
         <td>List system activity         </td>
      </tr>
   </tbody>
</table>

## Using the CFTSUPPORT command

The CFTSUPPORT command executes the CFTSUPPORT program, which retrieves information about the Transfer CFT and stores it in a tar file.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">CFTSUPPORT is currently not supported with an independent ASP (IASP).         </td>
      </tr>
   </tbody>
</table>

You can use Transfer CFT IBM i command line to execute the command:

1.  Enter the CFTSUPPORT command and press PF4.
2.  Enter the IFS path where the CFTSUPPORT.tar file should be created. If the IFS path does not exist it will be created.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Alternatively, from the CFT menu select <strong>3. Administration commands</strong> then <strong>2. Submit CFT support request</strong>.         </td>
      </tr>
   </tbody>
</table>

If the generated CFTSUPPORT.tar is too large, you can compress it prior to sending it to Axway support.

**Example**

In the following example, the command creates the CFTSUPPORT.tar and SAVFOUTQ.bin files in /home/cft/cftsupport/.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTSUPPORT IFSPATH('/home/cft/cftsupport')         </td>
      </tr>
   </tbody>
</table>
