{
    "title": "Post installation",
    "linkTitle": "Post installation",
    "weight": "180"
}This chapter describes a series of checks that you should perform to verify your Transfer CFT installation. For more information on performing commands and using CFTUTIL, refer to the *Transfer CFT {{< TransferCFT/releasenumber  >}} [{{< TransferCFT/doctypeuser  >}}](https://docs.axway.com/u/documentation/transfer_cft/index.htm?version=3.2.4)*.

> **Note:**
>
> The information in the Unix Management utilities page applies equally to the Unix-like interface used in HP NonStop.

## Verify the installation

### Check the Transfer CFT server

1.  Load the Transfer CFT profile:
2.  Verify the Transfer CFT version:
3.  *Optionally*, change the Transfer CFT Guardian process names *if you are performing multiple installations*. Because each Transfer CFT process is assigned a Guardian process name, these names should be globally unique.

-   Use the  [cft.guardian.process\_name\_prefix](../intro_os_features/hp_ns_batch#cft.guardian.process_name_prefix) UCONF parameter as described in the UCONF parameters section.
-   Be certain to change this parameter's default value if you are running several Transfer CFT installations at the same time.

Start the Transfer CFT server:

Verify that the default ports used in `$CFTDIRRUNTIME/conf/cft-tcp.conf` are available:

-   1761 (PeSIT Any protocol)
-   1762 (PeSIT Any protocol with SSL authentication)

If the ports are not available, modify the port(s) and re-apply the configuration:

Check that Transfer CFT server is started:

Perform a transfer:

Check the status of the transfer:

Stop the Transfer CFT server:

Verify that the Transfer CFT server is stopped:

### Start the Transfer CFT Copilot server

If you intend to use one of the following, configure it now:

-   Central Governance: see [Activate Central Governance connectivity](../../../governance_services_intro/register_cg)
-   Transfer CFT user interface: see [Using the web browser user interface](../../../c_intro_userinterfaces/web_copilot_ui)

After having configured one of these, you can run the Copilot server:

If you have activated the Central Governance connectivity, you can [Verify the Transfer CFT registration with Central Governance](../../unix_install_start_here/shared_verify_install#Verify).

Transfer CFT HP NonStop provides a start-process supervisor (CFTSUP) that can restart the Transfer CFT server or UI server in the case of an unexpected product stop. For more information, see <a href="hp_ns_sup" class="MCXref xref">Use the NonStop mode</a> .
