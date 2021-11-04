{
    "title": "_HOME_",
    "linkTitle": "_HOME_",
    "weight": "1450"
}### &HOME

A keyword to use with the [WORKINGDIR](../workingdir) parameter.

You can use the &HOME keyword in CFTSEND and CFTRECV command file names, script names, and directory parameters. This keyword functions differently depending on the system user setting:

-   When system users are enabled, &HOME represents the home folder ($HOME on UNIX or %USERPROFILE% on Windows) of the user that requested the transfer.
-   When system users are disabled, &HOME represents the home folder of the user that started Transfer CFT.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>For more information on system users, refer to the platform specific guide, <a href="#"><u>UNIX</u>:Using system users</a> or <a href="#"><u>Windows</u>: Using system users</a>.         </td>
      </tr>
   </tbody>
</table>
