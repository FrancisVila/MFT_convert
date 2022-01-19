{
    "title": "Troubleshoot  installation and registration",
    "linkTitle": "Installation and registration",
    "weight": "290"
}This section lists some possible post-installation issues along with corresponding corrective actions when applicable. If corrective actions do not remedy the issue, check the **Support tools** section for more information, or contact support at [support.axway.com](https://support.axway.com/).

## Transfer CFT installation

### Installation fails due to InstallBuilder issue

**UNIX systems**

You cannot run the InstallBuilder if the **noexec mount option** is set on both the` /tmp `directory and the user's `homedir`. For example, the installation will fail if you are running unattended mode for a target machine where the user has this mount option set on both directories.

Workarounds include:

- Remove the `noexec `option from one of the partitions.
- Run the` .run` with a user who has the necessary rights, for example `sudo`.
- Create a temporary `/home` directory on an unprotected disk:

```
sudo mkdir /instcft
sudo chown <user>:<user> /instcft
export HOME=/instcft (unprotected disk)
./Transfer_CFT_3.7_Install_linux-x86-64_BN13015241.run --mode unattended
```

## Central Governance

<span id="Troubles"></span>

### Troubleshoot the registration

If Copilot starts, but the Transfer CFT either does not display in the Central Governance **Product List** or registers in error:

- Verify the Central Governance IP address (or FQDN) used in the Transfer CFT configuration.
- On the computer running Transfer CFT, check that you can reach Central Governance at the IP address used in the Transfer CFT configuration.
- Check that the Transfer CFT appears in the Central Governance logs. If not, typically this is because the Transfer CFT is unable contact Central Governance.
- In Central Governance check **Administration > Services** to ensure that Central Governance is correctly started.
- Verify the shared secret for Central Governance used in the Transfer CFT configuration.

> **Note**
>
> See the Central Governance documentation for additional information and details.

### Cannot register Transfer CFT{{< TransferCFT/transfercftname  >}} with Central Governance{{< TransferCFT/centralgovernancename  >}} (error: (1103))

If you have the following error in the Transfer CFT log:

`XFBCOPT S99015 Central Governance: sending self-registration request`

**`XFBCOPT S99015 navigatorNotifSend: Central Governance: sending self-registration request error: (1103)`**

`Handshake failed (1) SSL_ERROR_SSL(1) - error:14090086:SSL routines: ssl3_get_server_certificate:certificate verify failed`

This is a Certificate Signing Request / CSR failure because the Transfer CFT{{< TransferCFT/transfercftname  >}} truststore does not contain the Central Governance{{< TransferCFT/centralgovernancename  >}} root &gt;CA certificate. Perform the steps described in [If CAs change after Transfer CFT registration](https://docs.axway.com/bundle/CentralGovernance_113_UsersGuide_allOS_en_HTML5/page/Content/CFT/cft_registration/t_change_cft_ca.htm).

### Generic registration issue with Central Governance or Flow Manager

You can use the CFTUTIL CHECK command to validate the coherence of parameters, partners, and the Transfer CFT PKI database.

```
CHECK CONTENT=BRIEF|FULL, FOUT=FileName
```

See also, <a href="../../../c_intro_userinterfaces/about_cftutil/check_command" class="MCXref xref">Use the check command</a>.

### Registration or Copilot connection issue

While trying to troubleshoot a non-working registration, you may find there are not enough http traces to diagnose connection issues.

To have more request details between Central Governance{{< TransferCFT/centralgovernancename  >}} and Transfer CFT{{< TransferCFT/transfercftname  >}} registration or between heartbeats, set the $\_JAVA\_OPTIONS environment variables as shown below (on UNIX in this example).

1. Requests from Central Governance{{< TransferCFT/centralgovernancename >}} to Transfer CFT{{< TransferCFT/transfercftname >}} (call to web services):  
    `export _JAVA_OPTIONS=$_JAVA_OPTIONS" -Dorg.apache.commons.logging.Log=org.apache.commons.logging.impl.SimpleLog"`  
    `export _JAVA_OPTIONS=$_JAVA_OPTIONS" -Dorg.apache.commons.logging.simplelog.defaultlog=debug"`  
    `export _JAVA_OPTIONS=$_JAVA_OPTIONS" -Dorg.apache.commons.logging.simplelog.showdatetime=true"`  
    `export _JAVA_OPTIONS=$_JAVA_OPTIONS" -Dorg.apache.commons.logging.simplelog.log.org.apache.href=debug"`
1. Requests from Transfer CFT{{< TransferCFT/transfercftname >}} to Central Governance{{< TransferCFT/centralgovernancename >}} (registration /heartbeat):  
    `export _JAVA_OPTIONS=$_JAVA_OPTIONS" -Dorg.eclipse.jetty.util.log.class=org.eclipse.jetty.util.log.StdErrLog"`  
    `export _JAVA_OPTIONS=$_JAVA_OPTIONS" -Dorg.eclipse.jetty.LEVEL=DEBUG"`
1. Restart Central Governance to activate the changes.
1. Ensure the ****Transfer CFT Connector**** service in Central Governance{{< TransferCFT/centralgovernancename >}} is in debug mode:  
    `cli > serviceLog -l DEBUG -name "Transfer CFT Connector"`
1. Return to info mode:  
    `cli > serviceLog -l INFO -name "Transfer CFT Connector"`
1. Check the logs in:  
    `$CG_HOME/runtime/com.axway.nodes.cftconnector_{un_UUID}/uma/logs/provider.log.*`

### Registration fails after installing in service mode when using a firewall

****Windows only, firewall enabled****

Transfer CFT cannot register in Central Governance when installing Copilot in service mode.

- Preventive measure: Deactivate the firewall to perform the registration.
- Workaround: If you encounter this error, perform the following steps to register:
    1.  Stop the Copilot Windows service.
    2.  Manually start the service in a DOSBOX to register.
    3.  Accept the authorization from the Windows firewall.

### Re-register with Central Governance

When Central Governance sends the SSL certificates to Transfer CFT{{< TransferCFT/componentshortname  >}}, the UCONF `cg.registration_id parameter` is set to a positive integer. If an error occurs, the registration process ends in error. To repeat the registration, perform the following steps:

1. Stop Transfer CFT{{< TransferCFT/componentshortname >}}.
1. Stop Copilot.
1. Set the UCONF `cg.registration_id` to its default value (-1) using the unset command:
1. Start the Transfer CFT Copilot. Copilot starts the registration process.

******More information******

For more information on Central Governance, refer to the Central Governance 1.1.3 documentation.

All Central Governance interoperability parameters are configured with uconf value settings. For more information, refer to the topic UCONF Central Governance parameters.
