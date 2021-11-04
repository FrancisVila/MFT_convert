{
    "title": "Uninstall Transfer CFT",
    "linkTitle": "Uninstall Transfer CFT",
    "weight": "200"
}To uninstall <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> in an IBM i environment, delete the following libraries:

-   CFTPROD
-   CFTPGM

In the HFS partition remove:

-   /home/cft/cft332/install
-   /home/cft/cft332/runtime

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>The user performing the uninstall must have delete rights for the CFTPGM and CFTPROD libraries, and the files in IFS <span class="code">/home/user/cft3x</span>.         </td>
      </tr>
   </tbody>
</table>
