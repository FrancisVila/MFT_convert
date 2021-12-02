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

```
Id.       Root iNum T S C K E  Exp.Date   Delivered to  Delivered by
------------ ------------ ---- - - - - - ---------- ------------- -------------
2K\_INTER  2K\_ROOT I A x           22/07/2029  2k\_l1\_ca         2k\_root
2K\_ROOT   2K\_ROOT R A x            22/07/2029  2k\_root         2k\_root
4K\_ROOT   4K\_ROOT R A x            28/07/2039  4k\_root           4k\_root
4K\_USER   4K\_ROOT U A x x        28/07/2039  4k\_l1\_user1   4k\_root
```

PKIEXT example

The result is a file that contains only information about the 2K\_ROOT and 2K\_INTER certificates.

```
PKIUTIL PKIEXT FOUT=PKI.CMD, ROOTCID=2K\_ROOT
```

LISTPKI example

```
PKIUTIL LISTPKI ROOTCID=4K\_ROOT
Id. Root iNum T S C K E  Exp.Date   Delivered to  Delivered by
------------ ------------ ---- - - - - - ---------- ------------- -------------
4K\_ROOT 4K\_ROOT R A x     28/07/2039   4k\_root      4k\_root
4K\_USER 4K\_ROOT U A x x   28/07/2039   4k\_l1\_user1  4k\_root
```

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
