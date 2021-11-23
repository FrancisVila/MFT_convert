{
    "title": "SSH protocol",
    "linkTitle": "SSH",
    "weight": "180"
}{{< Gateway/componentlongname  >}}: Managing Security

[About SSH protocol](#About_SSH_protocol)

[Establishing an SSH connection](#Establishing_an_SSH_connection)

[Establishing security with SSH](#Establishing_security_with_SSH)

[Checking the login\_user](#Checking_the_login_user)

[Using SSH with SFTP](#Using_SSH_with_SFTP)

[SSH renegotiation](#ssh_renegotiation)

<span id="About_SSH_protocol"></span>

## About SSH protocol

**SSH** (<span style="font-weight: bold;">S</span>ecure <span style="font-weight: bold;">Sh</span>ell) was created by SSH Communications Security Inc. ([www.ssh.com](http://www.ssh.com/)) to provide secure login over an insecure network. The SSH2 protocol is being standardized by the Secsh Working Group of the Internet Engineering Task Force (IETF).

SSH provides the following services:

-   [Authentication](../../../security_features/ov_gw_security_features#Authentication)
-   [Integrity](../../../security_features/ov_gw_security_features#Integrity)
-   [Confidentiality](../../../security_features/ov_gw_security_features#Privacy)

These services are performed on three communication layers, as defined in the SSH RFC:

-   Transport Layer Protocol (TLP) layer
-   User Authentication Protocol (UAP) layer
-   Connection Protocol (CP) layer

The Transport Layer Protocol and User Authentication Protocol allow you to establish the secure tunnel (via authentication, encryption and hash comparison).

The Connection protocol layer relies on the other two layers. It allows you to open one or several channels (multiplexing) above the first two layers, and controls the data flow.

<span id="Establishing_an_SSH_connection"></span>

## Establishing an SSH connection

SSH is a protocol based on mutual authentication. The client authenticates the server and the server authenticates the client so that both parties are assured of the identity of the other party.

To establish an SSH connection, the client must have server identification details (obtained by a method external to SSH). If the server authentication is by certificate, the client must have the certificate of the certification authority that issued the certificate and the certificate path (all the certificates up to the root).

For a successful connection, the server must also have the following client authentication parameters:

-   Client name
-   Authentication parameters (key, certificate or password) depending on negotiated authentication method

The connection procedure:

-   Sets up Transport Layer Protocol: Negotiation of encryption methods and integrity check (authentication of server)
-   Negotiates authentication method
-   Authenticates the client

When both the server and client are authenticated, the secured channel is open and you can begin transferring files.

<span id="Establishing_security_with_SSH"></span>

## Establishing security with SSH

### Incoming connection

Following the connection, the network sends the session initialization parameters to the Security server. For incoming connections, network parameters are used to retrieve a Network Profile object.

If the security option is set to SSH, the Network Profile indicates the SSH Profile to use.

The following diagram schematically illustrates Gateway implementation of an incoming SSH call:

<img src="/Images/Gateway/SSH_IncomingCall.png" class="maxWidth" />

### Outgoing connection

The Remote Site parameter <span class="code" style="font-weight: bold;">sshprof\_out</span> indicates which SSH Security Profile to use for the outgoing connection.

The following diagram schematically illustrates a Gateway implementation of an outgoing SSH call:

<img src="/Images/Gateway/SSH_OutgoingCall.png" class="mediumWidth" />

<span id="Checking_the_login_user"></span>

## Checking the login\_user

If Gateway successfully identifies a Network Profile to use for an incoming connection, it then uses the <span class="code" style="font-weight: bold;">login\_user</span> parameter to identify a CGate. A Remote Site template is defined in the CGateGroup. The authentication control parameters of the partner are found in the Remote Site.

<span id="Using_SSH_with_SFTP"></span>

## Using SSH with SFTP

SSH is only used with the SSH File Transfer Protocol (SFTP). SFTP has no integral identification mechanism and therefore relies on the SSH protocol for user authentication and a secure connection.

The two protocols are separate and technically different, but are exclusively used together in Gateway.

The configuration of an SFTP/SSH link requires the configuration of several compatible objects in Gateway:

-   [Remote Site](../../../../gateway_userguide_(primary)/managing_partners_start_here/sites_start_here/managing_remote_sites)
-   [Network Profile (netprof) object](../network_profiles_start_here/network_profiles_(gui))
-   [SSH Profile (sshprof) object](ssh_security_profiles__gui_)

In the SSH Profile object you must define a **key exchange algorithm** and a **DSS**, **ECDSA** or **RSA** key (or an **X.509** certificate).

The SFTP layer is above the three protocol layers used by SSH (TLP, UAP and CP).

Channel management is necessary, but typically SFTP does not need several channels, because it is simpler to open several requests in parallel within one unique channel. Opening the channels occurs on the initiative of the client.

Gateway supports SFTP in both client and server modes.

<span id="ssh_renegotiation"></span>

## SSH renegotiation

SSH renegotiation is the renewal of the encryption keys, authentication, and compression during an SSH session. The term <span style="font-style: italic;">renegotiation</span> is used because the protocol initiates at that moment a real negotiation between the client and the server about the choice of encryption, authentication and compression algorithms to be used for the continuation of the session.

SSH makes it possible to establish a secure channel between two computers allowing the remote control of one of the computers, file transfer, and so on. The world of Internet has realized that even though SSH offers a very high level of security, it is theoretically possible for a hacker to crack the keys and intercept the communication. To be able to do that a hacker needs a certain volume of data and/or time. Nowadays it is therefore recommended to change encryption keys after transferring 1 GB of data or after one hour, whichever occurs first.

### Response to a key change request

Without the need to set any parameters, Gateway automatically responds to key change requests originating from a third party (server or client).

### Initiation of a key change

Gateway can initiate a key change renegotiation. The behavior depends on the values of two parameters set in the SSH Security Profile:

-   <span style="font-weight: bold;">Minutes before New Keys</span> - the time period after which Gateway initiates an SSH renegotiation
-   <span style="font-weight: bold;">MB before New Keys</span> - the data volume transmitted in one direction after which Gateway initiates an SSH renegotiation

Gateway initiates key renegotiation when either of these two limits is reached.

To set these parameters, refer to [Managing SSH Security Profiles](ssh_security_profiles__gui_#key_renegotiation).

Related topics

[Managing Keys and Certificates in SSH](managing_keys_and_certificates_in_ssh)

[Using SSH](using_ssh)

[Managing SSH Security Profiles](ssh_security_profiles__gui_)

[SSH authentication](ssh_authentication)

[Managing SSH Security Profiles (command line)](managing_ssh_security_profiles_cli)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
