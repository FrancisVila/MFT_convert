{
    "title": "Register Transfer CFT with Flow Manager",
    "linkTitle": "Register with Flow Manager",
    "weight": "180"
}This section describes how to register a Transfer CFT instance with either an on premise or SaaS <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span>. You can refer to the [Flow Manager User Guide](https://docs.axway.com/bundle/FlowManager_20_allOS_en_HTML5/page/user_guide.html) for Flow Manager details.

## Prerequisites

<span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> prerequisites

-   An installed Transfer CFT version 3.6 or higher on a compatible platform.
-   Transfer CFT and Copilot services are stopped.

<span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> **prerequisites**

-   The shared secret that the Flow Manager administrator generated. Refer to the [Flow Manager User Guide](https://docs.axway.com/bundle/FlowManager_20_allOS_en_HTML5/page/flow_manager_user_guide.html) for details.
-   If you are implementing a SaaS cloud Flow Manager, you additionally require:
    -   A Flow Manager Agent capable of interconnecting Flow Manager and your <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> instance. Refer to the [Flow Manager User Guide](https://docs.axway.com/bundle/FlowManager_20_allOS_en_HTML5/page/user_guide.html) for details.
    -   Access to an on-demand Flow Manager SaaS environment.

## Automatically activate connectivity

UNIX/Windows

The automatic activation is only available on UNIX and Windows platforms and can be done during the installation. Please refer to the OS specific *Transfer CFT Installation Guide &gt; Customize the initialize.properties file &gt; Central Governance* section.

## Manually activate connectivity

This section describes the steps to register your <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> with <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span>. The procedure is the same for either an on-premise or SaaS <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span>, with the exception of the two steps described in [Define the <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> Agent](#Define).

All commands in this section are performed using CFTUTIL unless stated otherwise. For details on the UCONF parameters referenced in this section, please see UCONF: Central Governance options.

#### Define UCONF parameters used for <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> instance identification

Set the parameters used to identify a Transfer CFT instance. Follow these guidelines, otherwise the registration will fail:

-   The length of the `cft.instance_id` value is limited to 24 characters.
-   The address set in <span class="code">cft.full\_hostname</span> must be reachable from <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> or a Flow Manager Agent (for a SaaS deployment).

<!-- -->



    uconfset id=cft.instance_id, value=<cft_id>
    uconfset id=cft.instance_group, value=<cft_instance_group>
    uconfset id=cft.full_hostname, value=<cft_address>

Additionally, if running in a multi-host/multi-node environment, you must set the load balancer address(FQDN or IP address) and port that <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> uses to reach the Transfer CFT (<span class="code">copilot.general.ssl\_serverport</span>):



    uconfset id=cft.multi_node.load_balancer.host, value=<load_balancer_address>
    uconfset id=cft.multi_node.load_balancer.port,value=<load_balancer_port>

#### Define the Flow Manager Agent for SaaS

Define the name of the Flow Manager Agent that the Flow Manager must use to connect with your Transfer CFT instance.



    uconfset id=cg.metadata.agent.value, value=<agent_host_FQDN>

Please refer to the [Flow Manager User Guide](https://docs.axway.com/bundle/FlowManager_20_allOS_en_HTML5/page/user_guide.html) for Flow Manager Agent details.

#### Optionally define a proxy server for on-premise <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> to <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> communication

To use a proxy server for your on-premise <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> to connect to <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>, set the following parameters.



    uconfset id=cg.proxy.in.host, value= <proxy_address>
    uconfset id=cg.proxy.in.port,value= <proxy_port>
    uconfset id=cg.proxy.in.login, value= <proxy_login>
    uconfset id=cg.proxy.in.password, value= <proxy_login_password>

#### Optionally define a proxy server for <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> to <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> communication

To use a proxy server for your <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> to connect to <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span>, set the following parameters.



    uconfset id=cg.proxy.out.host, value= <proxy_address>
    uconfset id=cg.proxy.out.port,value= <proxy_port>
    uconfset id=cg.proxy.out.login, value= <proxy_login>
    uconfset id=cg.proxy.out.password, value= <proxy_login_password>  

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Transfer CFT can use the Flow Manager Agent as the outgoing HTTP proxy when connecting to the Flow Manager SaaS.         </td>
      </tr>
   </tbody>
</table>

#### Import the root certificate for the <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> certificate

Before Transfer CFT can register with Flow Manager, the HTTPS root certificate's CA must be known and trusted by the registering Transfer CFT.

1.  Download the HTTPS root certificate's CA, which is used to authenticate <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span>.
2.  Import this root CA into the PKI database using the PKIUTIL PKICER command.
3.  Set the `iname `to the root CA path.
4.  Define the UCONF variable `cg.ca_cert_id`, which must correspond with the value you set in the previous step. It is required so that <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> knows which certificate to use to authenticate <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span>. Using CFTUTIL:

#### Define the parameters used for the <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> connection

Set the following parameters that are used to connect to <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span>.



    uconfset id=cg.host, value=<Flow_Manager_FQDN> 
    uconfset id=cg.port, value=<FM_port>

Set the shared secret that the Flow Manager administrator generated and provided.


     uconfset id=cg.shared_secret, value=<Shared_Secret>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>If the shared secret is incorrect, <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> may be rejected with a 403 HTTP code. If this happens, the <span class="code">cg.enable </span>mode becomes disabled on your Transfer CFT to avoid sending repeat requests to Flow Manager.         </td>
      </tr>
   </tbody>
</table>

#### Optionally define the configuration policy for registration

You may want to automatically assign an existing <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> configuration policy during the <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> registration. To do so, set the UCONF parameter `cg.configuration_policy` to the name of the desired policy.



    uconfset id=cg.configuration_policy, value=<name_of_policy>

#### Optionally customize the business certificate Distinguished Name (DN)

You may want to customize the business certificate's Distinguished Name (DN), which is generated during the <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> registration or certificate renewal. Set the UCONF parameter cg.certificate.business.csr\_dn to the custom value. The default is O=Axway,OU=MFT,CN=%uconf:cft.full\_hostname%. Remember to separate tokens by a comma.


    uconfset id=cg.certificate.business.csr_dn, value='O=MyCompany,OU=MFT,CN=%uconf:cft.full_hostname%'

A best practice is to customize the certificate DN prior to registration. However, if you are customizing the certificate DN after the Transfer CFT registration, you can force an immediate renewal or wait for the automatic renewal as described in [SSL certificate renewal](../cg_postregister#SSL).

#### Optionally customize the governance certificate Distinguished Name (DN)

To override the governance certificate's Distinguished Name (DN), which is generated during the <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> registration or certificate renewal, set the UCONF parameter cg.certificate.governance.csr\_dn to the custom value. The default is O=Axway,OU=MFT,CN=&lt;Transfer CFT $(cft.instance\_id)>. Remember to separate tokens by a comma.


    uconfset id=cg.certificate.governance.csr_dn, value='O=MyCompany,OU=MFT,CN=%uconf:cft.full_hostname%'

A best practice is to customize the certificate DN prior to registration. However, if you are customizing the certificate DN after the Transfer CFT registration, you can force an immediate renewal or wait for the automatic renewal as described in [SSL certificate renewal](../cg_postregister#SSL).

<span id="Customize_keylength"></span>

#### Optionally customize the certificates' key length

By default Transfer CFT generates a key length of 2048 bits for its Governance and Business certificates. Optionally you can modify these values to 4096 bits.



    uconfset id=cg.certificate.governance.key_len, value=4096

    uconfset id=cg.certificate.business.key_len, value=4096

#### Enable <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span>

To enable connectivity, enter:



    uconfset id=cg.enable, value=yes

#### Perform the check command to validate parameters

Use the CFTUTIL CHECK command to validate the coherence of parameters, partners, and the Transfer CFT PKI database.


    CHECK CONTENT=BRIEF|FULL, FOUT=FileName

Check the list in the output for errors and correct all errors before attempting registration. See also, <a href="../../c_intro_userinterfaces/about_cftutil/check_command" class="MCXref xref">Use the check command</a>.

## Register or re-register

Ensure that `cft_registration_id `is reset to <span class="code">-1</span>. Otherwise, reset it as follows:  



     CFTUTIL uconfunset id=cg.registration_id

Start the <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> Copilot to automatically trigger registration. From the Flow Manager UI, check the **Product List** to confirm that the registration was successful.

<span id="Define"></span>

### 