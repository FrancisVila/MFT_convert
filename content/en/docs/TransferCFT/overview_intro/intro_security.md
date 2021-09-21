{
    "title": "Security services ",
    "linkTitle": "Security services ",
    "weight": "150"
}# <span id="10__Security"></span><span id="Security_system_objectives"></span>Security services

Transfer CFT offers different types of security services in order to secure communication, protect data, and control user access:

-   Transport security
-   Access management
-   DMZ enabled communication
-   File encryption at rest
-   SFTP

After configuring the security system, you define the users and the
actions that they can make on the various Transfer CFT objects. These definitions apply to objects declared within the operating
systems, such as files and batch procedures, as well as Transfer CFT
objects, commands, transfer requests and internal files.

## <span id="Transport_Security"></span>Transport security

Transfer CFT implements the cryptographic protocol TLS (Transport Layer Security) and its previous version SSL (Secure Sockets Layer), which provides authentication between the parties, data confidentiality, and integrity. Additionally, Transfer CFT is FIPS (Federal Information Processing Standards) compliant.

Transport Security is ensured through a public key infrastructure (PKI), which you can managed either using Transfer CFT, PassPort PS or an external PKI.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Check the security options 
 included in the license key before attempting to implement in your environment.         </td>
      </tr>
</table>

For more information on transport security, see the Transfer CFT [Security](../../transport_security_start_here) topics.

## Access management

Access management for Transfer CFT refers to the policy that allow users to perform actions on the product ( when not using Central Governance).

## DMZ enabled communication

Transfer CFTsupports communication in the DMZ using Secure Relay. All of the connections that use this Transfer CFT network resource transmit through Secure Relay for both incoming and outgoing connections.

\*Presently not configurable from the Central Governance interface.

## File encryption at rest

Transfer CFT embeds TrustedFile to encode and decode files in S/MIME, CMS, OpenPGP, XML Signature, XML Encryption, and XAdES (BES and EPES) format. These standards secure data at rest, independently of the data communication method.

\*Presently not configurable from the Central Governance interface.

## SFTP

SSH File Transfer Protocol (SFTP) is a protocol for transferring files over an encrypted SSH channel, which you can use with Transfer CFT.
