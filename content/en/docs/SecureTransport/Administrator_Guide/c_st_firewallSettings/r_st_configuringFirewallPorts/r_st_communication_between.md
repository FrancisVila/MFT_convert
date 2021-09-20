{
    "title": "Communication between SecureTransport Server and SecureTransport Edge",
    "linkTitle": "Communication between SecureTransport Server and SecureTransport Edge",
    "weight": "310"
}These port must be open between the private network and the peripheral network (DMZ) for the Transaction Manager Server on SecureTransport Server to connect to the protocol servers on SecureTransport Edge. The protocol is the SecureTransport secure streaming protocol.

-   20021 – FTP Server
-   20022 – SSH Server
-   20080 – HTTP Server
-   20444 – Administration Tool server
-   21080 – AS2 Server
-   27617 – PeSIT Server

**Related topics:**

-   [Communication between the outside and SecureTransport Edge](../r_st_communication_between_outside)
-   [Communication between SecureTransport Server and an internal network](../r_st_communication_between_server_internal_network)
-   [Internal SecureTransport communication](../r_st_internal_communication)
