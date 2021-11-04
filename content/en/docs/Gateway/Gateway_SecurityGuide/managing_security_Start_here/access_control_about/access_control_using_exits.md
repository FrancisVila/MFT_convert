{
    "title": "Access control using exits",
    "linkTitle": "Access Control using exits",
    "weight": "160"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

[Access control mechanisms](#mechanisms)

[Customizing user Access control](#customizing)

[Troubleshooting user access problems](#troubleshooting)

<span id="mechanisms"></span>

## Access control mechanisms

This section provides basic descriptions of access control mechanisms within Gateway:

-   [Login validation](#login_validation)
-   [Object access validation](#object_access_validation)
-   [File access validation](#file_access_validation)
-   [Logout validation](#logout_validation)

<span id="login_validation"></span>

### Login validation

Any access to Gateway, whether an interactive operator session or a batch command session, is preceded by a login request where users supply their login names and passwords.

The user login process involves the following steps.

1.  Gateway calls the exit routine ExitLoginParam() to ask for login username and password.
2.  From the Gateway Navigator, the user enters the user name and password.
3.  When Gateway receives the login request, it calls the exit ExitCheckUserLogin() to validate the request. The exit routine returns one of three values: <span style="font-style: italic;">Allowed</span>, <span style="font-style: italic;">Denied</span> or <span style="font-style: italic;">Undefined</span>. If the exit routine returns <span style="font-style: italic;">Undefined</span>, Gateway continues the validation with its own user database definition. The request is accepted if, and only if, all of the following conditions are met:
    -   The user name is defined
    -   The password is not empty and matches the one defined in the User record (the process of matching user name and password is not case-sensitive)
    -   The user is <span style="font-style: italic;">not</span> disabled and the expiration date is <span style="font-style: italic;">not</span> reached

If validation fails, Gateway rejects the user access request. If the user login request is rejected and the maximum consecutive retry count is reached, Gateway disables the user account. An administrator must then re-enable the account.

If the password is an empty string, a new password is required. You must enter a new password at login before you can proceed.

<span id="object_access_validation"></span>

### Object access validation

The following Gateway objects (or files) are protected objects:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><ul>
<li>Site</li>
<li>Application</li>
<li>Transfer Request</li>
<li>Model</li>
<li>Diffusion List</li>
<li>User</li>
<li>Profile</li>
<li>Log file</li>
<li>CGate and CGateGroup</li>
</ul>         </td>
         <td><ul>
<li>VFD</li>
<li>Rule Table</li>
<li>Decision Rule</li>
<li>Proxy</li>
<li>Trading Partner</li>
<li>Transfer security</li>
<li>Configuration</li>
<li>Audit</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

A protected object is protected from user access for any of the following actions:

-   Read
-   Write
-   Update
-   Delete
-   Admin

When a user attempts to access a protected object for any of the above actions, Gateway calls the exit routine ExitCheckUserAccessByObject() to validate the request. The exit routine returns one of three values: <span style="font-style: italic;">Allowed</span>, <span style="font-style: italic;">Denied</span> or <span style="font-style: italic;">Undefined</span>. If the exit routine returns <span style="font-style: italic;">Undefined</span>, (default action in the supplied sample codes), Gateway continues the validation with its own user database definition.

Gateway accepts the request if, and only if, at least one of the following conditions is met:

-   The user is an administrator
-   The associated Profile definition grants to the user the required access to the object in question

<span id="file_access_validation"></span>

### File access validation

When a user requests a file transfer, Gateway calls the exit routine ExitCheckFileAccess() to validate access to the required file. If the exit routine denies access, the Transfer Request is rejected. Otherwise, it is accepted. By default, in the supplied sample code, access is always accepted.

<span id="logout_validation"></span>

### Logout validation

When a user ends a login session, Gateway calls the exit routine ExitCheckUserLogout(). This exit routine enables you to clean up the environment, if necessary. The return code from the exit routine is ignored.

<span id="customizing"></span>

## Customizing user Access control

This section describes the cases in which you customize the access procedure to correspond to your network requirements.

<span id="login_paras"></span>

### Login parameters

During a login request to Gateway, a user (or a user program) supplies the required login user name and password.

Gateway calls the following user exit routine to validate the user data:

int ExitLoginParam(char \*name, int nm\_size, char \*password, int pw\_size, char \*newpassword, int npw\_size)

This user exit returns the required user name, password and new password in the buffer provided.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td><strong>The</strong> <span style="color: #8b0000;font-weight: bold;">default action in the supplied sample codes are not secure enough for a production environment!</span> <strong>You must customize this routine to meet your precise functional and security needs. Please see the</strong> <em>Security Guide &gt; <a href="##identified_threats_and_possible_mitigations">Identified threats and possible mitigations</a></em> <strong>section for additional information.</strong><br />
<br />
         </td>
      </tr>
   </tbody>
</table>

The <span class="code">ExitLoginParam() </span>exit routine is called on the client (navigator) side either in the address space of the operator interface or in the user program. The other exit routines are called on the server side (in the address space of the monitor).

> **Note:**
>
> To use the online commands with user access security, by default Gateway uses the following environment variables to define the user login and user password:p\_cs\_usernamep\_cs\_dk\_filep\_cs\_encpass\_file(Storing the cleartext password in the environment variable p\_cs\_passwordis is no longer supported.)For more information regarding password encryption, read Password management.

### Transfer Request owner

Every Transfer Request is associated with a creator, also known as an owner. Two cases are possible:

-   A user creates a Transfer Request: the owner is set to the login user name.
-   Gateway creates the Transfer Request (for example, on reception of a Transfer Request from a Remote Site): the owner is set to the Transfer Request owner name defined in the Remote Site record

If no user name is defined, the owner is set to the <span style="font-weight: bold;">Default user name</span> that you specify during configuration.

### Setting up Access control

User Access control is only effective if users access Gateway via the GUI or via a command line. The confidentiality and integrity of your installation data, as well as Gateway itself, must still be protected by normal system security. Make sure that this data is protected against unauthorized direct access.

To set up User Access control:

1.  In the configuration menu, enable the <span style="font-weight: bold;">User access control</span> option and set the <span style="font-weight: bold;">Default user name</span> to an appropriate value.  
    Refer to [Configuration: Gateway parameters: Gateway > Connection control](../../../../gateway_userguide_(primary)/configuration_start_here/config_gateway_paras#olh_gateway_connection_control).  
    If you do not enable this option, access control and exit routines are not activated.
2.  The first time you start Gateway, and before you define any users, the installation program creates a default user named ADMIN, with the password ADMIN. By default, this user is the product administrator. The ExitLoginParam() in the supplied sample codes uses this entry by default.
3.  Using either the GUI or the <span class="code" style="font-weight: bold;">peladm</span> command, set up your user and access rights profile database. It is recommended that you create an additional administrator besides the default ADMIN. You should also change the default ADMIN password.
4.  Edit the ExitLoginParam() routine to satisfy your production environment requirements. The exact procedure used to compile and link exit routines depends on the platform.
5.  Update all other optional server-side exit routines if you are connecting Gateway to your system security package.

<span id="troubleshooting"></span>

## Troubleshooting user access problems

This section outlines the various cases where access is denied and explores possible causes for this refusal. If you experience a problem not covered in this section, contact your system administrator or technical support staff.

### Login access denied

If the login request returns an <span style="font-style: italic;">access denied</span> message, check the following:

-   Are the specified user name and password correct?
-   Were the user name and password overwritten by the ExitLoginParam() routine?
-   Is access denied by an ExitCheckUserAccess() routine?
-   Is the user not enabled?
-   Is the expiration date reached?
-   Is a new password required?

### Operation access denied

If the login request is successful but an operation is refused, check the following:

-   Is the Profile (access rights) field defined in the user record?
-   Does the specified Profile (access rights) record exist? If a specific implementation exists, check it.
-   Does the Profile record allow the required operation on the object?
-   Are you the owner of the requested objects?

### User forgets password

Ask a system administrator to assign a new password or to erase the old one (in this second case, a new password is required at the next login).

### Administrator forgets password

If you have a backup administrator account, use it to re-assign a new password. Otherwise, disable the security feature, change the password in question and then re-enable the security feature.

Related topics

[About Access Control Management](../)

[Configuration: Gateway parameters](../../../../gateway_userguide_(primary)/configuration_start_here/config_gateway_paras)

[Internal user exits](../../../../gateway_userguide_(primary)/customizing_gw_about/user_exits_about/user_exits_internal)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
