{
    "title": "Pluggable authentication",
    "linkTitle": "Pluggable authentication",
    "weight": "240"
}A custom authentication plug-in allows you to implement your own authentication logic and override the SecureTransport authentication mechanism. The custom authentication has priority over the rest authentication types except for the Single sign-on (SSO). Only one authentication plug-in can be enabled at a time.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">A collection of  authentication plug-ins is available in the <a href="https://repository.axway.com/">AMPLIFY Repository</a>.         </td>
      </tr>
</table>

Pluggable Authentication features:

-   End-user authentication over the HTTP, FTP, and SSH.
-   Administrator authentication over HTTP only.
-   Supports multiple authentication methods for administrators and end-users: basic authentication (user name/password), certificates, and dual authentication (both username/password and a certificate)
-   The plug-in custom configuration is stored in the Server Configuration and can be [exported and imported](#plug-in) with it.
-   [Error and messages](#messages) from the plug-in are displayed in SecureTransport Server log.

 

The following conditions apply to Pluggable authentication:  

-   The deployment of multiple authentication plug-ins is not supported.
-   To be authenticated by a plug-in, a SecureTransport account must be created with the “Password is stored locally” option disabled.
-   On an Edge server, Pluggable authentication can be configured for administrators only.
-   Log-in Restriction Policies work if an IP address is used, and may not work when a username is used for a policy (due to the fact that the plug-in may accept one username and return a completely different one).

Before your custom plug-in can be configured and used, it must be deployed, registered, and then enabled in the Server Configuration.

## <span id="Plug-in2"></span>Plug-in deployment

The custom authentication logic (plug-in) is packaged as .jar file that follows the set of conventions described in the [Developer Guide](https://docs.axway.com/bundle/SecureTransport_55_DeveloperGuide_allOS_en_HTML5/page/Content/DevelopersGuide/ab_custom/pluggable_authentication_developer.htm).

To deploy an authentication plug-in, place its JAR file in the `/<st_dir>/plugins/authentication/` directory, and restart the Admin and the TM daemons.

In a cluster environment, the plug-in should be deployed on all nodes, and the Admin service and the TM - restarted on all nodes.

## Plug-in registration

SecureTransport identifies the plug-in by the name of its JAR file. Plug-ins are discovered and registered at the Admin daemon start. Each authentication plug-in is added to two configuration registries in the *Server Configuration* page:

-   `Plugins.Authentication.Admin.Registry`
-   `Plugins.Authentication.EndUser.Registry`

If the plug-in has a custom configuration, its configurable options are added in the Server Configuration page in the following format:

-   `Plugins.Authentication.<plugin_name>.<config_option>`

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><a name="Plug-in"></a> The plug-in configuration options are exported upon  server configuration export. <br/>Before importing a server configuration  with custom plug-in configuration options,  the relative plug-ins must be deployed. Otherwise, their configuration options will not be imported.         </td>
      </tr>
</table>

## Plug-in activation

After being registered, the authentication plug-ins are added to the admin and the end-user registries in the Server Configuration, but they are disabled (have a hash symbol in front of their names). SecureTransport will not automatically activate a newly registered plug-in. To activate a plug-in, remove the # symbol from its name.

Only one plug-in can be enabled per registry at a time. Otherwise, the authentication fails.

If no plug-in is enabled, users are authenticated by using the SecureTransport internal authentication logic.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"> Plug-in activation does not require service restart.         </td>
      </tr>
</table>

## Plug-in management

To undeploy a plug-in:

1\. Delete the JAR file from the `/<st_dir>/plugins/authentication/` directory.

2\. Restart the Admin and TM daemons.  
The plug-in name is then removed from the registries along with its configuration options.

When you uninstall SecureTransport, the plug-ins JAR files are also removed.

To redeploy or update a plug-in:

1\. Undeploy the existing plug-in.

2\. After the Admin and TM daemon restart, go to the Server Configuration registries and make sure the plug-in is removed from the registries.

3\. Deploy the new plug-in (version).

After the restart, the new plug-in is added to the admin and end-user authentication plug-ins list.

## Plug-in configuration

Successful plug-in usage depends on both the authentication methods that are supported by the plug-in and the correct configuration in **Login Settings**.

### Example scenarios and troubleshooting

If you have enabled a plug-in that supports Basic authentication, you must configure the users to log in with a username and a password.

If the enabled plug-in supports authentication with a certificate, you must configure certificate authentication.

To configure dual authentication, you must enable a plug-in that supports both authentication methods.

In case the plug-in is enabled but not configured correctly, and you cannot log in to the administration tool to reconfigure, undeploy the plug-in.

In a Standard Cluster, if the jar file is not uploaded to the secondary node, the configuration will not be considered correct, and an error message will be displayed in the Server Log at startup.

## Pluggable authentication status

The [Login settings](../c_st_login_settings) page displays the Pluggable authentication status and provides a link to the server configuration option related to the end-user authentication plug-ins list.

<span id="Messages"></span>Messages and errors:

-   "*Plugin &lt;plugin name> enabled.*"- an authentication plug-in with that name is enabled.
-   "*No plugins registered.*"- there are no registered plug-ins.
-   "*No authentication plugin enabled*."- there are registered plug-ins, but none of them is enabled.
-   "*Invalid configuration. Several authentication plug-ins are enabled*."- multiple plug-ins are enabled.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Plug-in authentication cannot be applied for a specific user class. When enabled, it applies to all user classes.         </td>
      </tr>
</table>

## Plug-in authentication notifications

On each login request, the following messages are displayed in the Server log:

-   INFO: "`Authentication call to <plugin_name>.`"- notification of an authentication request sent to an enabled authentication plug-in.
-   INFO: “`<plugin_name> successfully authenticated user <username>. Authentication result: SUCCESS, ‘<plugin_message>’”`- notification of a successful authentication by a plug-in
-   INFO: “`<plugin_name> failed to authenticate user. Authentication result: FAILURE, ‘<plugin_message>`’”- notification of an unsuccessful authentication
-   INFO: “`<plugin_name> was unable to authenticate user. Authentication result: CONTINUE, ‘<plugin_message>’`”- the plug-in does not recognize the user and indicates that an SecureTransport internal authentication must be executed.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"> All data sent/ received to/from a plug-in is available on a DEBUG log level.         </td>
      </tr>
</table>

## User mapping

If the authentication process is successful, user mapping is performed.

### End-user only

An end-user can log in to SecureTransport as a virtual account, account template, or an external account. In the first two cases, the user is authenticated based on the user properties pre-defined in SecureTransport; In order for an external user to be successfully authenticated, the plug-in must provide the following attributes: login name, UID, GID, home directory.

1\. The user logs in - the user class is determined by the user’s properties (login name, GID, UID, Address or the custom expression).

2\. SecureTransport searches for an account with the same login name and an externally stored password in its database. If such account is found, the user is mapped.

3\. If there is no virtual account with this login name, SecureTransport tries to map the user to an account template (based on the user class).

4\. If there is no matching account template, the user logs in as an external user. To determine the user, SecureTransport uses the attributes returned by the plug-in. If the plug-in does not return those attributes, the authentication fails.  

### Admin only

1.  If an admin account with that login name and an externally-stored password is not present, the authentication will fail.
2.  For certificate or dual authentication, the respective checkboxes on the [Admin Settings](../../c_st_advancedaccountadministration/c_st_manageadministratoraccounts/t_st_add_administrator_account) page must be enabled.
3.  If the plug-in successfully authenticates an administrator but their account is locked or it is of a 'dbsetup' type, the authentication will fallback to the internal SecureTransport logic.

## System attributes

-   Session attributes

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Attribute Name</th>
         <th>Expression Syntax</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>email         </td>
         <td>${sess.STSESSION_PLUGIN.email}         </td>
      </tr>
      <tr>
         <td>UID         </td>
         <td>${sess.STSESSION_PLUGIN.UID}         </td>
      </tr>
      <tr>
         <td>GID         </td>
         <td>${sess.STSESSION_PLUGIN.GID}         </td>
      </tr>
      <tr>
         <td>homeDir         </td>
         <td>${sess.STSESSION_PLUGIN.homeDir}         </td>
      </tr>
      <tr>
         <td>username         </td>
         <td>${sess.STSESSION_PLUGIN.username}         </td>
      </tr>
   </tbody>
</table>

-   The first element in a custom attribute `<attribute>`

`${sess.STSESSION_PLUGIN.additionalAttributes['<attribute>'][0]}`

-   Advanced routing environment attributes

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Attribute Name</th>
         <th>Expression Syntax</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>email         </td>
         <td>${plugin.email}         </td>
      </tr>
      <tr>
         <td>UID         </td>
         <td>${plugin.uid}         </td>
      </tr>
      <tr>
         <td>GID         </td>
         <td>${plugin.gid}         </td>
      </tr>
      <tr>
         <td>homeDir         </td>
         <td>${plugin.homeDir}         </td>
      </tr>
      <tr>
         <td>userName         </td>
         <td>${plugin.userName}         </td>
      </tr>
   </tbody>
</table>

-   The first element in the attribute `<attribute>`

`${plugin.attributes[‘attribute’][0]}`

## Usage in User Class custom expressions

You can use plug-in attributes in the User Class [custom expressions](../../c_st_accesscontrol/c_st_userclasses/c_st_custom_expressions).

For example:

-   PLUGIN.UID
-   PLUGIN.GID
-   PLUGIN.email
-   PLUGIN.homeDir
-   PLUGIN.pluginName

will return the corresponding attribute value from plug-in data.

For PLUGIN.attributes, you can use the built-in memberOf function (see the **Access Control** -> **User classes** -> **Custom expressions**, also on this page update the possible values for `DXAGENT_USERLOGINTYPE`).

When a custom authentication plug-in is used, the `DXAGENT_USERLOGINTYPE` value is `PLUGIN`; the

`DXAGENT_AUTHN_PLUGIN_NAME` value is the name of the plug-in that performed the authentication for the current user.
