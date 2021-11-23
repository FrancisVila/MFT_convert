{
    "title": "Using TLS",
    "linkTitle": "Using TLS",
    "weight": "220"
}{{< Gateway/componentlongname  >}}: Managing Security

[Installing TLS](#Installing_TLS)

[Configuring CGate objects for TLS](#Configuring_CGate_objects_for_TLS_use)

[Configuring Site objects for TLS use](#Configuring_Site_objects_for_TLS_use)

[TLS usage example](#TLS_usage_example)

<span id="Installing_TLS"></span>

## Installing TLS

To install TLS, select at least one TLS-enabled file transfer protocol when [configuring protocols](../../../../../gateway_userguide_(primary)/configuration_start_here/config_protocols_about/config_protocols).

<span id="Configuring_CGate_objects_for_TLS_use"></span>

## Configuring CGate objects for TLS

CGate (Connection Gate) objects are identification filters used internally in server mode at the protocol connection level. CGates determine whether a client has the right to connect to Gateway and exchange files with it or not. CGates can also determine if transport security must be implemented. Set the following parameters in the [CGate Security tab](../../../../../gateway_userguide_(primary)/managing_partners_start_here/cgates_start_here/working_with_cgates_and_cgategroups_(gui)#CGate_Security).

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadE-Column1-Header1">Possible values         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>TLS profile name</p>
<p>tls_sprof (-tlss)</p>         </td>
         <td><p>TLS Profile name.</p>
<p>This field can contain wildcards ('*' and '?').</p>         </td>
         <td><p>TLS Security Profile name used for the incoming call Handshake negotiation.</p>         </td>
      </tr>
      <tr>
         <td><p>TLS profile user parameter</p>
<p>tls_sprof_user_param (-tlssup)</p>         </td>
         <td><p>User parameter.</p>
<p>This field can contain wildcards ('*' and '?').</p>         </td>
         <td><p>User parameter that you can complete in the Security Profile definition.</p>         </td>
      </tr>
      <tr>
         <td><p>TLS Client Authentication</p>
<p>tls_client_auth (-tlscauth)</p>         </td>
         <td><p>Y | (N)</p>         </td>
         <td><p>Indicates whether authentication is required for the client trying to connect.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Configuring_Site_objects_for_TLS_use"></span>

## Configuring Site objects for TLS use

To use TLS, you must configure the Remote Site to use a TLS network security type. When you enable the TLS network security option for a Remote Site, you must set two parameters:

-   An outgoing Security Profile that is used to secure connections towards that Site
-   An incoming Security Profile that is used (if present) to check security of connections from that Site

The three TLS-specific parameters to set in the [Remote Site Net security tab](../../../../../gateway_userguide_(primary)/managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_net_security_tab) are:

-   **Network security option** (<span class="code">network\_security\_option</span> or<span class="code"> -nsopt</span>): set to TLS
-   <span style="font-weight: bold;">Security Profile for outgoing connection</span> (<span class="code">tls\_sprof\_out</span>): secures the outgoing connection
-   <span style="font-weight: bold;">Security Profile for incoming connection</span> (<span class="code">tls\_sprof\_in</span>): Incoming connections are first secured by selecting a Security Profile from the best Network Profile that matches the incoming connection parameters. Once the connected Site is known (at file transfer protocol level), a comparison is made between the session security parameters already used (from the network), and those of the session security parameters declared as the incoming Security Profile of the Site. If they do not match, the transfer is aborted and the connection is closed.

When a secured transfer is made, four pieces of information are added to the Transfer Request contained in the Mailbox:

-   Security Profile used (sprof)
-   Cipher suite used to encrypt connection
-   A client authentication indicator (<span style="font-weight: bold;">Yes</span> or <span style="font-weight: bold;">No</span>)
-   A server authentication indicator (<span style="font-weight: bold;">Yes</span> or <span style="font-weight: bold;">No</span>)

These parameters correspond to the last negotiated security parameters and are updated when necessary.

<span id="TLS_usage_example"></span>

## TLS usage example

To set up the TLS secured loop transfers:

1.  Enable the TLS option when [configuring protocols](../../../../../gateway_userguide_(primary)/configuration_start_here/config_protocols_about/config_protocols).

2.  Start Gateway and create basic loop configuration.

3.  Import the certificates:

    secadm import\_cert  -certificate\_name "SOPRACA"

       -certificate\_file "SopraCA.pem"

       –certificate\_file\_type BASE64

    secadm import\_cert  -certificate\_name "USER1"

       -certificate\_file "user1.p12"

       –certificate\_file\_type PKCS12

    secadm import\_cert  -certificate\_name "USER2"

       -certificate\_file "user2.p12"

       –certificate\_file\_type PKCS12

      
    These commands import three certificates:

    > -   <span style="font-weight: bold;">"SOPRACA" contained in the file "</span><span class="code" style="font-weight: bold;">SopraCA.pem</span><span style="font-weight: bold;">"</span>: The file, in this example, contains the BASE64 encoded certificate of the certification authority. This certificate has been used to sign the two others.
    > -   <span style="font-weight: bold;">"USER1" contained in the file "</span><span class="code" style="font-weight: bold;">user1.p12</span><span style="font-weight: bold;">"</span>: The file contains a PKCS12 structure that holds both the certificate and its asymmetrical key pair. Keys are encrypted using the password phrase "user1". Prompt for password occurs while importing.
    > -   <span style="font-weight: bold;">"USER2" contained in the file "</span><span class="code" style="font-weight: bold;">user2.p12</span><span style="font-weight: bold;">"</span>: Keys are encrypted using the password phrase "user2". Prompt for password occurs while importing.

4.  Import Security Profiles:

    > -   secadm import\_sprof  -sprof\_file "server.sprof"
    > -   secadm import\_sprof  -sprof\_file "client.sprof"

5.  The previous commands result in the creation of two Security Profiles:

    > -   "SRV\_SPROF" is used to secure incoming network connections. It sends the DN of "SOPRACA" as the accepted authority and "USER1" as the certificate.
    > -   "CLT\_SPROF" is used to secure outgoing connections. It sends "USER2" as the certificate (a check is made to ensure "USER2" is signed by "SOPRACA").

6.  Create Network Profiles (for the incoming connection).

    secadm create\_netprof  –nprof\_name SEC\_NETPROF

       -origin\_address "\*/\*"  –destination\_address "\*/2205"

       –tls\_option Y  –sprof\_name "SRV\_SPROF"

    secadm create\_netprof  –nprof\_name DEFAULT\_NETPROF

       -origin\_address "\*/\*"  –destination\_address "\*/\*"  –tls\_option N

      
    These commands create two Network Profiles:

    > -   "SEC\_NETPROF" that enables TLS with the Security Profile "SRV\_SPROF" for any incoming TCP/IP connection on port 2205
    > -   "DEFAULT\_NETPROF" that accepts every connection as non-secured (it matches any distant address with any distant SAP and any local address with any SAP)

7.  Configure every Remote Site that points to your Gateway address with an SAP of 2205 with the following options:

    > -   network\_security\_option TLS
    > -   tls\_sprof\_in "SRV\_SPROF"
    > -   tls\_sprof\_out "CLT\_SPROF"

8.  Process a file transfer toward one of the Sites configured in the previous step.

Related topics

<a href="../tls_cipher_suites" class="MCXref xref">TLS cipher suites</a>

<a href="../managing_tls" class="MCXref xref">Managing TLS</a>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
