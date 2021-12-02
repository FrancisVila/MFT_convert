{
    "title": "rootcid",
    "linkTitle": "rootcid",
    "weight": "2940"
}<span id="rootcid"></span>

### rootcid

#### PKICER  

\[ ROOTCID = string 32 \]

This parameter must be indicated for a certificate authority.
In this case, the ID and ROOTCID parameters have the same value.

This parameter is mandatory for:

-   DELETE: deletion of a certificate
    from the database, and
-   REPLACE: update of a certificate, modes

It indicates
the identifier of the certificate authority to be deleted or updated.

#### PKIEXT, LISTPKI

\[ ROOTCID = string 32 \]

This parameter allows you to chose the ROOTCID of the certificates to extract or display, respectively.

**Example**

PKIEXT example

The result is a file that contains only information about the 2K\_ROOT and 2K\_INTER certificates.

LISTPKI example

#### CFTSSL

\[ ROOTCID = string 32 \]

List of certificate authorities, where the total length of all identifiers cannot exceed 256 characters for CFTSSL. This list references a maximum of 10 identifiers in the local certificate database.

> **Note:**
>
> To use more than 10 identifiers, you can refer to the PKIENTITY information.

In client mode, this list is used to check the server
certificate. Only certificates signed by one of the authorities in the
ROOTCID parameter are accepted.

 

[Return to Command index](../../)
