{
    "title": "Configure SecureTransport Back End to Edge streaming communication",
    "linkTitle": "Configure SecureTransport Back End to Edge streaming communication",
    "weight": "300"
}The Edge to Back End server communication utilizes Network Zones that allows one or multiple Edge servers to be grouped in a "zone" that all inbound and outbound communications will go through. The existence of several zones provides the opportunity to have multiple peripheral networks (for example, one for intranet and one for internet traffic). Additionally, the communications are entirely outbound from Back End perspective. That means that no inbound ports in the firewall placed in between the Edge and Back End need to be opened for communication between the Edge and Back End.

To configure streaming communications between the Edge and Back End server, take the following steps:

1.  Exchange the Internal CA certificates of the Edge(s) and the Back End(s). To exchange CA certificates of a Back End and Edge, the CA certificate of the Back End should be exported and imported on the Edge and the CA certificate of the Edge should be exported and imported on the Back End. For additional information, refer to [Manage trusted CAs](../c_st_certificates/t_st_trustedcas).
    1.  On the Back End, select **Setup > Certificates**.

    2.  Click the **Trusted CAs** tab.

    3.  Navigate to the page that lists the certificate labeled *ca*.

    4.  Click the alias of the CA certificate.

    5.  Click **Export** and save the certificate file in the desired location.

    6.  On the Edge, select **Setup > Certificates**.

    7.  Click the **Trusted CAs** tab.

    8.  Click **Import**.

    9.  Browse and select the CA certificate exported from the Back End.

    10. Enter an alias for the CA certificate. For example, enter **ca\_be** for the certificate exported from the Back End imported into the Edge and **ca\_edge** for certificate exported from the Edge and imported into the Back End.

    11. <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Do not over write the Edge or Back End CA certificate with imported certificate.         </td>      </tr></table>

    12. Click **Import**.

    13. Follow the Steps a to k in the opposite direction in order to export the internal CA of the Edge and import it on the Back End.

      
    **On the Back End:**

2.  Generate a self-issued local certificate server that will only be used for streaming communications. For additional information, refer to [Generate a self-issued server certificate](../c_st_certificates/t_st_localcertificatesandcsrs).

3.  Search for and configure the `Streaming.TrustedAliases` parameter with the alias of the CA certificate of the Edge that was imported. For information on searching for configuration parameters, refer to [Search for a parameter](../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters). For information on changing configuration parameters, refer to [Change a parameter value](../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters).

4.  Add a new zone on the Back End for the Edge. For additional network zone configuration information, refer to [Manage the communication across Transaction Manager, protocol and proxy servers](../c_st_networkzones/t_st_networkzones)  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The Private zone on the Back End should not be modified.         </td>
      </tr>
</table>

5.  Enter a Title, Description, and Notes. In the *Streaming Configuration* pane, select the protocols which should be used for the streaming communications. Enter the port number of each selected protocol. The Back End will connect to the Edge to establish the streaming connections using these ports. The streaming connections are established in outbound direction - from Back End to Edge. The port numbers must match between the Back End and the Edge. For each selected protocol, select the alias of the certificate generated in Step 2 for the **SSL Key Alias**. Additionally, the streaming port numbers and certificate alias must be different from port numbers and certificates used for server control. Add the IP address of the Edge in *Addresses* pane.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><strong>ADMIN</strong> must be selected whenever another streaming protocol is selected. The ADMIN protocol is used for internal functions like DNS resolving and  DNS reverse lookups (<code>Server.ReverseDNSLookups</code>).  For additional information refer, to <a href="../c_st_miscellaneousconfiguration/t_st_miscellaneousoptions" xrefformat="{paratext}">Enable or disable reverse DNS lookups</a>.         </td>
      </tr>
</table>

      
    **On the Edge:**

6.  Generate a self-issued local certificate server that will only be used for streaming communications. For additional information, refer to [Generate a self-issued server certificate](../c_st_certificates/t_st_localcertificatesandcsrs).

7.  Edit the Network Zone node and change the default **localhost** to the IP address of the Edge server itself. To edit the Network Zone node, select the alias of the Network Zone from the *Network Zone List* and then select the Node from the *Node List*. For additional configuration information, refer to [Create a network zone to define communications with SecureTransport Edge servers](../c_st_networkzones/t_st_networkzones).  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><strong>ADMIN</strong> must be selected whenever another streaming protocol is selected. The ADMIN protocol is used for internal functions like DNS resolving and  DNS reverse lookups (<code>Server.ReverseDNSLookups</code>).  For additional information refer, to <a href="../c_st_miscellaneousconfiguration/t_st_miscellaneousoptions" xrefformat="{paratext}">Enable or disable reverse DNS lookups</a>.         </td>
      </tr>
</table>

8.  Verify that the ports for the services (FTP, HTTP, etc.) are the same and match the ports, configured for the same zone on the Back End. For each protocol, select the alias of the certificate generated in Step 6 for the **SSL Key Alias**.

9.  Search for and configure the `Streaming.TrustedAliases` parameter with the alias of the CA certificate of the Back End that was imported. For information on searching for configuration parameters, refer to [Search for a parameter](../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters). For information on changing configuration parameters, refer to [Change a parameter value](../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters).

10. For the streaming communication configuration to take effect, restart all of the services (`stop_all`/`start_all`) on both Back End and the Edge.

11. Wait for at least 2 minutes for Transaction Manager to connect to the Edge. You should have a streaming communications up and running once Transaction is connected to the Edge. Successful streaming communications can be verified with server log messages which contain "Established streaming connection".

To test Client Initiated Transfers, try to login using the address of the Edge.
