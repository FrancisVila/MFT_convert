{
    "title": "id",
    "linkTitle": "id",
    "weight": "1540"
}### <span id="id"></span>id

Identifier. The maximum length for an identifier value-type is 32 characters.
This affects all Transfer CFT commands.

#### <span id="id_CFTAUTH"></span>CFTAUTH

\[ID = identifier \]

Authorization list identifier.

If the value *identifier* begins with the characters ‘NOT’, the
IDFs designated by this command are inhibited for the corresponding partner;
the other IDFs are authorized.

If the value *identifier* does not begin with the characters ‘NOT’,
the IDFs designated by this command are authorized for the corresponding
partner; the other IDFs are prohibited.

To use an authorization list, the id must be defined in the CFTPART
keywords SAUTH or RAUTH.

#### <span id="id_CFTCAT"></span>CFTCAT

\[ID = identifier \]

Identifier for the CFTCAT object.

#### <span id="id_CFTDEST"></span>CFTDEST

\[ID = identifier \]

Identifier of the list of partners.

This identifier must be unique. You cannot have several CFTDEST with
the same ID.

#### <span id="id_CFTEXIT"></span>CFTEXIT

\[ID = identifier \]

**See
Identifier table below**

Command identifier (32 characters).

#### <span id="Exit_Identifier_table"></span>Exit Identifier table

The value of the identifier corresponds with the identifier in the related
commands listed below.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>EXIT type </th>
         <th>Command</th>
         <th>Parameter</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Directory         </td>
         <td>
            <p>CFTPROT</p>
         </td>
         <td>
            <p>EXITA </p>
         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>EXIT </p>
         </td>
      </tr>
      <tr>
         <td>File          </td>
         <td>
            <p>CFTSEND, SEND, CFTRECV, RECV </p>
         </td>
         <td>
            <p>EXIT </p>
         </td>
      </tr>
      <tr>
         <td>End of transfer         </td>
         <td>
            <p>CFTPARM </p>
         </td>
         <td>
            <p>EXITEOT </p>
         </td>
      </tr>
   </tbody>
</table>

#### <span id="id_CFTPARM"></span>CFTPARM

\[ID = identifier
\]

Identifier of the CFTPARM command.

This value, passed as an activation parameter, describes a monitor configuration.

Example

CFTMAIN parm1

Transfer CFT is started with the CFTPARM id = parm1. If no value is used,
the monitor uses the default value 'IDPARM0'.

#### <span id="id_CFTPART"></span>CFTPART

\[ID = identifier
\]

Local partner identifier.

#### <span id="id_CFTPROT"></span>CFTPROT

\[ID =
identifier \]

CFTPROT command identifier.

In order for to be used, this name must be referenced in the values
taken by the CFTPARM PROT parameter.

#### <span id="id_CFTLOG"></span>CFTLOG

\[ID = identifier
\]

Identifier of the CFTLOG command.

#### <span id="id_CFTXLATE"></span>CFTXLATE

\[ID = identifier
\]

Translation table identifier.

Several CFTXLATE commands may have the same identifier, if the values
of DIRECT, FCODE or NCODE are different.

#### <span id="id_CFTRECV"></span>CFTRECV

\[ID = identifier
\]

Local model file identifier (IDF)

The "COMMUT" value for this parameter takes a particular meaning
for Transfer CFT: it corresponds to the description of the files received
as an intermediate partner. For the store and forward to be accepted,
the command (CFTRECV ID = COMMUT) has to be customized explicitly on the
store and forward site. If not, the store and forward is refused.

<table cellspacing="0" width="90%">
   <col/>
   <col/>
      <tr>
         <td width="26%">
            <p><b>PeSIT SIT profile</b>
</p>
         </td>
         <td width="74%">
            <p>For 
 the PeSIT SIT profile, the model file identifier is subjected to the format 
 constraint (Fnnnnn). See  <a href="../../../../protocols_start_here/about_pesit">Protocols: 
 PeSIT</a>.</p>
         </td>
      </tr>
</table>

#### <span id="id_CFTSEND"></span>CFTSEND

\[ID = identifier
\]

Local
identifier of the model file (IDF) to be sent.

<table cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td width="26%">
            <p>PeSIT SIT profile</p>
         </td>
         <td width="74%">
            <p>In the PeSIT protocol with the SIT profile, the model file 
 identifier is subject to the format constraint (Fnnnnn). See  <a href="../../../../protocols_start_here/about_pesit">Protocols: 
 PeSIT</a>.</p>
         </td>
      </tr>
</table>

#### <span id="Network_id"></span>Network id

Network resource identifier.

#### CFTACCNT, CFTCOM, CFTIDF, CFTNET, CFTTCP, CFTTRACE, CFTAPPL, CFTSSL, CFTEXT, LISTPARM, LISTPART

\[ID = identifier \]

#### PKIENTITY

\[ID = identifier \]

Identifier for a list of certificate authorities.

#### EXTAMCACHE

**\[ ID = identifier \]**

Selects the user, or users, for which you want to obtain access rights.

#### CFTUIPREF

**\[ ID = identifier \]**

Identifier for the user interface preferences.

[Return to Command index](../../)