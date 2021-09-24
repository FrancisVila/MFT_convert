{
    "title": "How to free disk space from updates",
    "linkTitle": "How to free disk space from updates",
    "weight": "230"
}This topic describes how to reclaim disk space that is taken up by Service Packs and updates applied to Transfer CFT over time.  

## Use the purge command

Use the purge command followed by the appropriate options to removed accumulated backups of installed Transfer CFT updates.  

1.  Navigate to the Transfer CFT installation directory.  
2.  Run the purge command as described in the following sections.

Syntax

purge \[-h | --help\] | \[-k | --keep\] \[number\] \[-p | --pretend\]  

-   UNIX: purge.sh
-   Windows: purge64.exe or purge32.exe (from a command line window)  

Where:  

-   \[-h | --help\]: Displays the command help.  
-   \[-k | --keep\] \[number\]: Specifies the number of updates that should be kept.
-   \[-p | --pretend\]: Previews the action to be done.  

Examples  

Keep only the last backup, meaning you can remove the current patch or SP.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>&lt;Transfer_CFT_install_dir&gt;/purge.sh -k 1  </p>
         </td>
      </tr>
   </tbody>
</table>

Remove all backups, meaning that you cannot remove the current patch or SP.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>&lt;Transfer_CFT_install_dir&gt;/purge.sh -k 0 </p>
         </td>
      </tr>
   </tbody>
</table>

&lt;Options> include:

-   \[-d | --debug\]: Generates debug information in the log file.

Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>&lt;Transfer_CFT_install_dir&gt;/purge.sh -k 1 -d<br/></p>
         </td>
      </tr>
   </tbody>
</table>
