{
    "title": "Security features in depth",
    "linkTitle": "Security features in depth",
    "weight": "190"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Overview

Gateway includes a set of security features whose principal purpose is to protect the data stored and transferred over your network. This topic introduces basic security concepts and describes security implementation in Gateway.

<span id="concepts"></span>

## Security concepts

File transfer security relies on three basic concepts:

-   [Privacy](#Privacy)
-   [Integrity](#Integrity)
-   [Authentication](#Authentication)

Although these three concepts are independent, they must be combined to achieve a high level of security.

<span id="Privacy"></span>

### Privacy

<span style="font-style: italic;">Privacy</span> (also referred to as <span style="font-style: italic;">confidentiality</span>) involves protecting access to data. Privacy prevents third parties from accessing data that is not intended for them. Typically, data is made confidential through <span style="font-style: italic;">encryption</span>.

Two cryptographic techniques are often used and combined:

-   <span style="font-weight: bold;">Symmetrical encryption</span>: uses a unique key to encrypt and decrypt a message. Both connected parties share a key that they use to encrypt and decrypt data. The task of privately choosing the key before encrypting data is more problematic, since the connected parties share a single key that they cannot easily exchange.
-   <span style="font-weight: bold;">Asymmetrical encryption</span>: uses a pair of keys, where each key can decrypt messages encrypted using the other key. This technique solves the problem of exchanging the key between connected parties. When two parties want to communicate using this encryption mechanism, each party publishes one of its keys and keeps the other one secret.

SSL or TLS protocols use a symmetric encryption mechanism to encrypt data (DES, triple DES, RC4, and AES). This mechanism generates a key for each session and exchanges this key during the handshake phase. They are transmitted using an asymmetrical encryption mechanism, which is slower but more secure (RSA) than a symmetric encryption mechanism.

<span id="Integrity"></span>

### Integrity

Integrity consists in ensuring that the received data has not been modified. Typically, integrity verification requires adding an abstract data to the data that you send. On receiving a message, the receiver makes an abstract of the message and compares it with the abstract sent with the message. If the abstracts match, message integrity is assumed to be valid. Otherwise, it is not.

The message abstract is referred to as the <span style="font-style: italic;">message digest</span> or the <span style="font-style: italic;">hash code</span>. The procedure used to create the hash code is referred to as either the <span style="font-style: italic;">digest function</span> or the <span style="font-style: italic;">hash function</span>.

When you use SSL/TLS or SSH, a hash code, referred to as <span style="font-weight: bold;">MAC</span> (Message Authentication Code), is added to each message sent. The standard hash functions are <span style="font-weight: bold;">SHA-1</span> or <span style="font-weight: bold;">MD5</span>.

<span id="Authentication"></span>

### Authentication

Authentication is the process of verifying a claimed identity. The most widely used authentication mechanisms are:

-   Password request
-   Proof request

<span style="font-weight: bold;">Password requests</span> are associated with user login requests. When the user sends a login name, the password request is displayed.

<span style="font-weight: bold;">Proof requests</span> are associated with asymmetrical encryption mechanisms. The user sends the public key (or any information relevant enough to get the public key, such as a certificate), and then receives a random encrypted message. To decrypt the message, the user must own the unique private key associated with the public key. This means that if the user can decrypt the message, the user identity is authenticated.

When using TLS and SSL protocols, the client encrypts the symmetrical key with the public key for the server. If the server can decrypt the key, the client is as claimed. Otherwise, dialog is not possible and the connection is closed. When requested, the server uses a signature process to authenticate the client.

### Authentication signatures

Message signing is an authentication technique that incorporates integrity methods. It consists in sending an encrypted hash code with the message.

When a signed message is received, both the sender identity and data integrity are verified by:

-   Decrypting the signature
-   Comparing the result with the calculated hash code

If the hash code is correct, data integrity is valid, and the sender is considered to be authenticated because the sender had the valid key to encrypt the digest.

 

# Security features

Gateway includes functions that ensure security at each level of the file transfer process:

-   [Protocol connection level security](#Protocol_connection_security)
-   [Transport level security](#Transport_level_security)
-   [Host system security](#Host_system_security)
-   [Integration in secured environments](#Integration_in_secured_environments)
-   [DMZ deployment](#DMZ_deployment)

<span id="Protocol_connection_security"></span>

## Protocol connection level security

With Gateway, you can analyze the identity of Transfer partners during protocol connection to determine whether or not you want to authorize them to connect and exchange files. You have the option of using internal or external processes for this identity control:

### Internal processing: Using the CGate object

By default, Gateway uses the CGate object to process connection identification at the protocol connection level.

You can use the CGate object to link client access rights to connection authorization. You can define:

-   File visibility for groups or sub-groups of users
-   Access to portions of the VFD (Virtual File Directory) tree
-   File transfer rights for individual users
-   Filtering based on the port number and IP address of the caller

#### CGate connection mechanism

When a remote user attempts to connect to Gateway via a CGate, the following identification process occurs:

Gateway identifies a CGateGroup that corresponds to the connected user and then scans CGate objects within that group. Since CGates can contain wildcards (\* and ?), this selection is based on a best matching process. Gateway selects the CGate object whose parameters most closely correspond to those taken from the network.

After selecting a CGate object, Gateway checks the protocol-dependent parameters, security parameters, and so on. If these checks fail, Gateway rejects the connection.

Gateway retrieves and merges the CGateGroup hierarchy for the selected CGate, to build a set of the following output parameters:

-   Protocol-dependent parameters for use while the connection is active
-   Connected user access rights to the VFD

#### External processing: Using the Protocol Connection Exit

Gateway provides the user exit <span class="code">ExitRcProtoConn</span> that enables you to configure remote identification from a database or an LDAP directory. This exit overrides the default CGate identification mechanism described above. To activate Protocol Connection Exit scheduling as a replacement for the default identification process, set the <span style="font-weight: bold;">[Connection control method](../../../gateway_userguide/configuration_start_here/config_gateway_paras#connection_control_method)</span> parameter in the configuration menu.

<span id="Transport_level_security"></span>

## Transport level security

At the transport level, Gateway provides support for:

-   Protocol and network translation
-   SSL (Secure Socket Layer) / TLS (Transport Layer Security) on incoming and outgoing connections
-   SSH protocol
-   Network Profile objects that determine which Security Profile to use
-   Security Profile objects to define security characteristics
-   Certificates and keys to authenticate partners involved in the exchange

### Protocol and network translation

Gateway is both a protocol-level and a network-level gateway. You can use it, for example, to route an incoming FTP Transfer over TCP/IP as an outgoing PeSIT transfer over a TCP/IP network . The external network and the enterprise network can be completely different, which makes attacks against internal networks more difficult.

### TLS/SSL security protocol support

SSL (Security Socket Layer) is a creation of Netscape. The Internet Engineering Task Force (IETF) used Version 3.0 of SSL to define the TLS protocol (Transport Layer Security). These very similar protocols operate between the network protocol layer (for example, TCP/IP) and application protocol layer (for example, FTP).

TLS functions independently of the file transfer protocol used. With TLS you can use any protocol except SFTP. This type of connection enables initiator and responder partners to communicate in a way that provides:

-   Confidentiality – to prevent eavesdropping
-   Simple (server-to-client) or mutual authentication - to prevent modification or manipulation of information
-   Integrity – to prevent message forgery

Since TLS security may involve mutual authentication of connection partners, Gateway includes an internal stand-alone X.509 certificate manager.

Gateway may be included in a more global certificate manager, commonly known as a PKI (Public Key Infrastructure). PKI integration requires specific development through security server exit customization.

#### Remote access from Axway MFT Navigator

The Axway MFT Navigator, enables you to perform actions on Gateway from a remote machine using a Web browser. These commands are transmitted to Gateway using a proprietary protocol (also called APICS) that runs over a TCP/IP network.

This type of TCP/IP connection is vulnerable to attacks that may endanger the whole information system involving Gateway. You can therefore secure the connection using TLS.

### SSH security protocol support

SSH (Secure Shell) is a protocol that provides secure remote login and other secure network services over an insecure network. SSH guarantees:

-   Authentication (via certificates or keys)
-   Integrity
-   Confidentiality

The SSH File Transfer Protocol (SFTP) enables you to exchange files between two remote machines. SFTP is an application-level protocol that is used as a generic protocol for communication between users and proxies or gateways to other Internet systems. It relies on the SSH protocol that establishes a user login and secure connection.

SSH and SFTP are separate and technically different, but are exclusively used together in Gateway. Gateway supports SFTP in client and server modes.

SFTP/SSH links require the use of a DSS, ECDSA or RSA key (or certificate) and the configuration of the following Gateway objects:

-   Remote Site
-   Network Profile
-   SSH Profile

### Network Profile

Gateway uses Network Profile objects to determine whether an incoming connection must be secured. Network Profiles contain matching rules that Gateway applies to the incoming connection parameters (origin address, SAP…). From the Network Profile that best matches the incoming connection, Gateway determines which Security Profile to use. (The Security Profile contains all required security elements.)

The Network Profile object contains the following parameters:

-   Network type (TCP)
-   Called address
-   Calling address
-   Security option (TLS, SSH or none)
-   Security Profile to use if the Security option is set to SSH or TLS

When Gateway receives an incoming connection, it selects a Network Profile and a Remote Site that match the received network parameters (called address and calling address).

### Security Profile

Gateway uses the Security Profile object to establish security for both incoming and outgoing connections. It is a configuration set that determines which security protocol to use, which encryption method, and so on.

Gateway provides two types of Security Profile:

-   TLS Profile
-   SSH Profile

In most cases, when you use TLS/SSL or SSH protocols, the connection is secured as soon as you establish a network connection. When an incoming connection occurs, Gateway uses the Network Profile to determine whether to use TLS/SSL or SSH.

#### SSH Security Profile

To establish an SSH connection, a Security Profile is mandatory. You can define several Security Profiles in the database, which can be of the type <span style="font-style: italic;">Client</span> or <span style="font-style: italic;">Server</span>.

Security Profiles contain all the parameters required to establish the SSH transport layer, such as:

-   Key exchange algorithms
-   Encryption
-   MAC (Hash)
-   Server key
-   Client authentication method

Gateway selects the Security Profile in the following way:

<span style="font-weight: bold;">In client mode</span>, the outgoing transfer is destined to an SFTP Site. The Remote Site contains a parameter that indicates which Security Profile to use. The Security Profile is of the type CLIENT and is enabled.

<span style="font-weight: bold;">In server mode</span>, an incoming connection arrives at your Gateway server. This connection is characterized by its calling address and its called address. Gateway then searches for a Network Profile with a called address and calling address that match those of the connection. The Network Profile that Gateway selects must have the security option set to SSH and must contain a valid Security Profile name. This Security Profile must be of the type SERVER and must be enabled. If Gateway does not find an appropriate profile the connection is rejected.

#### TLS Security Profile

You can configure cryptographic and authentication parameters via the TLS Profile object. Gateway selects the Profile to use for a TLS session depending on the way the connection between the partners is established (incoming or outgoing connection).

An incoming connection in TLS has a minimum of two levels of verification. The first is identification of a corresponding Network Profile object and the second is the identification and checking of the Remote Site object and its parameters.

For an outgoing connection, the Remote Site parameters determine whether or not to use a TLS Security Profile.

### Certificates and keys

SSH requires client and server authentication. Client and server can be authenticated by public key or by certificate. With either method, server authentication is a two-step process beginning with server identification via a public key and followed by specification of the preferred authentication method.

In TLS/SSL, the public key is integrated into the certificate.

#### Certificates

A certificate is an electronic document that:

-   Identifies an individual, a server, a company or any other entity
-   Associates that identity with a public key

When you communicate with any remote party, you determine the identity of that correspondent, before dealing with data integrity and confidentiality. Forbidding access to data and verifying the integrity of the received data is meaningless if you are not sure of the identity of the other party. Certificates help prevent the use of fake public keys for impersonation. Only the public key certified by the certificate works with the corresponding private key that belongs to the entity identified by the certificate.

You can import the following types of certificate into Gateway:

-   Root (top-level CA certificate)
-   CA (Certification Authority)
-   User
-   Other

#### Keys

SSH uses DSS, ECDSA and RSA keys (or RSA keys in certificates) to authenticate partners. Gateway supports DSS, ECDSA and RSA keys and certificates with RSA keys.

The private key is a local key that is assigned to Gateway (or an application using Gateway). It has a public part and a private part. You can configure Gateway to import keys automatically. Alternatively, you can import keys manually.

<span id="Host_system_security"></span>

## Host system security

Gateway provides complete protection for the host system via:

-   Virtual File Directory
-   Database encryption
-   Temporary file encryption
-   User Access Control of Gateway objects

### Virtual File Directory (VFD)

Internally, Gateway represents each Transfer as a transfer record registered in the Mailbox. However, transfer records are not organized hierarchically. To provide data presentation and organization, Gateway supplies a virtual device used in association with the Gateway Mailbox, called the Virtual File Directory (VFD). The VFD provides a logical and internal representation of files and directories. Remote clients have only a logical view of files. Clients cannot directly access the associated physical files (stored on the Gateway host machine).

The VFD is available to connected HTTP, FTP and SFTP clients. Using the VFD feature, Gateway behaves like any standard FTP SFTP or HTTP server.

The VFD offers two running modes that you can operate separately or simultaneously:

-   <span style="font-weight: bold;">Logical mode</span>: The VFD is a logical representation of directories and files (also known as VFD Items). These logical files represent a duplication of a given Transfer Request extract in the Gateway Mailbox. From the Gateway client side (FTP, SFTP or HTTP clients), you can view the logical representation of these files, but cannot directly access them.
-   <span style="font-weight: bold;">RFD (Real File Directory) mode</span>: The RFD is supported by a mount mechanism that links the logical file system to the physical file system of the Gateway host machine. The files seen from the client side are real files that are located on the Gateway host machine. Optionally, you can associate these files with a Gateway Mailbox transfer record.

The content of a real directory (or a mounted directory) is an exact image of the content of the corresponding directory on the Gateway host machine File System. When you make a file available for clients, you effectively make a physical copy of the file in the corresponding directory.

### Database encryption

You can use AES (Advanced Encryption Standard) encryption mechanisms to store Gateway administration objects and/or the Mailbox file securely on the host machine. Only users with specific rights can read, modify, or delete files. This encryption mechanism prevents external attacks. No one can access data that could enable them to bypass the Gateway authentication process.

Gateway integrates an internal PKI (Public Key Infrastructure) to encrypt the internal security database that stores security objects and all certificates and private keys.

Additionally, an external PKI is accessible via user exits:

-   To access an external LDAP certificate directory
-   To perform online certificate validation: OCSP

### Temporary file encryption

A network machine located in a DMZ can be accessed by machines in unsecured areas. It may therefore be subject to malicious attacks.

To route files, Gateway must make a local copy of the files before routing them. Gateway uses <span style="font-style: italic;">temporary file encryption</span> to protect the files it temporarily stores from malicious attacks. This is particularly important when you deploy Gateway in a DMZ. In a DMZ deployment, you should take the additional precaution of encrypting the Gateway Mailbox.

When you route files using Gateway and temporary file encryption, you must link the input transfer to the output transfer using the combination of a Decision Rule (to identify the incoming transfer) and an applied Model (to specify the outgoing transfer characteristics).

This enables Gateway to identify the security key necessary to read the deposited ciphered file in order to process it for the subsequent transfer.

Alternately, you can use the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> module for your DMZ deployment. With this solution, Gateway and all Gateway files are located within the protected zone.

### User Access Control of Gateway objects

User Access Control applies to all methods of accessing Gateway objects: via the Gateway GUI, command lines, APIs or the Axway MFT Navigator.

The <span style="font-style: italic;">User</span> and <span style="font-style: italic;">Profile</span> objects in Gateway enable you to define user identification and access rights. Typically only Administrators have access to these objects. The User object defines properties for each user and the Profile object defines the type of operations a set of users can perform on each Gateway object.

In the Profile object you specify the operations (such as Read, Write or Delete) allowed on the different types of Gateway object (Sites, Models, Transfer Requests, and so on).

For example, you could specify that all Users associated with a given Profile are authorized to access Site objects in Read and Write mode only.

Alternatively you can use [Customizable user exits](../../managing_security_start_here/access_control_about/access_control_using_exits) or [PassPort AM](../../managing_security_start_here/access_control_about/passport_am_about) to manage user access control.

<span id="Integration_in_secured_environments"></span>

## Integration in secured environments

Gateway is fully compatible with SOCKS4, FTP and HTTP proxies.

<span id="DMZ_deployment"></span>

## DMZ deployment

You can further enhance the isolation and security of your enterprise network by deploying Gateway in a DMZ architecture.

[Next topic](../../../gateway_userguide/ov_gateway/ov_monitoring_gateway)

Related topics

[About CGates and CGateGroups](../../../gateway_userguide/managing_partners_start_here/cgates_start_here)

[Internal user exits](../../../gateway_userguide/customizing_gw_about/user_exits_about/user_exits_internal)

[Managing TLS](../../managing_security_start_here/security_start_here/ssl_and_tls_protocols_about/managing_tls)

[SSH protocol](../../managing_security_start_here/security_start_here/ssh_protocol_about)

[Network Profiles](../../managing_security_start_here/security_start_here/network_profiles_start_here)

[Managing SSH Security Profiles](../../managing_security_start_here/security_start_here/ssh_protocol_about/ssh_security_profiles__gui_)

[Managing TLS Security profiles](../../managing_security_start_here/security_start_here/ssl_and_tls_protocols_about/tls_security_profiles__gui_)

[Certificates and keys](../../managing_security_start_here/security_start_here/certificates_and_keys_start_here)

[About Virtual File Directories](../../../gateway_userguide/transfers_start_here/virtual_file_directory_start_here)

[About Access Control Management](../../managing_security_start_here/access_control_about)

[About Proxy objects](../../../gateway_userguide/managing_partners_start_here/proxies_about)

[Overview: DMZ deployment](../../../gateway_userguide/ov_gateway/ov_dmz_deployment)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
