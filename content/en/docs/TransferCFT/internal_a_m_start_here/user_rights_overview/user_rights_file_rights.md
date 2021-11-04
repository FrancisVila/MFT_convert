{
    "title": "4. File actions and procedure execution permissions ",
    "linkTitle": "4. File actions and procedure execution permissions",
    "weight": "240"
}This section explains the user rights required for system users to [execute files actions,](#Set) which allows a system user to perform all file actions, for example accessing or opening a file. By default, on the sender side the user who initiates the SEND is used, and on the receiver side the USERID specified in the CFTRECV object is used. Additionally this topic describes user rights required to [execute post-transfer procedures.](#Set2)

Before setting user rights, you must define special rights for the account on which <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is running.

<span id="Set"></span>

## Set permissions for users to act on files

The following conventions apply to the table below describing permissions to act on files:

-   Transfer CFT user: This is the account that started Transfer CFT.
-   USERID, and optionally GROUPID : This is the account that owns the transfer.
    -   Requester mode (SEND, RECV commands) is the account that executes the command.
    -   Server mode (Send and Receive templates) represents the value specified in USERID parameter.

    <table>
       <tbody>
          <tr>
             <td>         </td>
             <td><span><strong>Note</strong></span>         </td>
             <td>When referring to USERID, the same rules apply when using the optional GROUPID parameter.         </td>
          </tr>
       </tbody>
    </table>

<table>
   <th>
      <tr>
<th><p>Operating</p>
<p>System</p>         </th>
<th><p>USERCTRL</p>         </th>
<th><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>ALL OS         </td>
         <td>NO         </td>
         <td>The Transfer CFT user, that is, the account that started <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>, performs all file actions. Default value.         </td>
      </tr>
      <tr>
         <td>YES         </td>
         <td>The USERID performs all file actions.         </td>
      </tr>
   </tbody>
</table>

1.  Set the CFTPARM USERCTRL option to YES (enabled).
2.  Set the USERID for CFTRECV, for example domain\\user on Windows.
3.  Check that the user referred to by the USERID can access the destination directory.

### Operating system specific USERCTRL tasks

When you set USERCTRL to YES, the Transfer CFT server can access transferred files as if it were the transfer owner (USERID).

**If you set USERCTRL to YES, you must customize per the appropriate operating system instructions.**

Use the following OS-specific information to customize users.

-   [UNIX tasks](https://docs.axway.com/bundle/TransferCFT_38_InstallationGuide_unix_en_PDF/resource/TransferCFT_InstallationGuide_unix_en.pdf) - Regardless of the USERCTRL setting, if cft.server.exec\_as\_user is set to YES you must perform the tasks described in the UNIX *Using system users (USERCTRL)* section.
-   [Windows tasks](https://docs.axway.com/bundle/TransferCFT_38_InstallationGuide_windows_en_PDF/resource/TransferCFT_InstallationGuide_windows_en.pdf)
-   [z/OS tasks](https://docs.axway.com/bundle/TransferCFT_38_InstallationGuide_mvs_en_PDF/resource/TransferCFT_InstallationGuide_mvs_en.pdf) - APF allows an installation to identify system or user programs that can use sensitive system functions. If the system does not have APF (Authorized Program Facility), the USERCTRL has no effect on the file actions. All file actions are done by the account that started Transfer CFT. To enable user control for file actions you require APF.

<!-- -->

-   IBM i - There are no specific tasks to enable system users on an IBM i platform.

<span id="Set2"></span>

## Set permissions for users to execute post-transfer procedures

This feature allows system users to execute end-of-transfer procedures themselves. On the sender side, the system user who initiates the SEND is used to execute the end-of-transfer procedure by default. On receiver side, the USERID is specified in the corresponding CFTRECV object.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>When referring to USERID, the same rules apply when using the optional GROUPID parameter.         </td>
      </tr>
   </tbody>
</table>

To enable this feature:

1.  Set <span class="code">cft.server.exec\_as\_user</span> to <span class="code">Yes</span>. Scripts are then executed as if by the defined in [USERID](../../../c_intro_userinterfaces/command_summary/parameter_intro/userid).
2.  Define the CFTRECV <span class="bold_in_para">USERID </span>option.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Additionally, you can use substitution variables to set the USERID for CFTSEND and CFTRECV objects (&amp;RUSER, &amp;SUSER, &amp;RAPPL,&amp;SAPPL, and so on).         </td>
      </tr>
   </tbody>
</table>

Related topics

-   [About system users](../)
-   [User rights use case scenarios](../user_rights_security_scenarios)
-   [Recommendations and troubleshooting](../user_rights_tips)
