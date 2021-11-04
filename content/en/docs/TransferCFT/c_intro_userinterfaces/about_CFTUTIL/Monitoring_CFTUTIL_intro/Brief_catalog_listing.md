{
    "title": "LISTCAT - Brief/Full catalog listings",
    "linkTitle": "LISTCAT - Brief catalog listing",
    "weight": "310"
}<span id="Displayed_catalog_information"></span>

## Displayed catalog information

In the following examples, each field displayed is identified by a number
which makes reference to the associated comment. The display differs according
to the CONTENT and NPART selection parameters.

The following is indicated at the end of the display of the characteristics
of the selected catalog entries:

-   The number of entries
    whose characteristics are displayed (n)
-   The total number
    of entries recorded in the catalog at the time the LISTCAT command is
    processed (p)
-   The number of catalog
    entries still free (q) and the percentage of space still free (r%)

This information is displayed in the following form:

-   n records selected
-   p records in catalog
    file
-   q records free
    (r%)

## Parameter descriptions

<span id="Full_Catalog_listing"></span>

### LISTCAT CONTENT = FULL 

In this
example, the LISTCAT parameter content
is defined as full. Each field displayed is identified by a number
which references the associated comment. The display differs according
to the CONTENT and NPART parameters.

See also [Listing catalog contents](../listcat_command).

For DIAGI and DIAGP refer to: [Codes,
Diagnostics and Messages](../../../../troubleshoot_intro/messages_and_error_codes_start_here) .

Example

**LISTCAT CONTENT = FULL**



    CFTU20I
    CFTU20I CFT Windows
    CFTU20I Version 3.1.2 20140428
    CFTU20I (C) Copyright AXWAY 1989-2014
    CFTU20I ====> Starting Session on 20/03/2015 Time is 11:30:25
    CFTU20I Parameters file    :C:\Axway\Transfer_CFT\runtime\data\cftparm
    CFTU20I Partners file      :C:\Axway\Transfer_CFT\runtime\data\cftpart
    CFTU20I Catalog file       :C:\Axway\Transfer_CFT\runtime\data\cftcata
    CFTU20I
    0 record(s) selected
    10000 record(s) in Catalog file
    10000 record(s) free (100%)
    CFTU00I LISTCAT  _ Correct ()
    CFTU20I Number of Command(s) 1
    CFTU20I Number of error(s)   0
    CFTU20I Ending   Session on 20/03/2015 Time is 11:30:26
    CFTU20I Session active for  0:00:00

### LISTCAT CONTENT = BRIEF, NPART = {identifier | mask}

**LISTCAT CONTENT = BRIEF, NPART = {*identifier*
| *mask*}**


    1          2 
                 3 
                  4 
                    5 
                        6 
                         7
    Date = DD-MM-YYYY, Time = hh:mm
    Partner DTSA File Transfer Diags Parm
    Network Name) Id. Id.                                   CFT 
     Prot.
    xxxxxxxxxxxxx xxxx xxxxxx xxxxxx     xxx 
      xxxxxx 
      xxxxxxxxxxxx
    xxxxxxxxxx   xxxx 
       xxxxxx 
       xxxxxx 
           xxx 
      xxxxxx 
       xxxxxxx
    xxxxxxxxx   xxxx 
       xxxxxx 
       xxxxxx 
          xxx 
      xxxxx   xxxxxxxxxxx

The following table contains the comments associated with the various
headings contained in this example.

**LISTCAT CONTENT - BRIEF, NPART - Headings
comments**

<table>
   <th>
      <tr>
<th>Heading         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>1 </p>         </td>
         <td><p>Partner network identifier.<br />
The partner network name corresponds to the NRPART parameter of the CFTPART
command and has a length of 16 characters only. </p>         </td>
      </tr>
      <tr>
         <td><p>2 </p>         </td>
         <td><p>Transfer state<br />
The characters DTSA mean:</p>
<ul>
<li>Direction
= S/R (Send/Receive)</li>
<li>Type
= F/M/R (File/Message/Reply)</li>
<li>State = D/C/H/K/T/X (Disp/Current/Hold/Keep/Terminated/eXecuted)</li>
<li>Ack = A (Acknowledge)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>3 </p>         </td>
         <td><p>File identifier (IDF) for a file transfer or message identifier
(IDM) </p>         </td>
      </tr>
      <tr>
         <td><p>4 </p>         </td>
         <td><p>Transfer identifier. Transfer identifier assigned by the
Transfer CFT (IDT) </p>         </td>
      </tr>
      <tr>
         <td><p>5 </p>         </td>
         <td><p>Transfer CFT internal diagnostic code<br />
For a transfer with an error, this field is defined with the Transfer CFT
internal diagnostic code (DIAGI) relative to this error<br />
For a correctly terminated transfer, this field is set to zero (1) </p>         </td>
      </tr>
      <tr>
         <td><p>6 </p>         </td>
         <td><p>Protocol diagnostic code<br />
If the entry concerned is not a generic entry:</p>
<ul>
<li>for a
transfer with an error, this field is defined with the protocol diagnostic
code (DIAGP) relative to this error (2)</li>
<li>for a
correctly terminated transfer, this field indicates the compression factor
obtained which is documented as follows:</li>
<li><ul>
<li>CP
NONE: transfer correctly terminated with no "on line" compression
requested</li>
<li>CP
xx%: transfer terminated correctly with a compression factor of xx%</li>
</ul></li>
<li>for a
delayed transfer, this field is defined with:</li>
<li><ul>
<li>hh:mm:ss:
if sent the same day</li>
<li>dd/mm/yy:
if sent the following days</li>
</ul></li>
</ul>
<p> </p>
<p>If the entry concerned is a generic entry, this field is
defined with one of the following values:</p>
<ul>
<li>RECV
ALL: generic entry for a global reception request for all the files with
a given IDF</li>
<li>RECV
MSK: generic entry for a global reception request for IDFs with "wildcards"</li>
<li>MIN CYC: generic
entry for cyclic transfers, period expressed in minutes</li>
<li>DAY CYC: generic
entry for cyclic transfers, period expressed in days</li>
<li>MON CYC: generic
entry for cyclic transfers, period expressed in months</li>
<li>DIFFUS: generic
entry for a broadcasting</li>
<li>COLLECT: generic
entry for a collection</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>7 </p>         </td>
         <td><p>PARM field<br />
This field is 24 characters long and may be truncated as required </p>         </td>
      </tr>
   </tbody>
</table>

**(1) (2)**: Refer to
*[Codes
Diagnostics and Messages](../../../../troubleshoot_intro/messages_and_error_codes_start_here)*.

### For LISTCAT CONTENT = BRIEF, PART = {identifier | mask}

The NPART parameter is not defined.

**LISTCAT CONTENT = BRIEF, PART = {*identifier*
| *mask*}**


    1            2 
                 3 
                   4 
                   5 
                       6 
                    7 
                8 
                             9
    Date = DD-MM-YYYY, Time = hh:mm
    Partner DTSA     File 
               Transfer 
                   Records 
                Diag 
       Diag 
     Applic.
    Ident 
             Ident 
               Transmit 
         Total 
                        Protocol 
       Ident
    xxxxxxx   xxxx 
       xxxxxxxx 
       xxxxxxxx 
      nnnnnnnn 
     nnnnnnnn   nnn 
       xxxxxxxx 
       xxxxxxxx
    xxxxxxxx   xxxx 
       xxxxxxxx 
       xxxxxxxx 
      nnnnnnnn 
     nnnnnnnn   nnn 
       xxxxxxxx 
       xxxxxxxx
    xxxxxxx   xxxx 
       xxxxxxxx 
       xxxxxxxx 
       nnnnnnnn 
     nnnnnnnn   nnn 
       xxxxxxxx 
       xxxxxxxx

The following table contains the comments associated with the various
headings contained in this figure.

<table>
   <th>
      <tr>
<th>Heading         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>1 </p>         </td>
         <td><p>Identifier of the partner described in the commands CFTPART
(corresponding to the ID parameter) or CFTDEST (one of the PART in the
broadcasting list) </p>         </td>
      </tr>
      <tr>
         <td><p>2 </p>         </td>
         <td><p>Transfer state description<br />
The DTSA characters mean:</p>
<ul>
<li><strong>D</strong>irection = S/R    
(Send/Receive)</li>
<li><strong>T</strong>ype
= F/M/R     (File/Message/Reply)</li>
<li><strong>S</strong>tate
= D/C/H/K/T/X     Disp/Current/Hold/Keep/Terminated/eXecuted)</li>
<li><strong>A</strong>ck
= A     (Acknowledge)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>3 </p>         </td>
         <td><p>File identifier (IDF) for a file transfer or message identifier
(IDM). </p>         </td>
      </tr>
      <tr>
         <td><p>4 </p>         </td>
         <td><p>Transfer identifier (IDT) </p>         </td>
      </tr>
      <tr>
         <td><p>5 </p>         </td>
         <td><p>If the transfer involves:</p>
<ul>
<li>a file: number
of records to be sent</li>
<li>a message: message
text truncated to 21 characters</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>6 </p>         </td>
         <td><p>If the transfer involves:</p>
<ul>
<li>a file:
number of records sent</li>
<li>a message:
remainder of the message text truncated to 21 characters</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>7 </p>         </td>
         <td><p>Transfer CFT internal diagnostic code<br />
For a transfer with an error, this field is defined with the Transfer CFT
internal diagnostic code (DIAGI) relative to this error<br />
For a correctly completed transfer, this field is set to zero <strong>(1)</strong> </p>         </td>
      </tr>
      <tr>
         <td><p>8 </p>         </td>
         <td><p>Protocol diagnostic code<br />
If the entry concerned is not a generic entry:</p>
<ul>
<li>for a
transfer with an error, this field is defined with the protocol diagnostic
code (DIAGP) relevant to this error <strong>(2)</strong></li>
<li>for a
correctly completed transfer, this field indicates the obtained compression
factor which is documented with the following format:
<ul>
<li>CP
NONE: transfer terminated correctly with no "on line" compression
requested</li>
<li>CP
xx%: transfer terminated correctly with a compression factor of xx%</li>
</ul></li>
<li>for a
delayed transfer, this field is defined with:</li>
<li><ul>
<li>hh:mm:ss:
if sent the same day</li>
<li>dd/mm/yy:
if sent the following days</li>
</ul></li>
</ul>
<p>If the entry concerned is a generic entry, this field is
defined with one of the following values:</p>
<ul>
<li>RECV
ALL: generic entry for a global receive request for all the files with
a given IDF</li>
<li>RECV
MSK: generic entry for a global receive request for IDFs with "wildcards"</li>
<li>MIN CYC: generic
entry for cyclic transfers, period expressed in minutes</li>
<li>DAY CYC: generic
entry for cyclic transfers, period expressed in days</li>
<li>MON CYC: generic
entry for cyclic transfers, period expressed in months</li>
<li>DIFFUS: generic
entry for a broadcasting</li>
<li>COLLECT: generic
entry for a collection</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>9 </p>         </td>
         <td><p>Identifier of the application (IDA) associated with this
transfer </p>         </td>
      </tr>
   </tbody>
</table>

 **(1) (2)**: See *[Codes
Diagnostics and Messages](../../../../troubleshoot_intro/messages_and_error_codes_start_here)*.
