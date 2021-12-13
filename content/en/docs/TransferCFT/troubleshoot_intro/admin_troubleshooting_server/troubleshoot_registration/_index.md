{
    "title": "Troubleshoot  installation and registration",
    "linkTitle": "Installation and registration",
    "weight": "290"
}This section lists some possible post-installation issues along with corresponding corrective actions when applicable. If corrective actions do not remedy the issue, check the **Support tools** section  for more information, or contact support at [support.axway.com](https://support.axway.com/).

## Transfer CFT installation

### Installation fails due to InstallBuilder issue

**UNIX systems**

You cannot run the InstallBuilder if the **noexec mount option** is set on both the` /tmp `directory and the user's `homedir`. For example, the installation will fail if you are running unattended mode for a target machine where the user has this mount option set on both directories.

Workarounds include:

-   Remove the `noexec `option from one of the partitions.
-   Run the` .run` with a user who has the necessary rights, for example `sudo`.
-   Create a temporary `/home` directory on an unprotected disk:

```
sudo mkdir /instcft
sudo chown <user>:<user> /instcft
export HOME=/instcft (unprotected disk)
./Transfer_CFT_3.7_Install_linux-x86-64_BN13015241.run --mode unattended
```

## 

<span id="Troubles"></span>

### Troubleshoot the registration

If Copilot starts, but the Transfer CFT either does not display in the **Product List** or registers in error:

-   Verify the Central Governance IP address (or FQDN)  used in the Transfer CFT configuration.
-   On the computer running Transfer CFT, check that you can reach Central Governance  at the IP address used in the Transfer CFT configuration.
-   Check that the Transfer CFT appears in the Central Governance logs. If  not,  typically this is because the Transfer CFT is unable contact Central Governance.
-   In check **Administration > Services** to ensure that Central Governance is correctly started.
-   Verify the shared secret for Central Governance  used in the Transfer CFT configuration.

> **Note**
>
> See the Central Governance documentation for additional information and details.

### Cannot register {{< TransferCFT/transfercftname  >}} with {{< TransferCFT/centralgovernancename  >}} (error: (1103))

If you have the following error in the Transfer CFT log:

XFBCOPT S99015 Central Governance: sending self-registration request

XFBCOPT S99015 navigatorNotifSend: Central Governance: sending self-registration request error: (1103)

Handshake failed (1) SSL\_ERROR\_SSL(1) - error:14090086:SSL routines: ssl3\_get\_server\_certificate:certificate verify failed

This is  a Certificate Signing Request / CSR failure because the {{< TransferCFT/transfercftname  >}} truststore does not contain the {{< TransferCFT/centralgovernancename  >}} root &gt;CA certificate. Perform the steps described in [If CAs change after Transfer CFT registration](https://docs.axway.com/bundle/CentralGovernance_113_UsersGuide_allOS_en_HTML5/page/Content/CFT/cft_registration/t_change_cft_ca.htm).

### Generic registration issue with Central Governance or Flow Manager

You can use the CFTUTIL CHECK command to validate the coherence of parameters, partners, and the Transfer CFT PKI database.

```
CHECK CONTENT=BRIEF|FULL, FOUT=FileName
```

See also, <a href="../../../c_intro_userinterfaces/about_cftutil/check_command" class="MCXref xref">Use the check command</a>.

### Registration or Copilot connection issue

While trying to troubleshoot a non-working registration, you may find there are not enough http traces to diagnose connection issues.

To have more request details  between {{< TransferCFT/centralgovernancename  >}} and {{< TransferCFT/transfercftname  >}} registration or between heartbeats, set the  $\_JAVA\_OPTIONS environment variables as shown below (on UNIX in this example).

1.  Requests from {{< TransferCFT/centralgovernancename >}} to {{< TransferCFT/transfercftname >}} (call to web services):  
    `export _JAVA_OPTIONS=$_JAVA_OPTIONS" -Dorg.apache.commons.logging.Log=org.apache.commons.logging.impl.SimpleLog"`  
    `export _JAVA_OPTIONS=$_JAVA_OPTIONS" -Dorg.apache.commons.logging.simplelog.defaultlog=debug"`  
    `export _JAVA_OPTIONS=$_JAVA_OPTIONS" -Dorg.apache.commons.logging.simplelog.showdatetime=true"`  
    `export _JAVA_OPTIONS=$_JAVA_OPTIONS" -Dorg.apache.commons.logging.simplelog.log.org.apache.href=debug"`
2.  Requests from {{< TransferCFT/transfercftname >}} to {{< TransferCFT/centralgovernancename >}} (registration /heartbeat):  
    `export _JAVA_OPTIONS=$_JAVA_OPTIONS" -Dorg.eclipse.jetty.util.log.class=org.eclipse.jetty.util.log.StdErrLog"`  
    `export _JAVA_OPTIONS=$_JAVA_OPTIONS" -Dorg.eclipse.jetty.LEVEL=DEBUG"`
3.  Restart Central Governance to activate the changes.
4.  Ensure the **Transfer CFT Connector** service in {{< TransferCFT/centralgovernancename >}} is in debug mode:  
    `cli > serviceLog -l DEBUG -name "Transfer CFT Connector"`
5.  Return to info mode:  
    `cli > serviceLog -l INFO -name "Transfer CFT Connector"`
6.  Check the logs in:  
    `$CG_HOME/runtime/com.axway.nodes.cftconnector_{un_UUID}/uma/logs/provider.log.*`

### Registration fails after installing in service mode when using a firewall

Windows only, firewall enabled

Transfer CFT cannot register in Central Governance when installing Copilot in service mode.

-   Preventive measure: Deactivate the firewall to perform the registration.
-   Workaround: If you encounter this error, perform the following steps to register:
    1.  Stop the Copilot Windows service.
    2.  Manually start the service in a DOSBOX to register.
    3.  Accept the authorization from the Windows firewall.

### Re-register with

When Central Governance sends the SSL certificates to {{< TransferCFT/componentshortname  >}}, the UCONF `cg.registration_id parameter` is set to a positive integer. If an error occurs, the registration process ends in error. To repeat the registration, perform the following steps:

1.  Stop {{< TransferCFT/componentshortname >}}.
2.  Stop  Copilot.
3.  Set the UCONF `cg.registration_id` to its default value (-1) using the unset command:
4.  Start the Copilot. Copilot starts the registration process.

**More information**

For more information on  , refer to the documentation.

All interoperability parameters are configured with uconf value settings. For more information, refer to the topic UCONF parameters.