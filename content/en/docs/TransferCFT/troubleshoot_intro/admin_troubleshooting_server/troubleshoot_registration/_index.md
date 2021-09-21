{
    "title": "Installation and registration",
    "linkTitle": "Installation and registration",
    "weight": "290"
}This section lists some possible post-installation issues along with corresponding corrective actions when applicable. If corrective actions do not remedy the issue, check the **Support tools** section for more information, or contact support at [support.axway.com](https://support.axway.com/).

## Transfer CFT installation

### Installation fails due to InstallBuilder issue

**UNIX systems**

You cannot run the InstallBuilder if the **noexec mount option** is set on both the /tmp directory and the user's homedir. For example, the installation will fail if you are running unattended mode for a target machine where the user has this mount option set on both directories.

Workarounds include:

-   Remove the noexec option from one of the partitions.
-   Run the .run with a user who has the necessary rights, for example sudo.
-   Create a temporary /home directory on an unprotected disk:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>sudo mkdir /instcft
</p>
            <p>sudo chown &lt;user&gt;:&lt;user&gt; /instcft
</p>
            <p>export HOME=/instcft (unprotected disk)</p>
            <p>./Transfer_CFT_3.7_Install_linux-x86-64_BN13015241.run --mode unattended </p>
         </td>
      </tr>
   </tbody>
</table>

## Central Governance

### <span id="Troubles"></span>Troubleshoot the registration

If Copilot starts, but the Transfer CFT either does not display in the Central Governance **Product List** or registers in error:

-   Verify the Central Governance IP address (or FQDN) used in the Transfer CFT configuration.
-   On the computer running Transfer CFT, check that you can reach Central Governance at the IP address used in the Transfer CFT configuration.
-   Check that the Transfer CFT appears in the Central Governance logs. If not, typically this is because the Transfer CFT is unable contact Central Governance.
-   In Central Governance check **Administration > Services** to ensure that Central Governance is correctly started.
-   Verify the shared secret for Central Governance used in the Transfer CFT configuration.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">See the Central Governance documentation for additional information and details.         </td>
      </tr>
</table>

### Cannot register Transfer CFT with Central Governance (error: (1103))

If you have the following error in the Transfer CFT log:

XFBCOPT S99015 Central Governance: sending self-registration request

XFBCOPT S99015 navigatorNotifSend: Central Governance: sending self-registration request error: (1103)

Handshake failed (1) SSL\_ERROR\_SSL(1) - error:14090086:SSL routines: ssl3\_get\_server\_certificate:certificate verify failed

This is a Certificate Signing Request / CSR failure because the Transfer CFT truststore does not contain the Central Governance root &gt;CA certificate. Perform the steps described in [If CAs change after Transfer CFT registration](https://docs.axway.com/bundle/CentralGovernance_113_UsersGuide_allOS_en_HTML5/page/Content/CFT/cft_registration/t_change_cft_ca.htm).

### Generic registration issue with Central Governance or Flow Manager

You can use the CFTUTIL CHECK command to validate the coherence of parameters, partners, and the Transfer CFT PKI database.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CHECK CONTENT=BRIEF|FULL, FOUT=FileName         </td>
      </tr>
   </tbody>
</table>

See also, [Use the check command](../../../c_intro_userinterfaces/about_cftutil/check_command).

### Registration or Copilot connection issue

While trying to troubleshoot a non-working registration, you may find there are not enough http traces to diagnose connection issues.

To have more request details between Central Governance and Transfer CFT registration or between heartbeats, set the $\_JAVA\_OPTIONS environment variables as shown below (on UNIX in this example).

1.  Requests from Central Governance to Transfer CFT (call to web services):  
    export \_JAVA\_OPTIONS=$\_JAVA\_OPTIONS" -Dorg.apache.commons.logging.Log=org.apache.commons.logging.impl.SimpleLog"
      
    export \_JAVA\_OPTIONS=$\_JAVA\_OPTIONS" -Dorg.apache.commons.logging.simplelog.defaultlog=debug"
      
    export \_JAVA\_OPTIONS=$\_JAVA\_OPTIONS" -Dorg.apache.commons.logging.simplelog.showdatetime=true"
      
    export \_JAVA\_OPTIONS=$\_JAVA\_OPTIONS" -Dorg.apache.commons.logging.simplelog.log.org.apache.href=debug"
2.  Requests from Transfer CFT to Central Governance (registration /heartbeat):  
    export \_JAVA\_OPTIONS=$\_JAVA\_OPTIONS" -Dorg.eclipse.jetty.util.log.class=org.eclipse.jetty.util.log.StdErrLog"
      
    export \_JAVA\_OPTIONS=$\_JAVA\_OPTIONS" -Dorg.eclipse.jetty.LEVEL=DEBUG"
3.  Restart Central Governance to activate the changes.
4.  Ensure the Transfer CFT Connector service in Central Governance is in debug mode:  
    cli > serviceLog -l DEBUG -name "Transfer CFT Connector"
5.  Return to info mode:  
    cli > serviceLog -l INFO -name "Transfer CFT Connector"
6.  Check the logs in:  
    $CG\_HOME/runtime/com.axway.nodes.cftconnector\_{un\_UUID}/uma/logs/provider.log.\*

### Registration fails after installing in service mode when using a firewall

Windows only, firewall enabled

Transfer CFT cannot register in Central Governance when installing Copilot in service mode.

-   Preventive measure: Deactivate the firewall to perform the registration.
-   Workaround: If you encounter this error, perform the following steps to register:
    1.  Stop the Copilot Windows service.
    2.  Manually start the service in a DOSBOX to register.
    3.  Accept the authorization from the Windows firewall.

### Re-register with Central Governance

When Central Governance sends the SSL certificates to Transfer CFT, the UCONF cg.registration\_id parameter is set to a positive integer. If an error occurs, the registration process ends in error. To repeat the registration, perform the following steps:

1.  Stop Transfer CFT.
2.  Stop Copilot.
3.  Set the UCONF cg.registration\_id to its default value (-1) using the unset command:
4.  Start the Transfer CFT Copilot. Copilot starts the registration process.

**More information**

For more information on Central Governance, refer to the Central Governance 1.1.3 documentation.

All Central Governance interoperability parameters are configured with uconf value settings. For more information, refer to the topic UCONF Central Governance parameters.
