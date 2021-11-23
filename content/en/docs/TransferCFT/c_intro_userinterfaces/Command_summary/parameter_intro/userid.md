{
    "title": "userid",
    "linkTitle": "userid",
    "weight": "3680"
}<span id="userid"></span>

### userid

<span id="userid_CFTRECV"></span>

#### CFTRECV, **<span id="userid_CFTSEND"></span>**CFTSEND

**\[USERID =
{"<u>Transfer CFT userid</u>" | *string32* }\]**

Identifier of the transfer owner.

This parameter is used in server mode
to define the transfer owner associated with a CFTRECV object, or a CFTSEND
IMPL = YES object. If this parameter is not defined, its default value
is the system "userid" of the server {{< TransferCFT/componentshortname  >}}.

This field can include one or more of the following symbolic variables:

-   **&PART**:
    value substituted by the local identifier of the transfer partner (CFTPART
    <span style="font-weight: bold;">id</span>)
-   <span style="font-weight: bold;">&SUSER</span>:
    value substituted by the SUSER parameter sent between two <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>s (PeSIT D CFT profile and PeSIT E protocols)
-   &<span style="font-weight: bold;">RUSER</span>:
    value substituted by the <span style="font-weight: bold;">ruser</span>
    parameter sent between two <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>s (PeSIT D CFT profile
    and PeSIT E protocols)

> **Note:**
>
> If a SEND or RECV command is used for the transfer, the identifier
> of the transfer owner is the system "userid" of the user having
> activated the command.

Windows

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> can use domain\\user accounts instead of USER, except when using PassPort AM or internal security. To do so, set the USERID value to the format DOMAIN\\USER.

#### CFTCRON

z/OS (MVS)

The USERID value is used to perform the CRONJOB job submission.

All other platforms

The CRONJOB is executed by the user who started <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span>; you can use the &USERID variable for information purposes.

#### CFTAPPL, CLEARCMD

**USERID = {*string 32*
}**

#### CFTFOLDER

**USERID = {*string 32*
}**

Identifier for a user who can scan a folder. See the section, [Folder monitoring using USERCTRL](../../../../app_integration_intro/intro_folder_monitor/configure_folder_monitoring#Folder2).

If the USERID is set and the Transfer CFT USERCTRL=YES in the CFTPARM object, the folder monitoring is done on behalf another user.

Maximum length 32 characters.

> **Note:**
>
> Using a different user (USERID) is not available on Linux if the event mode is enabled (USEFSEVENTS=YES).

When implementing file user rights with USERCTRL on Windows systems, you must run Transfer CFT as a service. Please see <a href="" class="MCXref xref">How to enable system users - Windows</a> for more information.

[Return to Command index](../../)
