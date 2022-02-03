{
    "title": "REST API server configuration",
    "linkTitle": "REST API server configuration",
    "weight": "300"
}Before you can start using REST API operations with {{< TransferCFT/suitevariablesTransferCFTName  >}}, you need to set a few parameters in the {{< TransferCFT/suitevariablesTransferCFTName  >}} configuration.

Before you start
----------------

The REST server is a Copilot service. To start the REST server, use the `copstart `command to [start Copilot](../../../../admin_intro/manage_copilot).

Procedure
---------

{{< TransferCFT/suitevariablesTransferCFTName  >}} requires the following configuration settings before you can use REST API.

{{% TransferCFT/snippets/part_1_config_api%}}

The supported authentication methods are:


| Authentication method  | copilot.restapi.authentication_method  | Details  |
| --- | --- | --- |
| Operating System  | system  | The user/password is checked against the operating system.<br/> <blockquote> **Note**<br/> Note: We strongly recommend that you set copilot.misc.createprocessasuser=yes when using the system option.<br/> </blockquote> **Unix**<br/> You must use <code>cftsu </code>to create users as a superuser is required (sudo or root privilege) to create a group and assign a user to a group. Refer to <a href="../../../../cft_intro_install/unix_install_start_here/run_first_time_ux/run_first_time_ux/t_adding_system_user_unix" >Using system users - UNIX</a> for details.<br/> • Create a group &quot;group1&quot;: groupadd group1<br/> • Add user &quot;user1&quot; to group &quot;group1&quot;: usermod -a -G group1 user1<br/> **Windows**<br/> You require a superuser (administrative user account) to create a group and assign a user to a group.<br/> • Create a group &quot;group1&quot;: net localgroup group1 /add<br/> • Add user &quot;user1&quot; to group &quot;group1&quot;: net localgroup group1 user1 /add<br/> <blockquote> **Note**<br/> Note: For a user belonging to a domain, use: domain\user1 instead of user1<br/> </blockquote>  |
| Access Management  | am  | This methods uses an indirection towards the Access Management system. The user/password is checked by the configured access management system: {{< TransferCFT/suitevariablesFlowManager  >}}, PassPort AM, or internal AM. |
| xfbadm database<br/> (UNIX and HP NonStop exclusively) | xfbadm  | The user/password is checked using the xfbadm base (see the <a href="../../../../cft_intro_install/unix_install_start_here/run_first_time_ux/use_cft_utilities">xfbadmusr and xfbadmgrp utilities</a>).<br/> A user that can execute xfbadmusr/xfbadmgrp utilities can create users and groups after executing the <code>profile </code>from the runtime directory.<br/> • Create a group &quot;group1&quot; with gid=200: xfbadmgrp add -G group1 -p group1_pw -g 200<br/> • From the user prompt, to add a user &quot;user1&quot; to group &quot;group1&quot;enter: xfbadmusr add -l user1 -p user1_pw -u AUTO -g 200 |


********<span id="REST"></span>REST API server authentication method********

********![](/Images/TransferCFT/authentication_copilot_server.png)********

> **Note**
>
> Note: 1. If copilot.restapi.authentication_method = system, then your access management type must be set to either am.type= none, or both am.type=internal and am.internal.group_database = system.

> **Note**
>
> Note: 2. If copilot.restapi.authentication_method = xbfadm, then your access management type must be set to either am.type= none, or both am.type=internal and am.internal.group_database = xbfadm.

Parameter

Type

Default

Description

copilot.restapi.enable

bool

No

Enable/disable the REST API service:

- Yes: enable
- No: disable

copilot.restapi.serverport

int

1768

REST API server port.

copilot.restapi.authentication_method

string

system (Windows)

xfbadm (UNIX)

Defines authentication method.

 

See also, [xfbadmusr utilitiy.](../../../../cft_intro_install/unix_install_start_here/run_first_time_ux/use_cft_utilities#xfbadmusr1)

copilot.restapi.nb_workers

int

4

Number of activated workers that process the REST API requests.

copilot.restapi.maxclient

int

256

Number of client connections handled per REST worker.

copilot.restapi.coms_id

string

coms

The TCPIP CFTCOM object identifier used by the REST API server to communicate with the Transfer CFT server.

Leave empty to use
the COM file instead.

copilot.restapi.catalog.retry_delay

int

5

- The delay between retries
    in seconds. The Copilot server checks the request status in catalog every retry_delay seconds.
- The delay between retries
    in seconds. The Copilot server checks the request status in catalog every retry_delay seconds.

 

 

 

copilot.restapi.catalog.retry_timeout

int

30

The default value of the apiTimeout parameter as defined in the request URL.

Available exclusively for POST requests.
