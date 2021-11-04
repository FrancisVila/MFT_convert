{
    "title": "Troubleshooting",
    "linkTitle": "Troubleshooting",
    "weight": "210"
}## Using the support tool

To assist Axway Customer Support, the CFTSUPPORT command collects useful information from a Transfer CFT environment including the configuration, Unified Configuration parameters (UCONF), catalog information, log files, and so on. This information is then packaged and stored in a tar file in the specified IFS folder.

Collected information for the Transfer CFT <span class="mc-variable Primary.For_OS400 variable">Transfer CFT IBM i</span> platform includes these different CFTPROD/SUPOUT file members:

<table>
   <th>
      <tr>
<th>File         </th>
<th>Comment         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>ABOUT         </td>
         <td>About information         </td>
      </tr>
      <tr>
         <td>ALOG         </td>
         <td>Cftlog file         </td>
      </tr>
      <tr>
         <td>CFTOUTQ         </td>
         <td>List the Transfer CFT Out Queue messages         </td>
      </tr>
      <tr>
         <td>CFTEXT         </td>
         <td>CFT parameter extract         </td>
      </tr>
      <tr>
         <td>CFTOUT         </td>
         <td>CFT jobs outputs         </td>
      </tr>
      <tr>
         <td>COPJLOG.CSV         </td>
         <td>Primary Copilot QPJOBLOGs         </td>
      </tr>
      <tr>
         <td>COPJLOG2.CSV         </td>
         <td>Secondary Copilot QPJOBLOGs         </td>
      </tr>
      <tr>
         <td>COPOUT         </td>
         <td>Copilot jobs outputs         </td>
      </tr>
      <tr>
         <td>COPTRC         </td>
         <td>Copilot traces         </td>
      </tr>
      <tr>
         <td>JLOG.CSV         </td>
         <td>Primary CFT QPJOBLOGs         </td>
      </tr>
      <tr>
         <td>JLOG2.CSV         </td>
         <td>Secondary CFT QPJOBLOGs         </td>
      </tr>
      <tr>
         <td>LISTCAT         </td>
         <td>Brief listcat         </td>
      </tr>
      <tr>
         <td>LISTCATD         </td>
         <td>Debug listcat         </td>
      </tr>
      <tr>
         <td>LISTCATF         </td>
         <td>Full listcat         </td>
      </tr>
      <tr>
         <td>LISTCOM         </td>
         <td>listcom         </td>
      </tr>
      <tr>
         <td>LISTNODE         </td>
         <td>Listnode         </td>
      </tr>
      <tr>
         <td>LISTPKI         </td>
         <td>Listpki output         </td>
      </tr>
      <tr>
         <td>LISTPKID         </td>
         <td>Listpki debug output         </td>
      </tr>
      <tr>
         <td>LISTPKIF         </td>
         <td>Listpki full output         </td>
      </tr>
      <tr>
         <td>LISTUCONF         </td>
         <td>Listuconf output         </td>
      </tr>
      <tr>
         <td>LOG         </td>
         <td>Cftlog file         </td>
      </tr>
      <tr>
         <td>SAVFOUTQ.bin         </td>
         <td>Back up the Transfer CFT Out Queue (in *SAVF format)         </td>
      </tr>
      <tr>
         <td>WRKACTJOB         </td>
         <td>List system activity         </td>
      </tr>
   </tbody>
</table>

## Using the CFTSUPPORT command

The CFTSUPPORT command executes the CFTSUPPORT program, which retrieves information about the Transfer CFT and stores it in a tar file.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>CFTSUPPORT is currently not supported with an independent ASP (IASP).         </td>
      </tr>
   </tbody>
</table>

You can use Transfer CFT IBM i command line to execute the command:

1.  Enter the CFTSUPPORT command and press PF4.
2.  Enter the IFS path where the CFTSUPPORT.tar file should be created. If the IFS path does not exist it will be created.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Alternatively, from the CFT menu select <strong>3. Administration commands</strong> then <strong>2. Submit CFT support request</strong>.         </td>
      </tr>
   </tbody>
</table>

If the generated CFTSUPPORT.tar is too large, you can compress it prior to sending it to Axway support.

**Example**

In the following example, the command creates the CFTSUPPORT.tar and SAVFOUTQ.bin files in <span class="code">/home/cft/cftsupport/</span>.


    CFTSUPPORT IFSPATH('/home/cft/cftsupport')
