{
    "title": "Uninstall Transfer CFT",
    "linkTitle": "Uninstall Transfer CFT",
    "weight": "200"
}To uninstall Transfer CFT in an IBM i environment, delete the following libraries:

-   CFTPROD
-   CFTPGM

In the HFS partition remove:

-   /home/cft/cft332/install
-   /home/cft/cft332/runtime

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The user performing the uninstall must have delete rights for the CFTPGM and CFTPROD libraries, and the files in IFS <span>/home/user/cft3x</span>.         </td>
      </tr>
   </tbody>
</table>
