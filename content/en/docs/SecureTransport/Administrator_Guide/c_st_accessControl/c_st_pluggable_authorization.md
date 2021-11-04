{
    "title": "Pluggable /u0430uthorization",
    "linkTitle": "Pluggable Authorization",
    "weight": "160"
}<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Pluggable 0uthorization feature provides the option to add custom authorization logic by plugging it to the system. Existing <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Access Restrictions will be executed after any custom authorization logic. The FTP protocol is an exception, where the internal restrictions will be applied before the custom logic. Custom authorization will be applied for all protocols on client-initiated transfers.

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> will be executing any custom authorization on the following operations:

-   Upload a file
-   Download a file
-   List content of a directory
-   Change permissions (file or directory)
-   Rename a file
-   Delete a file
-   Create a directory
-   Delete a directory

The custom authorization attempt can be either successful or unsuccessful.

In case of success, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> will continue executing the set of applied Access Restrictions (if any). In case of authorization failure, the operation will not be executed.

Pluggable authorization also supports file filtering capabilities. All plug-in implementations are able to use <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> specific environment data described in the Developer's Guide.

> **Note:**
>
> A collection of authentication plug-ins is available in the AMPLIFY Repository.

Before your custom plug-in can be configured and used, it must be deployed, registered, and then enabled in the Server Configuration.

<span id="Plug-in2"></span>

## Plug-in deployment

The custom authorization logic (plug-in) is packaged as .jar file that follows the set of conventions described in the <a href="https://docs.axway.com/bundle/SecureTransport_55_DeveloperGuide_allOS_en_HTML5/page/Content/DevelopersGuide/ab_custom/pluggable_authorization_developer.htm" class="MCXref xref">Developer's Guide</a>.

To deploy an authorization plug-in, place its JAR file in the `/<st_dir>/plugins/authorization/` directory, and restart the Admin and the TM daemons.

In a cluster environment, the plug-in should be deployed on all nodes, and the Admin service and the TM - restarted on all nodes.

> **Note:**
>
> The plug-in is applicable only on SecureTransport Server installation.

## Plug-in registration

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> identifies the plug-in by the name of its JAR file. Plug-ins are discovered and registered at the Admin daemon start. Each authorization plug-in is added to the following configuration registry in the **Server configuration** page:

`Plugins.Authorization.Registry`

If the plug-in has a custom configuration, it is also added to the server configuration for the end users in the following format:

`Plugins.Authorization.<plugin_name>.<config_option>`

> **Note:**
>
> The plug-in configuration options are exported upon server configuration export. Before importing a server configuration with custom plug-in configuration options, the relative plug-ins must be deployed. Otherwise, their configuration options will not be imported.

## Plug-in activation

After being registered, the authorization plug-ins are added to the Server Configuration, but they are disabled (have a hash symbol in front of their names). <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> will not automatically activate a newly registered plug-in. To activate a plug-in, remove the # symbol from its name.

Only one authorization plug-in can be enabled at a time.

> **Note:**
>
> Plug-in activation does not require service restart.

<span id="Plug-in"></span>

## Plug-in management

### Undeploy a plug-in

1\. Delete the JAR file from the `/<st_dir>/plugins/authorization/` directory.

2\. Restart the Admin and TM daemons.  
The plug-in name is then removed from the registry along with its configuration options.

When you uninstall <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, the plug-ins JAR files are also removed.

### Redeploy or update a plug-in

1\. Undeploy the existing plug-in.

2\. After the Admin and TM daemon restart, go to the Server Configuration registry and make sure the plug-in is not present.

3\. Deploy the new plug-in (version).

After the restart, the new plug-in is added to the authorization plug-in list.

## Plug-in configuration

Successful plug-in usage depends on the plug-in implementation (check the Developer's guide for more details).

If you set up a Standard Cluster, and the steps in the [Plug-in deployment](#Plug-in2) section are not accomplished, this will not be considered as a correct configuration.

For example, in a Standard Cluster, if the jar file is not uploaded to the secondary node, the configuration will not be considered correct, and an error message will be displayed in the Server Log at startup.

## Plug-in authorization notifications

On each of the operations authorized by a plug-in, the following messages are displayed in the Server log:

-   On an INFO level: "Custom authorization plug-in &lt;plugin\_name> execution for &lt;type\_of\_operation> operation finished and it took: &lt;estimated\_execution\_time> ms.”
-   Custom authorization result:
    -   On success, on a DEBUG level: "&lt;plugin\_name>'s with class &lt;plugin\_authorizer\_impl> authorization successful. Result is &lt;result\_exitcode>, '&lt;result\_message>'"
    -   On failure, on an INFO level: "&lt;plugin\_name>'s with class &lt;plugin\_authorizer\_impl> authorization failed. Result is &lt;result\_exitcode>, '&lt;result\_message>'"
-   On an Error level, when exception is thrown from the executing of any of the plug-in.

> **Note:**
>
> All data sent/ received to/from a plug-in will be available on a DEBUG log level.

## Plug-in authorization considerations and special cases

The following considerations must be taken into account:

-   Custom authorization plug-ins will be executed for client-initiated transfers only.
-   Authorization will be executed for all protocols on any supported and applicable operation. Therefore, some protocols may not support particular operations (For example, directory listing) and the plug-in’s implementation will not be executed.
-   For pluggable authorization, server-initiated transfers are out of the scope. However, if performing such transfers on one host only with a deployed plug-in (or in two hosts which both have plug-ins deployed), half of the transfer will be authorized against the plug-in. For one of the parties such transfer always appears (and it is) as a true client-initiated transfer since the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> protocol daemons receive a remote connections and perform user operations as it is in an ordinary client upload/download.
-   Custom authorization will be executed before any internal <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> upload/download/filesystem restrictions. An exception is the FTP protocol, where the internal <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> restrictions are evaluated before the custom authorization.
-   Advanced Routing transformation steps will not trigger custom authorization.
-   Publish To Account routing step is excluded from custom authorization.
-   Send To Partner routing step will be authorized in the receiving party if any custom plug-ins are deployed.

## Plug-in file filtering capabilities

In addition, custom authorization supports plugging an implementation for filtering of directory content. Use this feature to restrict the view of some files for a particular user. Refer to the Developer's guide for more information regarding the file filtering extension.

> **Note:**
>
> Filtering is not applied for the directory content in Mailbox section in SecureTransport Web Client.
