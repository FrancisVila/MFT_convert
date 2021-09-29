{
    "title": "Secure Relay with a standalone architecture",
    "linkTitle": "Secure Relay with a standalone architecture",
    "weight": "250"
}This page describes how to configure Transfer CFT in a standalone architecture for use with Secure Relay.

Step overview:

-   Install 1 or more Secure Relay Router Agents
-   Configure Secure Relay
-   Enable Secure Relay and configure Java
-   Configure additional Transfer CFT objects
    -   Network object CFTNET
    -   Protocol object CFTPROT
    -   Partner object CFTPART and CFTTCP

## Secure Relay Router Agent installation

Follow the installation instructions provided in the [Secure Relay RA Installation Guide](https://docs.axway.com/bundle/SecureRelay_271_InstallationGuide_allOS_en_PDF/resource/SecureRelayRA_InstallationGuide_allOS_en_PDF.pdf). During installation, it is essential that you configure the Router Agent CA and user certificate as follows to enable secure communication between the Master Agent and Router Agent:

-   &lt;CACertificate>CA\_for\_RA.der&lt;/CACertificate>
-   &lt;UserCertificate>USER\_for\_RA.p12&lt;/UserCertificate>

You need these values when you configure the Master Agent in the Transfer CFT configuration, where the user certificate that you use must be signed by CA\_for\_RA. You should use the same CA and USER certificate as for the Master Agent.

## Configure the Router Agents in Transfer CFT

After completing installation, configure the Router Agents in the Transfer CFT configuration.

1.  Set the value for the number of Router Agents using the `secure_relay.ra` parameter. Transfer CFT generates a set of `secure_relay.ra.n.*` parameters, where the number, *n*, corresponds to the number of Router Agents you defined in this parameter.
2.  You can use the default values for most fields, but you must customize the` secure_relay.ra.0.dmz` parameter. This value must be unique; for example, you can increment the DMZ0 value by one for each Router Agent so that the  second Router Agent has the value` secure_relay.ra.0.dmz = DMZ1`.
3.  Configure the host address for each Secure Relay host using secure\_relay.ra.0.host.

Example of two Router Agent definitions

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>secure_relay.ra = 2</p>
<p> </p>
<p>secure_relay.ra.0.enable = yes</p>
<p>secure_relay.ra.0.dmz = <span>DMZ0</span></p>
<p>secure_relay.ra.0.host = <span>@hostF</span></p>
<p>secure_relay.ra.0.admin_port = 6810</p>
<p>secure_relay.ra.0.comm_port = 6811</p>
<p>secure_relay.ra.0.nb_data_connections = 5</p>
<p>secure_relay.ra.0.data_channel_ciphering = No</p>
<p>secure_relay.ra.0.outcall_network_interface =</p>
<p> </p>
<p>secure_relay.ra.1.enable = Yes</p>
<p>secure_relay.ra.1.dmz = <span>DMZ1</span></p>
<p>secure_relay.ra.1.host = <span>@hostG</span></p>
<p>secure_relay.ra.1.admin_port = 6810</p>
<p>secure_relay.ra.1.comm_port = 6811</p>
<p>secure_relay.ra.1.nb_data_connections = 5</p>
<p>secure_relay.ra.1.data_channel_ciphering = No</p>
<p>secure_relay.ra.1.outcall_network_interface =</p></td>
</tr>
</tbody>
</table>

## Configure the Master Agent in Transfer CFT

Configure the following UCONF parameters to enable the Master Agent communication with the Router Agent:

-   secure\_relay.ma.ca\_cert\_fname = &lt;must be the same as the CA\_for\_RA.der value>
-   secure\_relay.ma.cert\_fname = &lt;must be a P12 user certificate that is signed by the CA\_for\_RA.der>
-   secure\_relay.ma.cert\_password = &lt;user certificate password>

## Enable Secure Relay and configure the Java

In Transfer CFT from the CFTUTIL prompt, perform the following commands:

1.  Enable Secure Relay:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>UCONFSET id=secure_relay.enable ,value=yes</td>
    </tr>
    </tbody>
    </table>

2.  Set the full path to Java executable, for example:  

3.  <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>UCONFSET id=cft.jre.java_binary_path ,value=/bin/java</td>
    </tr>
    </tbody>
    </table>

## Configure Transfer CFT objects

### Createa CFTNET object

1.  Create a CFTNET object where:
    -   TYPE= TCP
    -   protocol value = SR
2.  Define the mandatory parameters RECALLHOST and SSLTERM.
    -   RECALLHOST: The host address on which the Master Agent calls Transfer CFT when Secure Relay receives an incoming call. If Transfer CFT and the Master Agent run of the same host, use the loopback network interface (for example, 127.0.0.1) instead of the public network interface. When using Secure Relay, the HOST parameter designates the network interface that is used on the Router Agent side.
    -   SSLTERM: Set this Boolean to YES to enable SSL termination.
3.  If there is existing CFTNET object(s), the class parameter must be different.

Example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTNET ID = NETSR,</p>
<p>PROTOCOL = SR,</p>
<p>TYPE = TCP,</p>
<p>CALL = INOUT,</p>
<p>CLASS = 1,</p>
<p>HOST = &lt;e.g. INADDR_ANY, network_interface_used_by_Router_Agent&gt;,</p>
<p>RECALLHOST = 127.0.0.1, /*network_interface_used_by_Transfer_CFT*/</p></td>
</tr>
</tbody>
</table>

## Create a CFTPROT object

This section describes the CFTPROT object, and how various parameters are related to enabling secure data transmission using Secure Relay.

-   CFTPROT is related to the CFTNET object through the NET parameter.
-   The SAP parameter is the listening port that is used on the RA side (using the CFTNET HOST parameter as the network interface).

Example

This example uses a CFTNET object called NETSR.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTPROT id = PESITANY,</p>
<p>net = NETSR,</p>
<p>sap = 1761,</p>
<p>Prot=PESIT,</p>
<p>prof = ANY</p></td>
</tr>
</tbody>
</table>

## Create CFTPART and CFTTCP objects

When a partner object refers to a CFTPROT object and a CFTNET object that use Secure Relay, it uses Secure Relay for both incoming and outgoing connections.

So to complete the configuration, create a CFTPART and a CFTTCP. In this way, the CFTPART refers to the CFTPROT object, and that in turn refers to a CFTNET, which points to Secure Relay.

Example

This is an example of the CFTPART and CFTTCP object configuration, using PESITANY.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTPART id = PARIS,</p>
<p> prot = PESITANY,</p>
<p> sap = &lt;remote_partner_sap&gt;,</p>
<p> nspart = NPHOENIX,</p>
<p>  nrpart = NPARIS,</p>
<p>  mode = replace</p>
<p> </p>
<p>CFTTCP id = PARIS,</p>
<p> class = 1, /* same class as the one used in the CFTNET */</p>
<p> host = &lt;remote_partner_host_address&gt;,</p>
<p> mode = replace</p></td>
</tr>
</tbody>
</table>

### Indicate a specific SecureRelay to use

If you would like to use a specific SecureRelay with a given partner, set the following parameter in the CFTPART:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>SRDMZ = &lt;UCONF secure_relay.ra.<em>n</em>.dmz value, where n is the number that corresponds to the SecureRelay to use&gt;</td>
</tr>
</tbody>
</table>
