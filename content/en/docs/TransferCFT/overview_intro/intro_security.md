{
    "title": "Security  services ",
    "linkTitle": "Security services ",
    "weight": "150"
}Transfer CFT offers different types of security services in order to secure communication, protect data, and control user access:

-   Transport security
-   Access management
-   DMZ enabled communication
-   File encryption at rest
-   SFTP

After configuring the security system, you define the users and the
actions that they can make on the various <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> objects. These definitions apply to objects declared within the operating
systems, such as files and batch procedures, as well as <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>
objects, commands, transfer requests and internal files.

<span id="Transport_Security"></span>

## Transport security

Transfer CFT implements the cryptographic protocol TLS (Transport Layer Security) and its previous version SSL (Secure Sockets Layer), which provides authentication between the parties, data confidentiality, and integrity. Additionally, Transfer CFT is FIPS (Federal Information Processing Standards) compliant.

Transport Security is ensured through a public key infrastructure (PKI), which you can managed either using Transfer CFT, PassPort PS or an external PKI.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Check the security options
included in the license key before attempting to implement in your environment.         </td>
      </tr>
   </tbody>
</table>

For more information on transport security, see the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> [Security](../../transport_security_start_here) topics.

## Access management

Access management for Transfer CFT refers to the policy that allow users to perform actions on the product ( when not using Central Governance).

## DMZ enabled communication

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>supports communication in the DMZ using Secure Relay. All of the connections that use this <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> network resource transmit through Secure Relay for both incoming and outgoing connections.

\*Presently not configurable from the <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> interface.

## File encryption at rest

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> embeds TrustedFile to encode and decode files in S/MIME, CMS, OpenPGP, XML Signature, XML Encryption, and XAdES (BES and EPES) format. These standards secure data at rest, independently of the data communication method.

\*Presently not configurable from the <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> interface.

## SFTP

SSH File Transfer Protocol (SFTP) is a protocol for transferring files over an encrypted SSH channel, which you can use with Transfer CFT.
