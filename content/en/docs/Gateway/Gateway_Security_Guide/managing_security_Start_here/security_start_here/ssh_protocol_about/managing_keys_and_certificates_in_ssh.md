{
    "title": "Managing Keys and Certificates in SSH",
    "linkTitle": "Managing Keys and Certificates in SSH",
    "weight": "200"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

This topic describes how to import and manage partner keys (and certificates).

[Overview](#Overview)

[Managing key pairs](#Managing_key_pairs)

[Importing key pairs automatically](#Importing_key_pairs_automatically)

[Importing key pairs manually](#Importing_key_pairs_manually)

[Validating (Enabling) a key](#Validating__Enabling__a_key)

[Trusting hosted keys](#Trusting_hosted_keys)

<span id="Overview"></span>

## Overview

For known partners, the Security server can run in complete autonomy. It requires no external services. The Security server uses information stored locally in its database to perform the remote communicating partner mutual authentication.

When a new partner attempts to connect, there are several possible scenarios:

-   Known partner sends a certificate from a known CA: the connection is accepted.
-   Known partner sends a public key with signature: the connection is accepted.
-   Unknown partner: key or certificate is imported or not depending on how you configure your automatic import parameter. Gateway rejects the connection and allows you to manually enable the key or certificate.

<span id="Managing_key_pairs"></span>

## Managing key pairs

SSH uses DSS, ECDSA and RSA keys (or RSA keys in certificates) to authenticate partners. Gateway supports DSS, ECDSA and RSA keys and certificates with RSA keys. Supported ECDSA keys are the ones required by RFC5656 (nistp256, nistp384 and nistp521).

The private key is a local key that is attributed to Gateway (or an application using Gateway). It has a public and private part.

A public key originates from a partner. This partner must have the private key to be able to authenticate itself to Gateway. The partner public keys are referred to as hosted keys.

The partner public keys are stored in the Gateway key database.

A key pair can be either a local key (public and private key parts) or a partner key (public key only). A Gateway database exists for storing the key pairs.

A <span style="font-weight: bold;">KeyPairRecord</span> consists of the following fields:

-   <span style="font-weight: bold;">Alias</span>: unique logical name to identify the key
-   <span style="font-weight: bold;">Group</span>: group name to organize keys by group
-   <span style="font-weight: bold;">Comment</span>: user comment
-   <span style="font-weight: bold;">State</span>: <span style="font-style: italic;">ENABLED</span>, <span style="font-style: italic;">DISABLED</span> or <span style="font-style: italic;">TO\_CHECK</span>
-   <span style="font-weight: bold;">Algorithm</span>: *RSA*, *DSS*, *ECDSA\_NISTP256*, *ECDSA\_NISTP384*, or *ECDSA\_NISTP521*
-   <span style="font-weight: bold;">CreatedOn</span>: import / creation date
-   <span style="font-weight: bold;">IsPrivateKeySet</span>: value is 1 if the key is local (private part is completed) otherwise 0 (public only)
-   <span style="font-weight: bold;">Fingerprint</span>: hash of the public part of the key
-   <span style="font-weight: bold;">Value of the Key</span>: triplet (n, e, d) for RSA (max length 4096 bits), quintuplet (p, q, g, y, x) for DSS (max length 1024 bits)

In an imported key, you can only modify the fields <span style="font-weight: bold;">Alias</span>, <span style="font-weight: bold;">Group</span> and <span style="font-weight: bold;">Comment</span>.

<span id="Importing_key_pairs_automatically"></span>

## Importing key pairs automatically

You can configure Gateway to import remote keys automatically in the <span style="font-weight: bold;">SSH Profile</span>, by setting <span style="font-weight: bold;">remote\_key\_import</span> parameter to Y.

If you set the automatic remote key import (<span style="font-weight: bold;">remote\_key\_import</span> = Y), and the public key of the partner is not present in the database, then this public key is stored in the database and the connection is closed.

<span style="font-weight: bold;">Note</span>: Unknown partners are always rejected even if their public keys are imported into the database. Imported keys remain in the <span style="font-style: italic;">TO\_CHECK</span> state until they are manually validated.

Gateway generates an alias automatically for the new key. The comment zone includes the partner name. You can modify the alias and the comment zone of an imported key.

When you import a key automatically it is associated with the group <span style="font-weight: bold;">public\_key\_group</span> defined in the Site (or the SSH Profile). If no <span style="font-weight: bold;">public\_key\_group</span> is defined, they are associated with the group GDEFAULT.

The public keys must be unique in the database. Therefore if a client tries to connect several times with the same key, only one key record will be created in the database.

The automatic import process applies both to client and server mode.

This method also applies to importing and validating certificates.

<span id="Importing_key_pairs_manually"></span>

## Importing key pairs manually

Alternatively, you can use the <span class="code" style="font-weight: bold;">[secadm import\_key](../../certificates_and_keys_start_here/managing_certificates_cli/managing_keys_cli#secadm_import_key)</span> command to manually import known partner keys (DER or PEM format).

If you do not define a <span class="code" style="font-weight: bold;">public\_key\_group</span>, the key is associated with the group GDEFAULT by default.

<span id="Validating__Enabling__a_key"></span>

## Validating (Enabling) a key

When you import a new key, the key has a <span style="font-weight: bold;">state</span> of <span style="font-style: italic;">TO\_CHECK.</span> You must validate the partner public key explicitly via the GUI or <span class="code" style="font-weight: bold;">secadm update\_key</span> command, by setting its state to <span style="font-style: italic;">ENABLED</span>. To refuse the key, you can set its state to <span style="font-style: italic;">DISABLED</span> or delete it from the database.

Unlike a certificate, a public key does not contain any information on its owner. The only reliable method to validate a key is to manually check the value of the key or its fingerprint with external (telephone or mail) confirmation from the partner in question.

To facilitate exchange of this value, you can use a fingerprint of the public key. The fingerprint is a hash of the key on 32 octets (using the SHA256 algorithm). The advantage of a hash is that you only have 32 octets to check as opposed to 404 octets for a DSS 1024-bit key or for an RSA 1024-bit key or 256 octets for a ECDSA\_NISTP521 key

<span id="Trusting_hosted_keys"></span>

## Trusting hosted keys

The parameter <span class="code">trust\_hosted\_public\_keys</span> allows the acceptance of the authentication of a partner if a public key (or a certificate) belonging to it is already present in the Gateway database in ENABLED state. The term <span style="font-weight: bold;">hosted</span> applies to a public key (or a certificate) hosted in the Gateway database, and for which the origin (owner of the associated private key) is known and authorized to connect via SSH.

When the parameter <span class="code">trust\_hosted\_public\_keys</span> is activated, Gateway searches for a hosted key equivalent to the key received.

The following three conditions must be fulfilled to accept a connection:

-   The two keys have the same fingerprint
-   The hosted key is in ENABLED state
-   If a group is completed in the authentication control, only a key in this group is trusted

Related topics

[SSH protocol](../)

[Using SSH](../using_ssh)

[Managing SSH Security Profiles](../ssh_security_profiles__gui_)

[SSH authentication](../ssh_authentication)

[Managing SSH Security Profiles (command line)](../managing_ssh_security_profiles_cli)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
