{
    "title": "userid",
    "linkTitle": "userid",
    "weight": "3710"
}### <span id="userid"></span>userid

#### <span id="userid_CFTRECV"></span>CFTRECV, **<span id="userid_CFTSEND"></span>**CFTSEND

**\[USERID =
{"<u>Transfer CFT userid</u>" | *string32* }\]**

Identifier of the transfer owner.

This parameter is used in server mode
to define the transfer owner associated with a CFTRECV object, or a CFTSEND
IMPL = YES object. If this parameter is not defined, its default value
is the system "userid" of the server Transfer CFT.

This field can include one or more of the following symbolic variables:

-   &PART:
    value substituted by the local identifier of the transfer partner (CFTPART
    id)
-   &SUSER:
    value substituted by the SUSER parameter sent between two Transfer CFTs (PeSIT D CFT profile and PeSIT E protocols)
-   &RUSER:
    value substituted by the ruser
    parameter sent between two Transfer CFTs (PeSIT D CFT profile
    and PeSIT E protocols)

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If a SEND or RECV command is used for the transfer, the identifier 
 of the transfer owner is the system "userid" of the user having 
 activated the command.         </td>
      </tr>
</table>

Windows

Transfer CFT can use domain\\user accounts instead of USER, except when using PassPort AM or internal security. To do so, set the USERID value to the format DOMAIN\\USER.

#### CFTCRON

z/OS (MVS)

The USERID value is used to perform the CRONJOB job submission.

All other platforms

The CRONJOB is executed by the user who started Transfer CFT; you can use the &USERID variable for information purposes.

#### CFTAPPL, CLEARCMD

**USERID = {*string 32*
}**

#### CFTFOLDER

**USERID = {*string 32*
}**

Identifier for a user who can scan a folder. See the section, [Folder monitoring using USERCTRL](../../../../app_integration_intro/intro_folder_monitor/configure_folder_monitoring).

If the USERID is set and the Transfer CFT USERCTRL=YES in the CFTPARM object, the folder monitoring is done on behalf another user.

Maximum length 32 characters.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Using a different user (USERID) is not available on Linux if the event mode is enabled (USEFSEVENTS=YES).         </td>
      </tr>
</table>

When implementing file user rights with USERCTRL on Windows systems, you must run Transfer CFT as a service. Please see [How to enable system users - Windows](../../../../cft_intro_install/windows_install_start_here/windows_install_start_here/running_cft_for_the_first_time_windows/add_system_user_windows) for more information.

[Return to Command index](../../)