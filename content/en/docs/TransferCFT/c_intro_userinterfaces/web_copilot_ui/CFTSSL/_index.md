{
    "title": "Security",
    "linkTitle": "Security",
    "weight": "180"
}The CFTSSL object describes a security
profile. The DIRECT parameter indicates the mode to which the security
profile applies: DIRECT=CLIENT for client mode or DIRECT=SERVER for server
mode.

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

See [Transport
security in CFTSSL](../../../transport_security_start_here/configuring_transport_security_start_here/transport_security_cftssl) for a description of available parameters.