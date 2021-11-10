{
    "title": "Address Book",
    "linkTitle": "Address Book",
    "weight": "300"
}{
"title": "Configure SecureTransport Back End to Edge streaming communication",
"linkTitle": "Configure SecureTransport Back End to Edge streaming communication",
"weight": "290"
}The Edge to Back End server communication utilizes Network Zones that allows one or multiple Edge servers to be grouped in a "zone" that all inbound and outbound communications will go through. The existence of several zones provides the opportunity to have multiple peripheral networks (for example, one for intranet and one for internet traffic). Additionally, the communications are entirely outbound from Back End perspective. That means that no inbound ports in the firewall placed in between the Edge and Back End need to be opened for communication between the Edge and Back End.
To configure streaming communications between the Edge and Back End server, take the following steps:
1. Exchange the Internal CA certificates of the Edge(s) and the Back End(s). To exchange CA certificates of a Back End and Edge, the CA certificate of the Back End should be exported and imported on the Edge and the CA certificate of the Edge should be exported and imported on the Back End. For additional information, refer to <a href="" class="MCXref xref">Manage trusted CAs</a>.
1. On the Back End, select \*\*Setup &gt; Certificates\*\*.
2. Click the \*\*Trusted CAs\*\* tab.
3. Navigate to the page that lists the certificate labeled \*ca\*.
4. Click the alias of the CA certificate.
5. Click \*\*Export\*\* and save the certificate file in the desired location.
6. On the Edge, select \*\*Setup &gt; Certificates\*\*.
7. Click the \*\*Trusted CAs\*\* tab.
8. Click \*\*Import\*\*.
9. Browse and select the CA certificate exported from the Back End.
10. Enter an alias for the CA certificate. For example, enter \*\*ca\\\_be\*\* for the certificate exported from the Back End imported into the Edge and \*\*ca\\\_edge\*\* for certificate exported from the Edge and imported into the Back End.
11. \*\*Note:\*\*
&gt;
&gt; Do not over write the Edge or Back End CA certificate with imported certificate.
12. Click \*\*Import\*\*.
13. Follow the Steps a to k in the opposite direction in order to export the internal CA of the Edge and import it on the Back End.
\*\*On the Back End:\*\*
2. Generate a self-issued local certificate server that will only be used for streaming communications. For additional information, refer to <a href="#Generate" class="MCXref xref">Generate a self-issued server certificate</a>.
3. Search for and configure the \`Streaming.TrustedAliases\` parameter with the alias of the CA certificate of the Edge that was imported. For information on searching for configuration parameters, refer to <a href="#Search" class="MCXref xref">Search for a parameter</a>. For information on changing configuration parameters, refer to <a href="#Change" class="MCXref xref">Change a parameter value</a>.
4. Add a new zone on the Back End for the Edge. For additional network zone configuration information, refer to <a href="#Specify4" class="MCXref xref">Manage the communication across Transaction Manager, protocol and proxy servers</a>
&gt; \*\*Note:\*\*
&gt;
&gt; The Private zone on the Back End should not be modified.
5. Enter a Title, Description, and Notes. In the \*Streaming Configuration\* pane, select the protocols which should be used for the streaming communications. Enter the port number of each selected protocol. The Back End will connect to the Edge to establish the streaming connections using these ports. The streaming connections are established in outbound direction - from Back End to Edge. The port numbers must match between the Back End and the Edge. For each selected protocol, select the alias of the certificate generated in Step 2 for the \*\*SSL Key Alias\*\*. Additionally, the streaming port numbers and certificate alias must be different from port numbers and certificates used for server control. Add the IP address of the Edge in \*Addresses\* pane.
&gt; \*\*Note:\*\*
&gt;
&gt; ADMIN must be selected whenever another streaming protocol is selected. The ADMIN protocol is used for internal functions like DNS resolving and DNS reverse lookups (Server.ReverseDNSLookups). For additional information refer, to Enable or disable reverse DNS lookups.
\*\*On the Edge:\*\*
6. Generate a self-issued local certificate server that will only be used for streaming communications. For additional information, refer to <a href="#Generate" class="MCXref xref">Generate a self-issued server certificate</a>.
7. Edit the Network Zone node and change the default \*\*localhost\*\* to the IP address of the Edge server itself. To edit the Network Zone node, select the alias of the Network Zone from the \*Network Zone List\* and then select the Node from the \*Node List\*. For additional configuration information, refer to <a href="#Create" class="MCXref xref">Create a network zone to define communications with SecureTransport Edge servers</a>.
&gt; \*\*Note:\*\*
&gt;
&gt; ADMIN must be selected whenever another streaming protocol is selected. The ADMIN protocol is used for internal functions like DNS resolving and DNS reverse lookups (Server.ReverseDNSLookups). For additional information refer, to Enable or disable reverse DNS lookups.
8. Verify that the ports for the services (FTP, HTTP, etc.) are the same and match the ports, configured for the same zone on the Back End. For each protocol, select the alias of the certificate generated in Step 6 for the \*\*SSL Key Alias\*\*.
9. Search for and configure the \`Streaming.TrustedAliases\` parameter with the alias of the CA certificate of the Back End that was imported. For information on searching for configuration parameters, refer to <a href="#Search" class="MCXref xref">Search for a parameter</a>. For information on changing configuration parameters, refer to <a href="#Change" class="MCXref xref">Change a parameter value</a>.
10. For the streaming communication configuration to take effect, restart all of the services (\`stop\_all\`/\`start\_all\`) on both Back End and the Edge.
11. Wait for at least 2 minutes for Transaction Manager to connect to the Edge. You should have a streaming communications up and running once Transaction is connected to the Edge. Successful streaming communications can be verified with server log messages which contain "Established streaming connection".
To test Client Initiated Transfers, try to login using the address of the Edge.
