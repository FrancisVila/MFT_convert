{
    "title": "Configure exchanges that use SSL",
    "linkTitle": "Configure exchanges that use SSL",
    "weight": "270"
}There are two ways to configure Transfer CFT with Secure Relay using the TLS protocol:

-   End-to-end SSL: The remote peer communicates with Transfer CFT via Secure Relay (RA) using end-to-end SSL.
-   SSL termination: The remote peer communicates with Secure Relay (RA) through an SSL channel. In this scenario, the handshake occurs between the remote peer and the Secure Relay RA. The RA retrieves the key and certificate stored in Transfer CFT through the Master Agent (MA) in order to complete the handshake.

The communication between the Master Agent (MA) and Transfer CFT occurs over a plain-text channel.

End-to-end SSL compared with SSL termination

![](/Images/TransferCFT/sr_schema.png)

This page describes how to create and configure the following Transfer CFT objects to enable SSL exchanges using Secure Relay:

-   Network object CFTNET
-   Protocol object CFTPROT
-   Security object CFTSSL
-   Partner objects CFTPART and CFTTCP

SSL termination in Secure Relay is possible using the internal PKI database. As such, the internal PKI base (pki.type=cft), rootcid, and usercid correspond to certificates stored in the internal PKI database.

## End-to-end SSL

### Create a CFTNET object

1.  Create a CFTNET object where:
    -   TYPE=TCP
    -   PROTOCOL=SR
2.  Define the mandatory parameters RECALLHOST, HOST, and SSLTERM.
    -   RECALLHOST: The host address on which the Master Agent calls Transfer CFT when Secure Relay receives an incoming call. If Transfer CFT and the Master Agent run of the same host, use the loopback network interface (for example, 127.0.0.1) instead of the public network interface.
    -   HOST: Designates the network interface that is used on the Router Agent side.
    -   SSLTERM: Set this Boolean to NO for end-to-end SSL.

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTNET id = NETSRSSL,</p>
<div>
            <p>type = TCP,</p>
            <p>call = INOUT,</p>
            <p>class = 2,</p>
            <p>host = &lt;network_interface_used_by_Router_Agent&gt;,</p>
            <p>protocol = SR,</p>
            <p>recallhost = 127.0.0.1, /*network_interface_used_by_CFT*/</p>
            <p>sslterm = NO</p>
</div>         </td>
      </tr>
   </tbody>
</table>

### Create a CFTPROT object

This section describes the CFTPROT object, and how various parameters are related to enabling secure data transmission using Secure Relay.

-   CFTPROT is linked to the CFTNET object through the NET parameter.
-   The SAP parameter is the listening port that is used on the RA side (using the CFTNET HOST parameter as the network interface).
-   The CFTPROT SSL parameter refers to a CFTSSL object, in this case PESITSSL, which is used when Secure Relay performs SSL termination in server mode.

Example

This example uses a CFTNET object called NETSRSSL.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTPROT id = PESITSSL,</p>
<div>
            <p>net = NETSRSSL,</p>
            <p>sap = 1762,</p>
            <p>ssl = PESITSSL,</p>
            <p>prof = ANY</p>
</div>         </td>
      </tr>
   </tbody>
</table>

### Create a CFTSSL object

Create a CFTSSL object to supply detailed information to Secure Relay on how the SSL termination should be done. Secure Relay only supports the SSL version TLSV1COMP.

-   Secure Relay uses the CFTSSL parameters rootcid, usercid and its password, cipher suites list, SSL version and client authentication policy.
-   Secure relay uses a restricted list of cipher suites (cipher suites ‘59’, ‘60’ and ’61 are not supported).

Example

Here the CFTSSL object is used for incoming connections (direct=server).

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTSSL id = PESITSSL,</p>
<div>
            <p>version = TLSV1COMP,</p>
            <p>direct = SERVER,</p>
            <p>verify = NONE,</p>
            <p>usercid = AXWMFTUSER,</p>
            <p>rootcid = AXWMFTCA,</p>
            <p>ciphlist = (47),</p>
            <p>passw = &lt;user_cid_password&gt;
<strong>NOTE</strong>: You must enter a value in this field even if you are using "pki.type=cft", which normally does not require a password.</p>
</div>
            <p> </p>         </td>
      </tr>
   </tbody>
</table>

Here the CFTSSL object is used for incoming connections (direct=client).

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTSSL id = PESITSSL,</p>
<div>
            <p>version = TLSV1COMP,</p>
            <p>direct = CLIENT,</p>
            <p>rootcid = AXWMFTCA,</p>
            <p>ciphlist = (47)</p>
</div>         </td>
      </tr>
   </tbody>
</table>

### Create CFTPART and CFTTCP objects

A partner object that refers to a CFTPROT and a CFTNET and that uses Secure Relay, uses Secure Relay for both incoming and outgoing connections.

SSL termination is also used for outgoing connections when the CFTNET object associated with the partner has its SSLTERM parameter set to **NO**. In this case the CFTSSL used will be in priority the one defined in partner (SSL parameter) or, if empty, the CFTSSL object of type client that have the same name as the one defined in the CFTPROT object.

To complete the configuration, create a CFTPART object and a CFTTCP object. In this way the CFTPART refers to the CFTPROT object, and that in turn refers to a CFTNET, which points to Secure Relay. Remember that the only SSL version supported by Secure Relay is TLSV1COMP.

Example

This is an example of the CFTPART and CFTTCP objects configuration, using PESITSSL.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTPART id = PARIS_SSL,</p>
            <p>prot = PESITSSL,</p>
            <p>sap = &lt;remote_partner_sap&gt;,</p>
            <p>nspart = NPARIS_SSL,</p>
            <p>nrpart = NPHOENIX_SSL</p>
            <p> </p>
            <p>CFTTCP id = PARIS_SSL,</p>
            <p>class = 2, /* the same class as the one used in the CFTNET */</p>
            <p>host = &lt;remote_partner_host_address&gt;</p>         </td>
      </tr>
   </tbody>
</table>

### How to enable Secure Relay FIPS mode

#### Prerequisites

-   You require an installed Secure Relay Router Agent 2.7.3 that has a license for FIPS mode. Please refer to the *Secure Relay Router Agent 2.7.3 documentation* at [docs.axway.com](https://docs.axway.com/bundle) for more information.
-   Your Transfer CFT license key requires the FIPS option.

#### Configure the Master Agent in Transfer CFT

1.  Go to the in the` $CFTDIRINSTALL/distrib/xsr/` folder, and rename the iaik\_jce-3.16.jar file as `iaik_jce-3.16.unused.`
2.  Move the entrust-toolkit-8.0.36.jar file from the $CFTDIRINSTALL/distrib/xsr/fips folder to the $CFTDIRINSTALL/distrib/xsr/ folder.

## SSL termination with Secure Relay

### Create a CFTNET object

1.  Create a CFTNET object where:
    -   TYPE=TCP
    -   PROTOCOL=SR
2.  Define the mandatory parameters RECALLHOST, HOST, and SSLTERM.
    -   RECALLHOST: The host address on which the Master Agent calls Transfer CFT when Secure Relay receives an incoming call. If Transfer CFT and the Master Agent run of the same host, use the loopback network interface (for example, 127.0.0.1) instead of the public network interface.
    -   HOST: Designates the network interface that is used on the Router Agent side.
    -   SSLTERM: Set this Boolean to YES to enable SSL termination.

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTNET id = NETSRSSL,</p>
<div>
            <p>type = TCP,</p>
            <p>call = INOUT,</p>
            <p>class = 2,</p>
            <p>host = &lt;network_interface_used_by_Router_Agent&gt;,</p>
            <p>protocol = SR,</p>
            <p>recallhost = 127.0.0.1, /*network_interface_used_by_CFT*/</p>
            <p>sslterm = YES</p>
</div>         </td>
      </tr>
   </tbody>
</table>

### Create a CFTPROT object

This section describes the CFTPROT object, and how various parameters are related to enabling secure data transmission using Secure Relay.

-   CFTPROT is linked to the CFTNET object through the NET parameter.
-   The SAP parameter is the listening port that is used on the RA side (using the CFTNET HOST parameter as the network interface).
-   The CFTPROT SSL parameter refers to a CFTSSL object, in this case PESITSSL, which is used when Secure Relay performs SSL termination in server mode.

Example

This example uses a CFTNET object called NETSRSSL.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTPROT id = PESITSSL,</p>
<div>
            <p>net = NETSRSSL,</p>
            <p>sap = 1762,</p>
            <p>ssl = PESITSSL,</p>
            <p>prof = ANY</p>
</div>         </td>
      </tr>
   </tbody>
</table>

### Create a CFTSSL object

Create a CFTSSL object to supply detailed information to Secure Relay on how the SSL termination should be done. Secure Relay only supports the SSL version TLSV1COMP.

-   Secure Relay uses the CFTSSL parameters rootcid, usercid and its password, cipher suites list, SSL version and client authentication policy.
-   Secure relay uses a restricted list of cipher suites (cipher suites ‘59’, ‘60’ and ’61 are not supported).

Example

Here the CFTSSL object is used for incoming connections (direct=server).

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTSSL id = PESITSSL,</p>
<div>
            <p>version = TLSV1COMP,</p>
            <p>direct = SERVER,</p>
            <p>verify = NONE,</p>
            <p>usercid = AXWMFTUSER,</p>
            <p>rootcid = AXWMFTCA,</p>
            <p>ciphlist = (47),</p>
            <p>passw = &lt;user_cid_password&gt;
<strong>NOTE</strong>: You must enter a value in this field even if you are using "pki.type=cft", which normally does not require a password.</p>
</div>
            <p> </p>         </td>
      </tr>
   </tbody>
</table>

Here the CFTSSL object is used for incoming connections (direct=client).

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTSSL id = PESITSSL,</p>
<div>
            <p>version = TLSV1COMP,</p>
            <p>direct = CLIENT,</p>
            <p>rootcid = AXWMFTCA,</p>
            <p>ciphlist = (47)</p>
</div>         </td>
      </tr>
   </tbody>
</table>

### Create CFTPART and CFTTCP objects

A partner object that refers to a CFTPROT and a CFTNET and that uses Secure Relay, uses Secure Relay for both incoming and outgoing connections.

SSL termination is also used for outgoing connections when the CFTNET object associated with the partner has its SSLTERM parameter set to **YES**. In this case the CFTSSL used will be in priority the one defined in partner (SSL parameter) or, if empty, the CFTSSL object of type client that have the same name as the one defined in the CFTPROT object.

To complete the configuration, create a CFTPART object and a CFTTCP object. In this way the CFTPART refers to the CFTPROT object, and that in turn refers to a CFTNET, which points to Secure Relay. Remember that the only SSL version supported by Secure Relay is TLSV1COMP.

Example

This is an example of the CFTPART and CFTTCP objects configuration, using PESITSSL.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTPART id = PARIS_SSL,</p>
            <p>prot = PESITSSL,</p>
            <p>sap = &lt;remote_partner_sap&gt;,</p>
            <p>nspart = NPARIS_SSL,</p>
            <p>nrpart = NPHOENIX_SSL</p>
            <p> </p>
            <p>CFTTCP id = PARIS_SSL,</p>
            <p>class = 2, /* the same class as the one used in the CFTNET */</p>
            <p>host = &lt;remote_partner_host_address&gt;</p>         </td>
      </tr>
   </tbody>
</table>
