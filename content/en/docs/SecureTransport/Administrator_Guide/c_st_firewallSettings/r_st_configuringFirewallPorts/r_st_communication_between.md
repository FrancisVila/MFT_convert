{
    "title": "Communication between SecureTransport Server and SecureTransport Edge",
    "linkTitle": "Communication between SecureTransport Server and SecureTransport Edge",
    "weight": "300"
}These port must be open between the private network and the peripheral network (DMZ) for the Transaction Manager Server on <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server to connect to the protocol servers on <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge. The protocol is the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> secure streaming protocol.

-   20021 – FTP Server
-   20022 – SSH Server
-   20080 – HTTP Server
-   20444 – Administration Tool server
-   21080 – AS2 Server
-   27617 – PeSIT Server

**Related topics:**

-   <a href="../r_st_communication_between_outside" class="MCXref xref">Communication between the outside and SecureTransport Edge</a>
-   <a href="../r_st_communication_between_server_internal_network" class="MCXref xref">Communication between SecureTransport Server and an internal network</a>
-   <a href="../r_st_internal_communication" class="MCXref xref">Internal SecureTransport communication</a>
