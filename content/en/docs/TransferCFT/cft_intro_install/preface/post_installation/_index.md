{
    "title": "Post installation",
    "linkTitle": "Post installation",
    "weight": "180"
}This chapter describes a series of checks that you should perform to verify your Transfer CFT installation. For more information on performing commands and using CFTUTIL, refer to the *Transfer CFT <span class="mc-variable axway_variables.Release_Number variable">3.9</span> [<span class="mc-variable suite_variables.DocTypeUser variable">User Guide</span>](https://docs.axway.com/u/documentation/transfer_cft/index.htm?version=3.2.4)*.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>The information in the Unix <a href="../../unix_install_start_here/run_first_time_ux/use_cft_utilities" class="MCXref xref">Management utilities</a> page applies equally to the Unix-like interface used in HP NonStop.         </td>
      </tr>
   </tbody>
</table>

## Verify the installation

### Check the Transfer CFT server

Load the Transfer CFT profile:


    . <installation_directory>/runtime/profile

Verify the Transfer CFT version:


    CFTUTIL about

*Optionally*, change the Transfer CFT Guardian process names *if you are performing multiple installations*. Because each Transfer CFT process is assigned a Guardian process name, these names should be globally unique.

-   Use the  [cft.guardian.process\_name\_prefix](../intro_os_features/hp_ns_batch#cft.guardian.process_name_prefix) UCONF parameter as described in the UCONF parameters section.
-   Be certain to change this parameter's default value if you are running several Transfer CFT installations at the same time.

<!-- -->


    CFTUTIL uconfset id=cft.guardian.process_name_prefix,value=LB

Start the Transfer CFT server:


    cft start

Verify that the default ports used in <span class="code">$CFTDIRRUNTIME/conf/cft-tcp.conf</span> are available:

-   1761 (PeSIT Any protocol)
-   1762 (PeSIT Any protocol with SSL authentication)

If the ports are not available, modify the port(s) and re-apply the configuration:



    cftupdate $CFTDIRRUNTIME/conf/cft-tcp.conf
                            

Check that Transfer CFT server is started:



    cftping -v
    cftlog

Perform a transfer:


    CFTUTIL SEND PART=PARIS, IDF=TEST

Check the status of the transfer:


    CFTUTIL LISTCAT

Stop the Transfer CFT server:


    cft stop

Verify that the Transfer CFT server is stopped:


    cftping –v

### Start the Transfer CFT Copilot server

If you intend to use one of the following, configure it now:

-   Central Governance: see [Activate Central Governance connectivity](../../../governance_services_intro/register_cg)
-   Transfer CFT user interface: see [Using the web browser user interface](../../../c_intro_userinterfaces/web_copilot_ui)

After having configured one of these, you can run the Copilot server:



    cd <CFTDIRRUNTIME>
    . . /profile
    copstart
    http://MyHostName:1766

If you have activated the Central Governance connectivity, you can [Verify the Transfer CFT registration with Central Governance](../../unix_install_start_here/shared_verify_install#Verify).

Transfer CFT HP NonStop provides a start-process supervisor (CFTSUP) that can restart the Transfer CFT server or UI server in the case of an unexpected product stop. For more information, see <a href="hp_ns_sup" class="MCXref xref">Use the NonStop mode</a> .