{
    "title": "Using  the LISTPKI command",
    "linkTitle": "Using LISTPKI",
    "weight": "250"
}You can use the LISTPKI
command to display the local certificate database according to criteria
that you set in the command parameters. Additionally, you can use the default model or create a new model to customize the elements displayed in the output. By default, the LISTPKI command uses the`  dspcnf.xml` model file as a basis for the dispaly, which is located in `<installdir>/runtime/conf`.

## Display the local certificate database

Parameter

Description

 

\[CONTENT = BRIEF |
FULL | DEBUG \]

Result display mode.

-   FULL: All contents display

-   DEBUG: All contents and additional general information display

-   BRIEF: a 79-character entry is displayed
    for each certificate. Additionally, when using the BRIEF value to display content:

    -   Items display showing a clear parent/child relationship
    -   If a certificate is marked as **Expired** (!), all of its children are labeled **Parent expired** (?)
    -   If a certificate's parent is missing, the line displays either a question mark (**?**) if the issuer is filtered, or an exclamation mark (**!**) if the issuer is missing

    The [FMODEL display example](#FMODEL%C2%A0d) features these elements.

\[ID    
= {\*, string1..8}\]

Unique local identifier of the certificate(s) to be displayed.

The \* and ? wildcard characters are accepted for the ID
parameter value.

\[ INUM  = {number0...99} \]

Internal number for the intermediate certificates in an imported chain of certificates (in the PKI database).

You can use this option to select a specific intermediate certificate.

\[TYPE = ALL |
USER | ROOT | INTER | KEY | CERT | |  ENTITY \]

Type of certificate to display:

-   ALL:
    all certificates
-   USER:
    user certificates
-   ROOT:
    root authority certificates
-   INTER:
    intermediate authority certificates
-   KEY: list PKIKEY items
-   CERT: list ROOT, INTER, and USER certificates for PKICER only
-   ENTITY: any entity identifier created using PKIENTITY command

\[STATE = ALL | ACT
| INACT | EXPIRED\]

Status of the certificates to display:

-   ALL:
    all statuses
-   ACT:
    all activated certificates
-   INACT:
    all deactivated certificates
-   EXPIRED:
    all expired certificates

FMODEL

The path to the file containing the models. If no model is found, the default format, which is the same as for the DISPLAY command, is used.

> **Note**  
> Transfer CFT 3.7 and higher uses the  dspcnf.xml model fileby default. To have the display format from a previous version, use FMODEL=NONE.

ROOTCID

The  certificate authority ID.  See an example in [ROOTCID](../../../../c_intro_userinterfaces/command_summary/parameter_intro/rootcid).

HELP 

Provides helps for the available fields for the different elements, or lists the available MODELS for the given file. Values include:

-   NONE (default)
-   FIELDS
-   MODELS

<span id="CONTENT_BRIEF_Display"></span>

### CONTENT=BRIEF display (default format)

The following information is displayed for the CONTENT parameter BRIEF
value:

```
 
 
```
<span id="CONTENT_BRIEF_Display"></span>

### CONTENT=BRIEF display (former format, or no model)

```
 
 
 
 
```

Id

Identifier assigned to the certificate when it was imported into the
database.

Root

Identifier of the root certificate authority.

Miscellaneous

Miscellaneous certificate information (the letter only displays in when using the old format or no model):

-   T: Type of Certificate: R for
    Root (Root Authority), I for Intermediate (Intermediate Authority),
    U for User
-   S: Certificate state: A for
    active or I for inactive
-   C: x denotes if the certificate
    is in the database
-   K: x denotes if the private
    key associated with the certificate exists
-   E: Certificate expired (!) or otherwise

Exp. Date

Expiry date of the certificate.

Delivered to

CN (Common name) attribute of the certificate user DN field.

Delivered by

CN (Common name) attribute of the certificate signer DN field.

<span id="CONTENT_FULL_Display"></span>

### CONTENT=FULL display (default display)

```
```

### CONTENT=FULL display (former format, or no model)

```
```

Certificate id

Identifier assigned to the certificate when it was imported into the
database.

Certificate Type

Identifier of the root certificate authority.

Root id

Identifier of the root certificate authority.

Signer id

Identifier of the certificate signer (issuer).

State

State of the certificate in the database (active or inactive).

Serial Number

Serial number of the certificate.

Delivered to

CN (Common name) attribute of the certificate user DN field.

Delivered by

CN (Common name) attribute of the certificate signer DN field.

Expired before and after

Period of validity of the certificate (start and end date )

Comment

Value assigned to the COMMENT parameter when the certificate was imported
into the database.

Owner DN

Value of the certificate user DN field.

Signer DN

Value of the certificate signer DN field.

<span id="INUM"></span>

### 

<span id="FMODEL d"></span>

### Filter using FMODEL example

You can use the FMODEL parameter to display only certain types of certificates; for example below we want to display the certificates that have the ACT state:

```
PKIUTIL LISTPKI CONTENT=BRIEF, STATE=ACT
```

Resulting in:

```
Id.              Root         Type    State Exp.Date       K   Delivered to Delivered by
EXPIRED      EXPIRED  ROOT   ACT     01/09/2015 !      4k_ca        4k_ca
EXPIRED    EXPIRED   USER    ACT    01/09/2030 ? x 4k_user      4k_ca
ROOT            ROOT         ROOT   ACT    22/07/2029       2k_root      2k_root
INTER1      ROOT         INTER  ACT    22/07/2029       2k_l1_ca     2k_root
?       USER2  ROOT        USER   ACT    22/07/2029   x  2k_l3_user1  2k_l2_ca
USER1     ROOT         USER    ACT    22/07/2029   x  2k_l2_user1  2k_l1_ca
USER0       ROOT         USER    ACT    22/07/2029   x  2k_l1_user1  2k_root
>      7 Certificates selected
```

Key to indicators and symbols:

-   The "EXPIRED" ROOT certificate displays the "!" symbol in the "K" column.
-   The "EXPIRED" USER certificate displays the "?" symbol in the "K" column, indicating one if his issuer is expired.
-   The "?" before their ID indicates that their issuer is not shown, although available.
-   If a certificate displays an explanation mark "!" before the ID, it indicates that their issuer is not available (error).
