{
    "title": "Register with Flow Manager",
    "linkTitle": "Register with Flow Manager",
    "weight": "180"
}This section describes how to register a Transfer CFT instance with either an on premise or SaaS Flow Manager. You can refer to the [Flow Manager User Guide](https://docs.axway.com/bundle/FlowManager_20_allOS_en_HTML5/page/user_guide.html) for Flow Manager details.

## Prerequisites

Transfer CFT prerequisites

-   An installed Transfer CFT version 3.6 or higher on a compatible platform.
-   Transfer CFT and Copilot services are stopped.

Flow Manager **prerequisites**

-   The shared secret that the Flow Manager administrator generated. Refer to the [Flow Manager User Guide](https://docs.axway.com/bundle/FlowManager_20_allOS_en_HTML5/page/flow_manager_user_guide.html) for details.
-   If you are implementing a SaaS cloud Flow Manager, you additionally require:
    -   A Flow Manager Agent capable of interconnecting Flow Manager and your Transfer CFT instance. Refer to the [Flow Manager User Guide](https://docs.axway.com/bundle/FlowManager_20_allOS_en_HTML5/page/user_guide.html) for details.
    -   Access to an on-demand Flow Manager SaaS environment.

## Automatically activate connectivity

UNIX/Windows

The automatic activation is only available on UNIX and Windows platforms and can be done during the installation. Please refer to the OS specific *Transfer CFT Installation Guide &gt; Customize the initialize.properties file &gt; Central Governance* section.

## Manually activate connectivity

This section describes the steps to register your Transfer CFT with Flow Manager. The procedure is the same for either an on-premise or SaaS Flow Manager, with the exception of the two steps described in [Define the Flow Manager Agent](#define).

All commands in this section are performed using CFTUTIL unless stated otherwise. For details on the UCONF parameters referenced in this section, please see [UCONF: Central Governance options](cg_uconf_register_parms.htm).

#### Define UCONF parameters used for Transfer CFT instance identification

Set the parameters used to identify a Transfer CFT instance. Follow these guidelines, otherwise the registration will fail:

-   The length of the `cft.instance_id` value is limited to 24 characters.
-   The address set in cft.full\_hostname must be reachable from Flow Manager or a Flow Manager Agent (for a SaaS deployment).

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>uconfset id=cft.instance_id, value=&lt;cft_id&gt;</p>
<p>uconfset id=cft.instance_group, value=&lt;cft_instance_group&gt;</p>
<p>uconfset id=cft.full_hostname, value=&lt;cft_address&gt;</p></td>
</tr>
</tbody>
</table>

Additionally, if running in a multi-host/multi-node environment, you must set the load balancer address(FQDN or IP address) and port that Flow Manager uses to reach the Transfer CFT (copilot.general.ssl\_serverport):

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>uconfset id=cft.multi_node.load_balancer.host, value=&lt;load_balancer_address&gt;</p>
<p>uconfset id=<span>cft.multi_node.load_balancer.port,value=&lt;load_balancer_port&gt;</span></p></td>
</tr>
</tbody>
</table>

#### Define the Flow Manager Agent for SaaS

Define the name of the Flow Manager Agent that the Flow Manager must use to connect with your Transfer CFT instance.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>uconfset id=cg.metadata.agent.value, value=&lt;agent_host_FQDN&gt;</p></td>
</tr>
</tbody>
</table>

Please refer to the [Flow Manager User Guide](https://docs.axway.com/bundle/FlowManager_20_allOS_en_HTML5/page/user_guide.html) for Flow Manager Agent details.

#### Optionally define a proxy server for on-premise Flow Manager to Transfer CFT communication

To use a proxy server for your on-premise Flow Manager to connect to Transfer CFT, set the following parameters.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>uconfset id=cg.proxy.in.host, value= &lt;proxy_address&gt;</p>
<p>uconfset id=cg.proxy.in.port<span>,value= &lt;proxy_port&gt;</span></p>
<p>uconfset id=cg.proxy.in.login, value= &lt;proxy_login&gt;</p>
<p>uconfset id=<span>cg.proxy.in.password, value= &lt;proxy_login_password&gt;</span></p></td>
</tr>
</tbody>
</table>

#### Optionally define a proxy server for Transfer CFT to Flow Manager communication

To use a proxy server for your Transfer CFT to connect to Flow Manager, set the following parameters.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>uconfset id=cg.proxy.out.host, value= &lt;proxy_address&gt;</p>
<p>uconfset id=cg.proxy.out.port,value= &lt;proxy_port&gt;</p>
<p>uconfset id=cg.proxy.out.login, value= &lt;proxy_login&gt;</p>
<p>uconfset id=cg.proxy.out.password, value= &lt;proxy_login_password&gt;</p></td>
</tr>
</tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Transfer CFT can use the Flow Manager Agent as the outgoing HTTP proxy when connecting to the Flow Manager SaaS.</td>
</tr>
</tbody>
</table>

#### Import the root certificate for the Flow Manager certificate

Before Transfer CFT can register with Flow Manager, the HTTPS root certificate's CA must be known and trusted by the registering Transfer CFT.

1.  Download the HTTPS root certificate's CA, which is used to authenticate Flow Manager.
2.  Import this root CA into the PKI database using the PKIUTIL PKICER command.
3.  Set the `iname `to the root CA path.
4.  Define the UCONF variable `cg.ca_cert_id`, which must correspond with the value you set in the previous step. It is required so that Transfer CFT knows which certificate to use to authenticate Flow Manager. Using CFTUTIL:

#### Define the parameters used for the Flow Manager connection

Set the following parameters that are used to connect to Flow Manager.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>uconfset id=cg.host, value=&lt;Flow_Manager_FQDN&gt;</p>
<p>uconfset id=cg.port, value=&lt;FM_port&gt;</p></td>
</tr>
</tbody>
</table>

Set the shared secret that the Flow Manager administrator generated and provided.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>uconfset id=cg.shared_secret, value=&lt;Shared_Secret&gt;</td>
</tr>
</tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">If the shared secret is incorrect, <span>Transfer CFT</span> may be rejected with a 403 HTTP code. If this happens, the <span>cg.enable </span>mode becomes disabled on your Transfer CFT to avoid sending repeat requests to Flow Manager.</td>
</tr>
</tbody>
</table>

#### Optionally define the configuration policy for registration

You may want to automatically assign an existing Flow Manager configuration policy during the Transfer CFT registration. To do so, set the UCONF parameter `cg.configuration_policy` to the name of the desired policy.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>uconfset id=cg.configuration_policy, value=&lt;name_of_policy&gt;</p></td>
</tr>
</tbody>
</table>

#### Optionally customize the business certificate Distinguished Name (DN)

You may want to customize the business certificate's Distinguished Name (DN), which is generated during the Flow Manager registration or certificate renewal. Set the UCONF parameter cg.certificate.business.csr\_dn to the custom value. The default is O=Axway,OU=MFT,CN=%uconf:cft.full\_hostname%. Remember to separate tokens by a comma.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>uconfset id=cg.certificate.business.csr_dn, value='O=MyCompany,OU=MFT,CN=%uconf:cft.full_hostname%'</td>
</tr>
</tbody>
</table>

A best practice is to customize the certificate DN prior to registration. However, if you are customizing the certificate DN after the Transfer CFT registration, you can force an immediate renewal or wait for the automatic renewal as described in [SSL certificate renewal](../cg_postregister).

#### Optionally customize the governance certificate Distinguished Name (DN)

To override the governance certificate's Distinguished Name (DN), which is generated during the Flow Manager registration or certificate renewal, set the UCONF parameter cg.certificate.governance.csr\_dn to the custom value. The default is O=Axway,OU=MFT,CN=&lt;Transfer CFT $(cft.instance\_id)>. Remember to separate tokens by a comma.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>uconfset id=cg.certificate.governance.csr_dn, value='O=MyCompany,OU=MFT,CN=%uconf:cft.full_hostname%'</td>
</tr>
</tbody>
</table>

A best practice is to customize the certificate DN prior to registration. However, if you are customizing the certificate DN after the Transfer CFT registration, you can force an immediate renewal or wait for the automatic renewal as described in [SSL certificate renewal](../cg_postregister).

#### <span id="Customize_keylength"></span>Optionally customize the certificates' key length

By default Transfer CFT generates a key length of 2048 bits for its Governance and Business certificates. Optionally you can modify these values to 4096 bits.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>uconfset id=cg.certificate.governance.key_len, value=4096</p>
<p>uconfset id=cg.certificate.business.key_len, value=4096</p></td>
</tr>
</tbody>
</table>

#### Enable Flow Manager

To enable connectivity, enter:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>uconfset id=cg.enable, value=yes</p></td>
</tr>
</tbody>
</table>

#### Perform the check command to validate parameters

Use the CFTUTIL CHECK command to validate the coherence of parameters, partners, and the Transfer CFT PKI database.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CHECK CONTENT=BRIEF|FULL, FOUT=FileName</td>
</tr>
</tbody>
</table>

Check the list in the output for errors and correct all errors before attempting registration. See also, [Use the check command](../../c_intro_userinterfaces/about_cftutil/check_command).

## Register or re-register

Ensure that `cft_registration_id `is reset to -1. Otherwise, reset it as follows:  

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTUTIL uconfunset id=cg.registration_id</p></td>
</tr>
</tbody>
</table>

Start the Transfer CFT Copilot to automatically trigger registration. From the Flow Manager UI, check the **Product List** to confirm that the registration was successful.

### <span id="Define"></span>
