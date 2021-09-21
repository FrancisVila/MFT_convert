{
    "title": "Using LISTPKI",
    "linkTitle": "Using LISTPKI",
    "weight": "260"
}# <span id="Using_the_LISTPKI_command"></span>Using the LISTPKI command

You can use the LISTPKI
command to display the local certificate database according to criteria
that you set in the command parameters. Additionally, you can use the default model or create a new model to customize the elements displayed in the output. By default, the LISTPKI command uses the`  dspcnf.xml` model file as a basis for the dispaly, which is located in `<installdir>/runtime/conf`.

## Display the local certificate database

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">       </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>[CONTENT = BRIEF | 
 FULL | DEBUG ]</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Result display mode.</p>
            <ul>
               <li>FULL: All contents display               </li>
               <li>DEBUG: All contents and additional general information display               </li>
               <li>BRIEF: a 79-character entry is displayed 
 for each certificate. Additionally, when using the BRIEF value to display content:            <ul>               <li>Items display showing a clear parent/child relationship               </li>               <li>If a certificate is marked as <b>Expired</b> (!), all of its children are labeled <b>Parent expired</b> (?)               </li>               <li>If a certificate's parent is missing, the line displays either a question mark (<b>?</b>) if the issuer is filtered, or an exclamation mark (<b>!</b>) if the issuer is missing               </li>            </ul>            <p>The <a href="#fmodel%c2%a0d">FMODEL display example</a> features these elements.</p>               </li>
            </ul>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>[ID     
 = {*, string1..8}]</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Unique local identifier of the certificate(s) to be displayed.</p>
            <p>The * and ? wildcard characters are accepted for the ID 
 parameter value.</p>
         </td>
      </tr>
      <tr valign="top">
      </tr>
      <tr valign="top">
         <td>[ INUM  = {number0...99} ]          </td>
         <td>
            <p>Internal number for the intermediate certificates in an imported chain of certificates (in the PKI database). </p>
            <p>You can use this option to select a specific intermediate certificate.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>[TYPE = ALL | 
 USER | ROOT | INTER | KEY | CERT | |  ENTITY ]</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Type of certificate to display:</p>
            <ul>
               <li>ALL: 
 all certificates               </li>
               <li>USER: 
 user certificates               </li>
               <li>ROOT: 
 root authority certificates               </li>
               <li>INTER: 
 intermediate authority certificates               </li>
               <li>KEY: list PKIKEY items               </li>
               <li>CERT: list ROOT, INTER, and USER certificates for PKICER only               </li>
               <li>ENTITY: any entity identifier created using PKIENTITY command               </li>
            </ul>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>[STATE = ALL | ACT 
 | INACT | EXPIRED]</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Status of the certificates to display:</p>
            <ul>
               <li>ALL: 
 all statuses               </li>
               <li>ACT: 
 all activated certificates               </li>
               <li>INACT: 
 all deactivated certificates               </li>
               <li>EXPIRED: 
 all expired certificates               </li>
            </ul>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="35.143%">
            <p>FMODEL</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>The path to the file containing the models. If no model is found, the default format, which is the same as for the DISPLAY command, is used.</p>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="35.143%">ROOTCID         </td>
         <td>The  certificate authority ID.  See an example in <a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/rootcid">ROOTCID</a>.         </td>
      </tr>
      <tr valign="top">
         <td width="35.143%">HELP          </td>
         <td>
            <p>Provides helps for the available fields for the different elements, or lists the available MODELS for the given file. Values include:</p>
            <ul>
               <li> NONE (default)               </li>
               <li>FIELDS               </li>
               <li>MODELS               </li>
            </ul>
         </td>
      </tr>
   </tbody>
</table>

### <span id="CONTENT_BRIEF_Display"></span>CONTENT=BRIEF display (default format)

The following information is displayed for the CONTENT parameter BRIEF
value:

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><span>Transfer CFT</span> 3.7 and higher uses the <code> dspcnf.xml</code> model fileby default. To have the display format from a previous version, use FMODEL=NONE.         </td>
      </tr>
</table>

### <span id="CONTENT_BRIEF_Display"></span>CONTENT=BRIEF display (former format, or no model)

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
<p xmlns="http://www.w3.org/TR/REC-html40"><span> 
Id.        Root    Type State
Exp.Date     Delivered to    Delivered by</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span> 
4KL1CA     4KL1CA  R    INACT
28/07/2039   4k_l1_ca       
4k_root</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span> 
4KL1CA1    4KL1CA1 R    ACT  
28/07/2039   4k_l1_ca       
4k_root</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span> 
4KROOT     4KROOT  R    ACT  
28/07/2039   4k_root        
4k_root</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>   
4K1L1EXP 4KROOT  U    ACT   14/10/2009 !
4k_l1_user2_exp 4k_root</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>   
4KL1US1  4KROOT  U    ACT  
28/07/2039   4k_l1_user1     4k_root</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>&gt;      
5 PKICER selected</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"> </p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>Id.    
Certificates list</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>ENTITY1 4KL1US1,
4K1L1EXP</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>&gt;      
1 PKIENTITY selected</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"> </p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>Id.             
S K Bits</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>4KL1USER1       
A x 4096</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>4KL1USER1KEYPRIV I x
4096</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>4KL1USER1KEYPUB 
A   4096</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>&gt;      
3 PKIKEY selected</span>
</p>
         </td>
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

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>Certificates:</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"> </p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>Id.         
Root         iNum T S C K E
Exp.Date   Delivered to  Delivered by</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>------------
------------ ---- - - - - - ---------- ------------- -------------</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>4KL1CA      
4KL1CA            R I
x     28/07/2039 4k_l1_ca     
4k_root</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>4KL1CA1     
4KL1CA1           R A
x     28/07/2039 4k_l1_ca     
4k_root</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>4KROOT      
4KROOT            R A
x     28/07/2039
4k_root       4k_root</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>4K1L1EXP    
4KROOT            U A x
x ! 14/10/2009 4k_l1_user2_e 4k_root</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>4KL1US1     
4KROOT            U A x
x   28/07/2039 4k_l1_user1   4k_root</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"> </p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>Entities:</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"> </p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>Id.                             
Certificate list</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>--------------------------------
---------------------------------</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>ENTITY1                         
4KL1US1</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>                                
4K1L1EXP</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>Keys:</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"> </p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>Id.                             
S K Bits</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>--------------------------------
- - ----</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>4KL1USER1                       
A x 4096</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>4KL1USER1KEYPRIV                
I x 4096</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>4KL1USER1KEYPUB                 
A   4096</span>
</p>
         </td>
      </tr>
   </tbody>
</table>

### CONTENT=FULL display (former format, or no model)

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>&lt;FIELD  Cert
Id.             =
'4KL1US1'</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>       
Cert Type            =
'U'</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>       
Cert Root            =
'4KROOT'</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>       
Internal num         = ''</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>       
Signer Id.           =
'4KROOT'</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>       
State               
= 'ACT'</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>       
Serial number        = '45'</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>       
Delivered to         = '4k_l1_user1'</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>       
Delivered by         = '4k_root'</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>       
Issuer status        = 'missing'</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>       
Expired Before       = '29/07/2009'</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>       
Expired After        = '28/07/2039'</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>       
Comment             
= ''</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>       
Owner's DN           =
'/C=FR/ST=HAUTS-DE-SEINE/L=PUTEAUX/O=CFT_SAMPLE/OU=CFT_L1_SAMPLE/CN=4k_l1_user1'</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>       
Signer's DN          =
'/C=FR/ST=HAUTS-DE-SEINE/L=PUTEAUX/O=CFT_SAMPLE/OU=CFT_SAMPLE/CN=4k_root'</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>       
Private RSA Key size = '4096'</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>       
Usage Key            =
'Digital Signature, Key Encipherment, Data Encipherment'</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>       
Extended Usage Key   = 'TLS Web Server Authentication, TLS Web Client
Authentication'</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>       
/&gt;</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>&gt;      
1 PKICER selected</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>&gt;      
1 PKICER without displayed issuer</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>&gt;      
0 PKIENTITY selected</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>&gt;      
0 PKIKEY selected</span>
</p>
         </td>
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

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
Cert  id.     
ID         = 4KL1US1</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
Cert  type    
TYPE       = USER</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
Root  id.     
ROOT       = 4KROOT</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
Internal num.  INUM       =</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span> </span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
Signer id.    
SID        = 4KROOT</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span> </span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
State         
STATE      = ACT</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span> </span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
Serial number  SNUMB      = 45</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span> </span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
Delivered to   Us.CN      =</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
4k_l1_user1</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
Delivered by   Si.CN      =</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
4k_root</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span> </span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
Certificat validity</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
-------------------</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
Expired Before :         29/07/2009
00:00:00</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
Expired After  :         28/07/2039
23:59:59</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span> </span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
Comment       
COMMENT     =</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span> </span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
Owner's DN     OWNER'S DN  =</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
/C=FR/ST=HAUTS-DE-SEINE/L=PUTEAUX/O=CFT_SAMPLE/OU=CFT_L1_SAMPLE/</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
CN=4k_l1_user1</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span> </span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>   
      Signer's DN    SIGNER'S DN =</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
/C=FR/ST=HAUTS-DE-SEINE/L=PUTEAUX/O=CFT_SAMPLE/OU=CFT_SAMPLE/CN=</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
4k_root</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span> </span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
Private Key type  RSA      =  4096 bits</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span> </span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
Usage
Key                 
=</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
Digital Signature, Key Encipherment, Data Encipherment</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span> </span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
Extended Usage Key         =</span>
</p>
<p xmlns="http://www.w3.org/TR/REC-html40"><span>         
TLS Web Server Authentication, TLS Web Client Authentication</span>
</p>
         </td>
      </tr>
   </tbody>
</table>

Resulting in:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>PKIUTIL LISTPKI CONTENT=BRIEF, STATE=ACT         </td>
      </tr>
   </tbody>
</table>

Key to indicators and symbols:

-   The "EXPIRED" ROOT certificate displays the "!" symbol in the "K" column.
-   The "EXPIRED" USER certificate displays the "?" symbol in the "K" column, indicating one if his issuer is expired.
-   The "?" before their ID indicates that their issuer is not shown, although available.
-   If a certificate displays an explanation mark "!" before the ID, it indicates that their issuer is not available (error).
