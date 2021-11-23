{
    "title": "After Upgrading ",
    "linkTitle": "After migrating",
    "weight": "90"
}## Update password environment variables

After upgrade, check your files (exits, scripts) for usage of the `p_cs_username` and `p_cs_password` environment variables. Update those files, using the new environment variables.

In the new version, when access management is enabled, the password used by commands is stored encrypted. This concerns the command line utility, exits, and scripts. The environment variables are now the following:

-   administration user: `p_cs_username`
-   decryption key file pathname`: p_cs_dk_file`
-   encrypted password file pathname: `p_cs_encpass_file `

(Storing the cleartext password in the environment variable p\_cs\_password is no longer supported.)

For more information regarding password encryption, see *Security guide &gt;* [Password management](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Password_management.htm).

> **Note:**
>
> If you are migrating the architecture only - for example, migrating from aix-32 to aix-64 - and the source Gateway version is 6.17.x, then you need to upgrade the files pointed by the p\_cs\_dk\_file and p\_cs\_encpass\_file variables. You can either recreate them using pelencpass command, or simply copy them from the Gateway source installation.

## Copy parameters

**Important:** after upgrading Gateway from version 6.16.x to 6.17, perform the following steps:

1.  Copy the `cstcp_command `parameter from `uconfdict1.ini `to `pelsetup.ini`. The parameter values should be:
    -   UNIX: `ipelapid.sock -tpt CSTCP`
    -   Windows: `/new /hide %p_home_ dir%\bin\ipelsock.exe -tpt CSTCP`
2.  Copy the `notif_exec_path `parameter from `pelsetup.def `to `conffile`. The parameter values should be:
    -   UNIX:  
        `$p_home_dir/bin/notif`
    -   Windows: `"/new /hide notif.exe"`

## Update {{< Gateway/securerelayname  >}}

If you are using {{< Gateway/securerelayname  >}} in conjunction with {{< Gateway/gatewayname  >}} V6.17, it is strongly advised to update to {{< Gateway/securerelayname  >}} Version 2.6.4 at least.

If {{< Gateway/gatewayname  >}} was already configured with {{< Gateway/securerelayname  >}}, then {{< Gateway/copyorrecreate  >}}:

-   xsrsaltfile.dat
-   xsrdkfile.dat
-   xsrpwd.dat

If {{< Gateway/passportname  >}} termination is used, then {{< Gateway/copyorrecreate  >}}:

-   pkisaltfile.dat
-   pkidkfile.dat
-   pkipwd.dat

## Updating PassPort configuration 7

### use\_legacy\_settings

If `use_legacy_settings `was used for {{< Gateway/passportname  >}}, then:

-   For {{< Gateway/passportname >}} AM configuration: {{< Gateway/copyorrecreate >}}:
    -   amloginsalt.dat
    -   amlogindk.dat
    -   amloginpass.dat
-   For PassPort PS configuration: {{< Gateway/copyorrecreate >}}:
    -   xpploginsalt.dat
    -   xpplogindk.dat
    -   xpploginpass.dat
-   For PassPort PM configuration: {{< Gateway/copyorrecreate >}}:
    -   tpmloginsalt.dat
    -   tpmlogindk.dat
    -   tpmloginpass.dat

### New passport configuration

Steps to follow if a new passport configuration was used:

-   For PassPort AM configuration: copy the following files from {{< Gateway/gatewayname >}} 6.16.x, (or recreate the \*.dat files):
    -   passport.p12
    -   PassportCA.crt
    -   ppss.dat
    -   ppssdk.dat
    -   ppsssalt.dat
    -   ppcertsalt.dat
    -   ppcertdk.dat
    -   ppcertpass.dat

<!-- -->

-   For PassPort PS configuration: {{< Gateway/copyorrecreate >}}:
    -   pploginsalt.dat
    -   pplogindk.dat
    -   pploginpass.dat
-   For PassPort PM configuration: {{< Gateway/copyorrecreate >}}:
    -   pploginsalt.dat
    -   pplogindk.dat
    -   pploginpass.dat

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
