{
    "title": "Using  the LISTPKI command",
    "linkTitle": "Using LISTPKI",
    "weight": "260"
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

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top"><span>Transfer CFT</span> 3.7 and higher uses the <code> dspcnf.xml</code> model fileby default. To have the display format from a previous version, use FMODEL=NONE.         </td>
      </tr>
   </tbody>
</table>

ROOTCID

The certificate authority ID. See an example in [ROOTCID](../../CFTUTIL/Parameter_index/rootcid.htm).

HELP 

Provides helps for the available fields for the different elements, or lists the available MODELS for the given file. Values include:

-   NONE (default)
-   FIELDS
-   MODELS

### <span id="CONTENT_BRIEF_Display"></span>CONTENT=BRIEF display (default format)

The following information is displayed for the CONTENT parameter BRIEF
value:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p><span> 
Id.        Root    Type State
Exp.Date     Delivered to    Delivered by</span></p>
            <p><span> 
4KL1CA     4KL1CA  R    INACT
28/07/2039   4k_l1_ca       
4k_root</span></p>
            <p><span> 
4KL1CA1    4KL1CA1 R    ACT  
28/07/2039   4k_l1_ca       
4k_root</span></p>
            <p><span> 
4KROOT     4KROOT  R    ACT  
28/07/2039   4k_root        
4k_root</span></p>
            <p><span>   
4K1L1EXP 4KROOT  U    ACT   14/10/2009 !
4k_l1_user2_exp 4k_root</span></p>
            <p><span>   
4KL1US1  4KROOT  U    ACT  
28/07/2039   4k_l1_user1     4k_root</span></p>
            <p><span>&gt;      
5 PKICER selected</span></p>
            <p> </p>
            <p><span>Id.    
Certificates list</span></p>
            <p><span>ENTITY1 4KL1US1,
4K1L1EXP</span></p>
            <p><span>&gt;      
1 PKIENTITY selected</span></p>
            <p> </p>
            <p><span>Id.             
S K Bits</span></p>
            <p><span>4KL1USER1       
A x 4096</span></p>
            <p><span>4KL1USER1KEYPRIV I x
4096</span></p>
            <p><span>4KL1USER1KEYPUB 
A   4096</span></p>
            <p><span>&gt;      
3 PKIKEY selected</span></p>         </td>
      </tr>
   </tbody>
</table>

### <span id="CONTENT_BRIEF_Display"></span>CONTENT=BRIEF display (former format, or no model)

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p><span>Certificates:</span></p>
            <p> </p>
            <p><span>Id.         
Root         iNum T S C K E
Exp.Date   Delivered to  Delivered by</span></p>
            <p><span>------------
------------ ---- - - - - - ---------- ------------- -------------</span></p>
            <p><span>4KL1CA      
4KL1CA            R I
x     28/07/2039 4k_l1_ca     
4k_root</span></p>
            <p><span>4KL1CA1     
4KL1CA1           R A
x     28/07/2039 4k_l1_ca     
4k_root</span></p>
            <p><span>4KROOT      
4KROOT            R A
x     28/07/2039
4k_root       4k_root</span></p>
            <p><span>4K1L1EXP    
4KROOT            U A x
x ! 14/10/2009 4k_l1_user2_e 4k_root</span></p>
            <p><span>4KL1US1     
4KROOT            U A x
x   28/07/2039 4k_l1_user1   4k_root</span></p>
            <p> </p>
            <p><span>Entities:</span></p>
            <p> </p>
            <p><span>Id.                             
Certificate list</span></p>
            <p><span>--------------------------------
---------------------------------</span></p>
            <p><span>ENTITY1                         
4KL1US1</span></p>
            <p><span>                                
4K1L1EXP</span></p>
            <p><span>Keys:</span></p>
            <p> </p>
            <p><span>Id.                             
S K Bits</span></p>
            <p><span>--------------------------------
- - ----</span></p>
            <p><span>4KL1USER1                       
A x 4096</span></p>
            <p><span>4KL1USER1KEYPRIV                
I x 4096</span></p>
            <p><span>4KL1USER1KEYPUB                 
A   4096</span></p>         </td>
      </tr>
   </tbody>
</table>

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

### <span id="CONTENT_FULL_Display"></span>CONTENT=FULL display (default display)

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p><span>&lt;FIELD  Cert
Id.             =
'4KL1US1'</span></p>
            <p><span>       
Cert Type            =
'U'</span></p>
            <p><span>       
Cert Root            =
'4KROOT'</span></p>
            <p><span>       
Internal num         = ''</span></p>
            <p><span>       
Signer Id.           =
'4KROOT'</span></p>
            <p><span>       
State               
= 'ACT'</span></p>
            <p><span>       
Serial number        = '45'</span></p>
            <p><span>       
Delivered to         = '4k_l1_user1'</span></p>
            <p><span>       
Delivered by         = '4k_root'</span></p>
            <p><span>       
Issuer status        = 'missing'</span></p>
            <p><span>       
Expired Before       = '29/07/2009'</span></p>
            <p><span>       
Expired After        = '28/07/2039'</span></p>
            <p><span>       
Comment             
= ''</span></p>
            <p><span>       
Owner's DN           =
'/C=FR/ST=HAUTS-DE-SEINE/L=PUTEAUX/O=CFT_SAMPLE/OU=CFT_L1_SAMPLE/CN=4k_l1_user1'</span></p>
            <p><span>       
Signer's DN          =
'/C=FR/ST=HAUTS-DE-SEINE/L=PUTEAUX/O=CFT_SAMPLE/OU=CFT_SAMPLE/CN=4k_root'</span></p>
            <p><span>       
Private RSA Key size = '4096'</span></p>
            <p><span>       
Usage Key            =
'Digital Signature, Key Encipherment, Data Encipherment'</span></p>
            <p><span>       
Extended Usage Key   = 'TLS Web Server Authentication, TLS Web Client
Authentication'</span></p>
            <p><span>       
/&gt;</span></p>
            <p><span>&gt;      
1 PKICER selected</span></p>
            <p><span>&gt;      
1 PKICER without displayed issuer</span></p>
            <p><span>&gt;      
0 PKIENTITY selected</span></p>
            <p><span>&gt;      
0 PKIKEY selected</span></p>         </td>
      </tr>
   </tbody>
</table>

### CONTENT=FULL display (former format, or no model)

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p><span>         
Cert  id.     
ID         = 4KL1US1</span></p>
            <p><span>         
Cert  type    
TYPE       = USER</span></p>
            <p><span>         
Root  id.     
ROOT       = 4KROOT</span></p>
            <p><span>         
Internal num.  INUM       =</span></p>
            <p><span> </span></p>
            <p><span>         
Signer id.    
SID        = 4KROOT</span></p>
            <p><span> </span></p>
            <p><span>         
State         
STATE      = ACT</span></p>
            <p><span> </span></p>
            <p><span>         
Serial number  SNUMB      = 45</span></p>
            <p><span> </span></p>
            <p><span>         
Delivered to   Us.CN      =</span></p>
            <p><span>         
4k_l1_user1</span></p>
            <p><span>         
</span></p>
            <p><span>         
Delivered by   Si.CN      =</span></p>
            <p><span>         
4k_root</span></p>
            <p><span> </span></p>
            <p><span>         
Certificat validity</span></p>
            <p><span>         
-------------------</span></p>
            <p><span>         
Expired Before :         29/07/2009
00:00:00</span></p>
            <p><span>         
Expired After  :         28/07/2039
23:59:59</span></p>
            <p><span> </span></p>
            <p><span>         
Comment       
COMMENT     =</span></p>
            <p><span> </span></p>
            <p><span>         
Owner's DN     OWNER'S DN  =</span></p>
            <p><span>         
/C=FR/ST=HAUTS-DE-SEINE/L=PUTEAUX/O=CFT_SAMPLE/OU=CFT_L1_SAMPLE/</span></p>
            <p><span>         
CN=4k_l1_user1</span></p>
            <p><span> </span></p>
            <p><span>   
      Signer's DN    SIGNER'S DN =</span></p>
            <p><span>         
/C=FR/ST=HAUTS-DE-SEINE/L=PUTEAUX/O=CFT_SAMPLE/OU=CFT_SAMPLE/CN=</span></p>
            <p><span>         
4k_root</span></p>
            <p><span> </span></p>
            <p><span>         
Private Key type  RSA      =  4096 bits</span></p>
            <p><span> </span></p>
            <p><span>         
Usage
Key                 
=</span></p>
            <p><span>         
Digital Signature, Key Encipherment, Data Encipherment</span></p>
            <p><span> </span></p>
            <p><span>         
Extended Usage Key         =</span></p>
            <p><span>         
TLS Web Server Authentication, TLS Web Client Authentication</span></p>         </td>
      </tr>
   </tbody>
</table>

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

### <span id="INUM"></span>

### <span id="FMODEL d"></span>Filter using FMODEL example

You can use the FMODEL parameter to display only certain types of certificates; for example below we want to display the certificates that have the ACT state:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>PKIUTIL LISTPKI CONTENT=BRIEF, STATE=ACT         </td>
      </tr>
   </tbody>
</table>

Resulting in:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Id.      Root      Type   State Exp.Date   K   Delivered to Delivered by</p>
            <p>EXPIRED  EXPIRED  ROOT   ACT   01/09/2015 !    4k_ca 4k_ca</p>
            <p>EXPIRED  EXPIRED   USER   ACT   01/09/2030 ? x 4k_user 4k_ca</p>
            <p>ROOT     ROOT      ROOT   ACT   22/07/2029   2k_root 2k_root</p>
            <p>INTER1   ROOT      INTER  ACT   22/07/2029   2k_l1_ca 2k_root</p>
            <p>? USER2  ROOT      USER   ACT  22/07/2029 x  2k_l3_user1 2k_l2_ca</p>
            <p>USER1    ROOT      USER   ACT  22/07/2029 x  2k_l2_user1 2k_l1_ca</p>
            <p>USER0    ROOT      USER   ACT  22/07/2029 x  2k_l1_user1 2k_root</p>
            <p>&gt; 7 Certificates selected</p>         </td>
      </tr>
   </tbody>
</table>

Key to indicators and symbols:

-   The "EXPIRED" ROOT certificate displays the "!" symbol in the "K" column.
-   The "EXPIRED" USER certificate displays the "?" symbol in the "K" column, indicating one if his issuer is expired.
-   The "?" before their ID indicates that their issuer is not shown, although available.
-   If a certificate displays an explanation mark "!" before the ID, it indicates that their issuer is not available (error).
