{
    "title": "Manage PGP keys",
    "linkTitle": "Manage PGP keys",
    "weight": "110"
}PGP keys are managed from the Administration Tool according to their scope: *local* or *partner*.

-   *Local PGP keys* can be either server-scoped or account-based. To manage server-scoped certificates select **Setup > Certificates** and the *Local Certificates* tab. Account-based certificates are managed from the *Private Certificates* pane of the *Certificates* pane of the *User Account* page. You can use the appropriate page to get detailed information for a particular key, generate a key, delete a key, or export public and private keys.
-   *Partner PGP keys* are also managed by account. You can generate, import, delete, and export account-specific PGP keys. For partner PGP keys, the private key can be exported on certificate creation only. For more information on managing account-based PGP keys, see [Use the following procedure to import a partner certificate.](../../../accounts/c_st_usercertificates/manage-user-partner-certificates)

The following topics provide how-to instructions for managing PGP keys:

-   [Generate PGP keys](#generate)
-   [Export PGP keys](#export)
-   [Import PGP keys](#import)
-   [Local (server) PGP keys management](#local)

## <span id="Generate"></span>Generate PGP keys

The two scenarios for generation of PGP keys are:

-   Generate a local key pair and export it into a text file that can be used by the respective partners for encryption of the incoming data. You can export the private key for a local or account private certificate at any time.
-   Generate a partner key pair and export the private key in a file that can be used by the partner for decryption and signing. In this case only the public key is saved and used by SecureTransport. You can save the private key immediately after you generate the key pair. SecureTransport deletes the private key after you save it or decline to save it.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Partner and local PGP keys are stored in different key rings. Partner keys are account-specific and have a relation to the account, while local keys are not connected to a particular account. To this end, all partner keys are stored in a single key ring and all partner private keys are stored in a corresponding single secret key ring.         </td>
      </tr>
</table>

## <span id="Export"></span>Export PGP keys

PGP keys are exported in the format of ASCII-armored key data in compliance with RFC 2440. The data of the exported PGP key is stored directly in a file. The private key of a partner key pair can only be exported when the certificate is first generated by SecureTransport.

## <span id="Import"></span>Import PGP keys

There are three scenarios for importing PGP keys into SecureTransport:

-   Import a partner PGP public key
-   Import a PGP key pair, generated by a third party, in the set of local keys that applies to all of the SecureTransport system
-   Import a local PGP key pair as a private certificate from the *Private Certificates* pane of the *Certificates* pane of the *User Account* page

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The supported formats of the imported keys are as specified in the RFC 2440 standard: a binary or armored PGP public/private key message.         </td>
      </tr>
</table>

## <span id="Local"></span>Local (server) PGP keys management

Local (server) and partner PGP keys are generated, exported, imported, and deleted for a particular account. See [User certificates](../../../accounts/c_st_usercertificates)

 

**Related topic:**

-   [PGP transfer settings dependencies](../r_st_pgptransfersettingsdependencies)

[User certificates](../../../accounts/c_st_usercertificates)