{
    "title": "User rights and privileges use cases",
    "linkTitle": "User rights and privileges use cases",
    "weight": "250"
}This topic describes how you can add mounting levels of security to your Transfer CFT environment, and features 4 typical user types. In all but the first example, no added security, the user types are defined by Central Governance roles. By adding file and user controls you can add increasing security controls.

For more information on roles and privileges in Central Governance, refer to the *Central Governance User Guide*.

In this section:

-   User scenario with no security applied
-   [User types](#User): Describes the actions that example users can perform
-   [Use case 1](#Security): Security controlled by Central Governance roles
-   [Use case 2](#Security2): Security controlled by USERCTRL and file rights
-   [Use case 3](#Security3): Security controlled by copilot.misc.createprocessasuser
-   [Define additional user rights security option](#Define)

<span id="Use"></span>

## Use case with no security applied

In this use case, there is no security enabled either in Transfer CFT or Central Governance (<span class="code">am.type=none</span>). However, normally when using Central Governance with Transfer CFT the default value is set to <span class="code">am.type=passport</span>. This results in no control over the transfer owner.

<span id="User"></span>

## User types

This section presents example user types, and describes the actions that they can perform given the Central Governance roles and systems rights. Machine1 represents a system with an installed Transfer CFT and user directories.

These scenarios are based on a single <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span>, **Machine1** in our examples, that is managed by <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>.

<table>
   <th>
      <tr>
<th>User type         </th>
<th>CG role(s)         </th>
<th>Machine1 user         </th>
<th>File access         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Monitoring Assistant</p>         </td>
         <td><p>Help Desk</p>
<p>for Transfer CFT</p>         </td>
         <td>Not defined         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>Operator         </td>
         <td>IT Manager for CG         </td>
         <td>Defined         </td>
         <td><p>All permissions on runtime files, but does not have access to other user's working directories</p>         </td>
      </tr>
      <tr>
         <td>Partner Manager         </td>
         <td>CG Admin         </td>
         <td>Not defined         </td>
         <td>No privileges on the physical files         </td>
      </tr>
      <tr>
         <td>Flow Manager         </td>
         <td><p>Middleware</p>
<p>Manager for CG, and Application for Transfer CFT</p>         </td>
         <td>Defined         </td>
         <td>Rights on Machine1, and his own working directory         </td>
      </tr>
      <tr>
         <td>Superuser         </td>
         <td>N/A         </td>
         <td>Defined         </td>
         <td>Rights on all runtime files on Machine1, but no rights on user's working directories         </td>
      </tr>
   </tbody>
</table>

Remember that these are examples and your system users, assigned roles, and file rights will vary.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>When referring to user's working directories, in these use cases the working directories are located outside of the runtime directory.         </td>
      </tr>
   </tbody>
</table>

<span id="Security"></span>

## Security controlled by Central Governance roles

In this security scenario, the central governance roles are the exclusive defining security system (i.e. the parameters USERCTRL and copilot.misc are set to NO, the default settings).

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Tip  </strong></span>         </td>
         <td>The transfer owner in this scenario is the user that started <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>. All actions are done by the user that started the <span class="mc-variable suite_variables.CopilotName variable">Copilot</span> server, pending rights given by the Central Governance roles. This applies to all of the registered <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> users. The superuser however can perform actions only by using CFTUTIL, but not via the Transfer CFT UI.         </td>
      </tr>
   </tbody>
</table>

#### Monitoring Assistant

The help desk cannot monitor Transfer CFT through Central Governance if they have no other role assigned to them.

-   Perform monitoring: YES, but only via a Transfer CFT client (not using Central Governance visibility services)
-   Submit a transfer: NO
-   Connect to Transfer CFT UI: YES
-   Modify configuration: NO 
-   Start/stop Transfer CFT: NO

#### Operator

-   Monitor: YES, but only using Central Governance
-   Transfer: NO
-   Connect to Transfer CFT UI: NO
-   Modify configuration: YES, but only through Central Governance
-   Start/stop Transfer CFT: YES

#### Partner Manager

-   Monitor: YES, but only through Central Governance
-   Transfer: NO
-   Connect to Transfer CFT UI: NO
-   Modify configuration: NO
-   Start/stop Transfer CFT: NO

#### Flow Manager

-   Monitor: YES, but only by using Central Governance
-   Transfer: YES, can access and perform transfers using any user's working directory
-   Connect to Transfer CFT UI: YES
-   Modify configuration: YES, via Central Governance only
-   Start/stop Transfer CFT: NO

#### System Engineer (superuser)

Using CFTUTIL this user can perform configuration actions and transfers, but cannot do anything from <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>.

-   Monitor: YES
-   Transfer: YES
-   Connect to Transfer CFT UI: NO
-   Modify configuration: YES
-   Start/stop Transfer CFT: YES, but only via CFTUTIL

<span id="Security2"></span>

## Security controlled by USERCTRL and file rights

The following scenario consists of a single <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span> with the USERCTRL parameter set to **yes**.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Reminder, when copilot.misc.createprocessasuser=no, the user may be known by <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, though not necessarily known by Machine1. All actions in Transfer CFT client are done as if the user was the user who started server.         </td>
      </tr>
   </tbody>
</table>

USERCTRL is set to YES and file rights are assigned to each specific type of user. Rights depend on user/role type (limitation).

#### Monitoring Assistant

Help desk alone cannot monitor Transfer CFT through Central Governance if they have no other role assigned to them.

-   Perform monitoring: YES, but only via a Transfer CFT client (not using CG visibility services)
-   Submit a transfer: NO
-   Connect to Transfer CFT UI: YES
-   Modify configuration: NO 
-   Start/stop Transfer CFT: NO

#### Operator

-   Monitor: YES, but only through Central Governance
-   Transfer: NO
-   Connect to Transfer CFT UI: NO
-   Modify configuration: YES, but only through CG.
-   Start/stop Transfer CFT: YES

#### Partner Manager

-   Monitor: YES, but only via Central Governance
-   Transfer: NO
-   Connect to Transfer CFT UI: NO
-   Modify configuration: NO
-   Start/stop Transfer CFT: NO

#### Flow Manager

-   Monitor: YES, via Central Governance only
-   Transfer: YES, but is limited to his own working directory
-   Connect to Transfer CFT UI: YES
-   Modify configuration: YES, via Central Governance only
-   Start/stop Transfer CFT: NO

#### System Engineer (superuser)

Using CFTUTIL this user can perform configuration actions and transfers, but cannot do anything from <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>.

-   Monitor: YES, but only using CFTUTIL
-   Transfer: NO, because he cannot access (no rights on) the user's working directories
-   Connect to Transfer CFT UI: NO
-   Modify configuration: YES
-   Start/stop Transfer CFT: YES, but only via CFTUTIL

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>When copilot.misc.createprocessasuser=no, the user may be known on <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, but not necessarily known on Machine1. All actions in Transfer CFT client are done as if the user was the user who started server.         </td>
      </tr>
   </tbody>
</table>

<span id="Security3"></span>

## Security controlled by copilot.misc.createprocessasuser

On top of the previous security steps, additionally you have set copilot.misc.createprocessasuser to YES.

-   The log in connection is a system check and not a CG check
-   All actions on files that Copilot can access are performed on behalf of the user connected to Copilot

#### Monitoring Assistant

Help desk alone cannot monitor Transfer CFT through Central Governance if they have no other role assigned to them.

-   Perform monitoring: NO, this user is not defined on Machine1
-   Submit a transfer: NO
-   Connect to Transfer CFT UI: NO
-   Modify configuration: NO 
-   Start/stop Transfer CFT: NO

#### Operator

-   Monitor: YES, through either Central Governance or Copilot
-   Transfer: NO
-   Connect to Transfer CFT UI: <span style="color: #000000;">NO</span>
-   Modify configuration: YES
-   Start/stop Transfer CFT: YES

#### Partner Manager

-   Monitor: YES, but only through CG.
-   Transfer: NO
-   Connect to Transfer CFT UI: NO
-   Modify configuration: NO
-   Start/stop Transfer CFT: NO

#### Flow Manager

-   Monitor: YES, via CG only.
-   Transfer: YES, but is limited to his own working directory.
-   Connect to Transfer CFT UI: YES
-   Modify configuration: YES, via CG only.
-   Start/stop Transfer CFT: NO

#### System Engineer (superuser)

Using CFTUTIL this user can perform configuration actions and transfers, but cannot do anything from <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>.

-   Monitor: YES, but only using CFTUTIL 
-   Transfer: NO, because he cannot access (no rights on) the user's working directories
-   Connect to Transfer CFT UI: NO
-   Modify configuration: YES, using either CFTUTIL or Copilot
-   Start/stop Transfer CFT: YES

<span id="Define"></span>

## Define additional user rights security option

This example describes how to add an additional user rights security restriction. The user in this case is not known on Central Governance, but has all rights on all files on the Transfer CFT system, runtime as well as working directories.

-   When am.passport.userctrl.check\_permissions\_on\_transfer\_execution=no, the default value, this user, who defined on the Machine1, can use CFTUTIL to perform a transfer even though not known on <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>.
-   When am.passport.userctrl.check\_permissions\_on\_transfer\_execution=yes, this same user cannot perform transfers as he is not defined in <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>.

Related topics

-   [About system users](../)
-   [Recommendations and troubleshooting](../user_rights_tips)