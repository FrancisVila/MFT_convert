{
    "title": "Extended catalog query APIs",
    "linkTitle": "Extended catalog query APIs",
    "weight": "180"
}# <span id="Extended_catalog_query_APIs"></span>Extended catalog query APIs

This topic describes the additional
fields relating to transport security that can be accessed via the catalog
query APIs (cftaix). These fields are used to determine whether transport
security was implemented for a terminated transfer, and if so, the session
parameters (authentication mode, suite negotiated, certificates used,
and so on).

### <span id="Extended_catalog_query_API_structure"></span>Extended catalog query API structure

The output structure of the extended catalog query API, cftaix, has
been modified. New fields relating to transport security have been added.
These fields are as follows:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>char cMode ;             /* Session mode (client/server) */<br />
char cAuthPolicy ;       /* Session auth (server/both) */<br />
char sCipher[3+1] ;      /* Session cipher suite */<br />
char sParm[64+1] ;       /* Profile free parameter */<br />
char sRemoteCn[32+1];    /* CN of remote user certificate */<br />
char sRemoteCaId[8+1];   /* CA alias of remote user certificate */<br />
char sUserCId[8+1];      /* Local user certificate alias */<br />
char sCertFname[64+1];   /* File including remote DER certificate */<br />
char sProf[8+1] ;        /* SSL profile ID */</td>
</tr>
</tbody>
</table>

The following table describes the new fields declared in the structure
returned by the extended catalog query API, cftaix.

All string-type fields, char name\[n+1\], are expressed in text format,
either ASCII or EBCDIC depending on the system, are left justified, and
terminated by a null byte.

Fields in cftaix queries

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="18%"><p>cMode </p></td>
<td data-valign="top" width="82%"><p>Direction of the SSL session in which the transfer was
performed.</p>
<p>C signifies client and
S signifies server. </p></td>
</tr>
<tr class="even" data-valign="middle">
<td data-valign="top" width="18%"><p>cAuthPolicy </p></td>
<td data-valign="top" width="82%"><p>Authentication mode of the SSL session in which the transfer
was performed.</p>
<ul>
<li>S
signifies that only the server was authenticated.</li>
<li>B
signifies that the client and server were authenticated.</li>
<li>A
signifies that the anonymous mode has been implemented. </li>
</ul></td>
</tr>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="18%"><p>sCipher </p></td>
<td data-valign="top" width="82%"><p>Suite negotiated for the SSL session.</p>
<p>This suite is set to one of the values from the suites
supported by Transfer CFT (1, 2, 4, 5, 9, 10 or 47). </p></td>
</tr>
<tr class="even" data-valign="middle">
<td data-valign="top" width="18%"><p>sParm </p></td>
<td data-valign="top" width="82%"><p>Value of the PARM parameter in the CFTSSL command used
to negotiate the session parameters. </p></td>
</tr>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="18%"><p>sRemoteCn </p></td>
<td data-valign="top" width="82%"><p>CN field of the user certificate presented by the remote
partner. </p></td>
</tr>
<tr class="even" data-valign="middle">
<td data-valign="top" width="18%"><p>sRemote CaId </p></td>
<td data-valign="top" width="82%"><p>Certificate identifier (in the local certificate database)
of the root authority of the certificate presented by the remote partner. </p></td>
</tr>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="18%"><p>sUserCId </p></td>
<td data-valign="top" width="82%"><p>Identifier (in the local certificate database) of the user
certificate used locally for authentication by the remote partner. </p></td>
</tr>
<tr class="even" data-valign="middle">
<td data-valign="top" width="18%"><p>sCertFname </p></td>
<td data-valign="top" width="82%"><p>Physical name of the file in which the certificate presented
by the remote partner was recorded. </p></td>
</tr>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="18%"><p>sProf </p></td>
<td data-valign="top" width="82%"><p>Identifier of the CFTSSL command used to negotiate the
session parameters. </p></td>
</tr>
</tbody>
</table>
