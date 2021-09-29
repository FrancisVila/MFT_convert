{
    "title": "Password authentication",
    "linkTitle": "Password authentication",
    "weight": "300"
}# Password authentication



## About password authentication for synchronous communication media



Password authentication lets you control remote users that perform CFTUTIL commands via a synchronous communication media.



## Enabling <span id="kanchor26"></span>password authentication on a Transfer CFT server



To enable password authentication set the authentication feature to yes, and specify the authentication method using these unified configuration parameters:



-   cft.server.cftcoms.authentication\_enable

-   cft.server.authentication\_method



Available authentication methods are:



-   Operating System: value=system

    -   The user/password is checked against the Operating System values. For Unix environments, you must enable <span>cftsu </span>as described in <a href="../../../cft_intro_install/unix_install_start_here/run_first_time_ux/run_first_time_ux/t_adding_system_user_unix">How to use system user authentication for the user interfaces</a>

-   Access Management: value=am

    -   The user/password is checked by the configured access management system (either PassPort AM, or the AM exit)

-   Transfer CFT UI User Access Base (UNIX and HP NonStop only): value=xfbadm

    -   The user/password is checked using the xfbadm base

    -   Refer to [xfbadmusr and xfbadmgrp utilities](../../UNIX/UNIX_operations/Utilities/use_cft_utilities.htm) for more information



See Related topics below for links to more information on these access management types.



## Configuring the communication media



1.  Define the unified configuration settings so that you enable authentication yes, and select the method.



<table data-cellspacing="0">
<thead>
<tr>
<th>Parameters</th>
<th>Default</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>cft.server.cftcoms.authentication_enable</td>
<td>No</td>
<td><p>Authentication for synchronous communication:</p>
<ul>
<li>Yes: Enable password authentication</li>
<li>No: Disable authentication</li>
</ul></td>
</tr>
<tr>
<td>cft.server.authentication_method</td>
<td>None</td>
<td><p>Authentication method can be:</p>
<ul>
<li>none: No method defined</li>
<li>system: Operating system</li>
<li>am: PassPort AM or AM exit</li>
<li>xfbadm: <a href="../../../cft_intro_install/unix_install_start_here/run_first_time_ux/use_cft_utilities">xfbadmusr</a> utility</li>
</ul></td>
</tr>
</tbody>
</table>



1.  Define the following parameters.



<table data-cellspacing="0">
<tbody>
<tr>
<td>CONFIG TYPE=COM, MEDIACOM=TCPIP, FNAME=protocol://host:port, PASSWORD=password</td>
</tr>
</tbody>
</table>



The username/password is then checked for each subsequent request. The username used for the authentication is the user that is currently logged in. api sample



Related topics



-   [Command summary](../../Command_summary.htm)

-   [PassPort AM](../../internal_access_mgt/About_PassPort_am.htm)

-   [Access Management exits](../../internal_access_mgt/am_exits.htm)

-   [CONFIG - Setting default CFTUTIL file names](../Redefining_CFTUTIL_data_media.htm)

