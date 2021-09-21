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

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The user performing the uninstall must have delete rights for the CFTPGM and CFTPROD libraries, and the files in IFS  <span>/home/user/cft3x</span>.         </td>
      </tr>
</table>
