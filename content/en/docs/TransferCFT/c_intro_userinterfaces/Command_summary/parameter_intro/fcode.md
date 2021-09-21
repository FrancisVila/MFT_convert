{
    "title": "fcode",
    "linkTitle": "fcode",
    "weight": "1120"
}### **<span id="fcode_CFTAUTH"></span>**<span id="fcode"></span>fcode

#### **CFTXLATE**

The sent file data code. The following table indicates for each OS the
default value supported.

<table border="1" cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>OS</th>
         <th>Default</th>
      </tr>
   </thead>
      <tr>
         <td valign="top" width="27%">
            <p>z/OS (MVS)</p>
         </td>
         <td valign="top" width="73%">
            <p>EBCDIC </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="27%">
            <p>IBM i (OS400)</p>
         </td>
         <td valign="top" width="73%">
            <p>EBCDIC </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="27%">
            <p>UNIX </p>
         </td>
         <td valign="top" width="73%">
            <p>ASCII </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="27%">
            <p>VMS </p>
         </td>
         <td valign="top" width="73%">
            <p>ASCII </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="27%">
            <p>Windows</p>
         </td>
         <td valign="top" width="73%">
            <p>ASCII </p>
         </td>
      </tr>
</table>

#### <span id="fcode_CFTRECV"></span>CFTRECV, RECV

**\[FCODE = {depending
on FTYPE | ASCII | BINARY | EBCDIC}\]   **

**C**ode of the receiver file data (local file encoding).

*Default values:*  
In the PeSIT protocol (except for the SIT profile), if the code of the
data received from the network is BINARY, the default value of FCODE (dynamically
determined at each transfer) is BINARY.  
If not, the default value of FCODE (dynamically determined at each transfer)
is equal to the value of the native code of the receiver system.  
The default value of FCODE does not depend on the file type received from
the network.

The translation performed on reception depends on the:

-   Local
    code (explicit or implicit value of the FCODE parameter)
-   Network
    code (code of the data received from the network)
-   Presence
    of an external translation table if needed

Note that an external translation table is taken into account:

-   If
    it corresponds to the local code and network code
-   And
    if the ID of the CFTXLATE command is referenced by an XLATE parameter
    (of the RECV, CFTRECV or CFTPART command), or else is equal to the "default"
    ID of CFTPARM

At each receive transfer:

-   if
    the data received is in ASCII and the local data is in EBCDIC, or vice-versa,
    translation is always performed: translation according to an external
    table, or, by default, translation according to the Transfer CFT internal
    table
-   if
    the data received and the local data have the same code, ASCII or EBCDIC,
    an external table is required to execute a translation

Transfer CFT does not have an ASCII/ASCII or EBCDIC/EBCDIC
internal table. If the data received and/or the local data are binary,
no translation is performed.

The code of the data received is not detected by examining the data.
This code is:

-   Either
    explicitly communicated by the sender (see NCODE parameter of the CFTSEND
    command, for PeSIT CFT to CFT)
-   Or
    deduced from the protocol rules

#### <span id="fcode_CFTSEND"></span>CFTSEND, SEND

\[FCODE = {ASCII | BINARY | EBCDIC}\]

Code of the data to be sent.

The default value, determined according to the characteristics of each
transfer, depends on the type (FTYPE) of the file sent (see the Operations
Guide specific your OS). The sender’s automatic detection of the FTYPE
as required, partly takes the place of automatic code detection.

For the effect of FCODE on the translation performed during the send
transfer: see the explanations given at the level of the NCODE parameter
of the present command.

[Return to Command index](../../)