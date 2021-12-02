{
    "title": "Transport  security in CFTSSL ",
    "linkTitle": "CFTSSL configuration",
    "weight": "180"
}<span id="Defining_a_transport_security_profile"></span>

## Defining a transport security profile

Transfer CFT opens an SSL session in client mode for any secure file
or message transfer in requester mode. Transfer CFT opens an SSL session
in server mode for any incoming call requiring a secure protocol.

The properties of each SSL session opened by Transfer CFT in both client
and server modes are determined by a security profile.

A security profile monitors the:

-   Required authentication
    mode: simple (server only) or mutual (server and client) authentication
-   Authentication,
    encryption and sealing algorithms to be used
-   Certificate to
    be sent for local authentication and the RSA authentication algorithm
-   Checks to be performed
    on the remote certificate for remote authentication and the RSA authentication
    algorithm

The CFTSSL command describes a security
profile. The DIRECT parameter indicates the mode to which the security
profile applies: DIRECT=CLIENT for client mode or DIRECT=SERVER for server
mode.

> **Note:**
>
> The Transfer CFT CFTSSL object in client mode is a dynamic object. However, when set to server mode this object is static (you must restart Transfer CFT for the value to be taken into account).

### Client mode SSL

### Server mode

### Associate the security profile with the CFTPROT object

The SSL parameter is used to associate a security profile with a protocol
definition.

-   For a security profile related to incoming calls (server mode), the
    SSL parameter value must correspond to the identifier of a DIRECT=SERVER
    SSL command.
-   For a default security profile related to outgoing calls (client mode),
    the SSL parameter value must correspond to the identifier of a DIRECT=CLIENT
    SSL command.

If you do not define the CFTPROT SAP parameter when using the SSL protocol,
then the server mode for CFTSSL is not mandatory.

Related topics

-   [CFTPROT](../../../admin_intro/admin_config_commands/transfer_protocol_concepts)
