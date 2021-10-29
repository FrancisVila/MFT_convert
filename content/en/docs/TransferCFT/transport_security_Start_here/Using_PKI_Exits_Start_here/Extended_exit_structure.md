{
    "title": "Extended exit structure",
    "linkTitle": "Extended exit structure",
    "weight": "250"
}This table displays the fields and communication structure for the
directory, end of transfer, and file exits in server mode:

Exit structure

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>char cMode;      /* Client/Server */<br />
char cAuthPolicy;      /* Server/Both */<br />
char bCipher;      /* Cipher suite */<br />
char sParm[64+1];      /* Free parameter from CFTSSL
command */<br />
char sRemoteUserDn[256+1]; /* Remote user certificate DN */<br />
char sRemoteIssuerDn[256+1]; /* Remote issuer DN */<br />
char sRemoteCaId[8+1];      /* Remote CA alias */<br />
char sUserCId[8+1];           
/* Local user alias */<br />
char sCertFname[64+1];      /* File including remote
DER certificate */<br />
char sProf[8+1] ;      /* SSL profile ID. */<br />
char sRemoteSerial[64+1];      /* Serial number */<br />
char zExitFree[64];      /* Free area for external
PKI */         </td>
      </tr>
   </tbody>
</table>
