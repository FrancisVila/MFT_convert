{
    "title": "Delivered templates for IBM i (iSeries)",
    "linkTitle": "Delivered templates for IBM i (iSeries)",
    "weight": "370"
}This topic describes the Axway Transfer CFT API templates and CL programs  for the IBM i (iseries) platform. You may decide to use the delivered samples as a basis for integrating APIs, or as a model to create your own.

The Transfer CFT IBM i templates are located in the production library (CFTPROD by default), in the CFTSRC folder.

## <span id="COBOL"></span>COBOL language (CBLLE file extension)

In the **CL program** column, click the program link for information on how to compile and execute.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>CL program</th>
         <th>Associated COBOL</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>I_TCFTU_CBL         </td>
         <td>TCFTU_CBL1         </td>
         <td>Synchronous API.         </td>
      </tr>
      <tr class="even">
         <td>I_INTCAT         </td>
         <td>INTCAT         </td>
         <td>Same results as CFTUTIL LISTCAT, with some filtering allowed.         </td>
      </tr>
      <tr class="odd">
         <td>I_ACCNTPGM         </td>
         <td>ACCNTPGM         </td>
         <td>Statistics based on the V23 ACCNT file.         </td>
      </tr>
      <tr class="even">
         <td>I_ACCNT24         </td>
         <td>ACCNTPGM24         </td>
         <td>Statistics based on the V24 ACCNT file.         </td>
      </tr>
   </tbody>
</table>

## <span id="RPG"></span>RPG language (.RPGLE file extension)

In the **Template** column, click the template link to view the sample template as a text file.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Template</th>
         <th>Function</th>
         <th>            <p>Services</p></th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td><a href="#">TCFTI_RPG</a>         </td>
         <td>CFTI         </td>
         <td>OPEN - CLOSE - NEXT - SELECT- MODIF         </td>
         <td>Using CFTI function (CFTAPI V23 structure )         </td>
      </tr>
      <tr class="even">
         <td><a href="#">TCFTI2_RPG</a>         </td>
         <td>cftaix         </td>
         <td>OPEN - CLOSE - SELECT240 - NEXT240 - SORT - DO -         </td>
         <td>Using CFTIX function (CFTAPI V24 structure )         </td>
      </tr>
      <tr class="odd">
         <td><a href="#">TCFTU_RP1</a>         </td>
         <td>CFTU         </td>
         <td>SEND - DELETE         </td>
         <td>Tests the CFTU, CFTC functions (asynchronous API)         </td>
      </tr>
      <tr class="even">
         <td><a href="#">TCFTU_RP1N</a>         </td>
         <td>CFTU         </td>
         <td>SEND         </td>
         <td>Using PLIST for receiving the SEND command         </td>
      </tr>
      <tr class="odd">
         <td><a href="#">TCFTU_RP2</a>         </td>
         <td>CFTU         </td>
         <td>COM, SEND, GETXINFO, CLOSEAPI         </td>
         <td>Tests the CFTU function (synchronous API)         </td>
      </tr>
   </tbody>
</table>

## How to compile and execute a COBOL sample

### <span id="TCFTU"></span> I\_TCFTU\_CBL program

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CRTCBLMOD MODULE(&lt;<span>CFTPGM</span>&gt;/TCFTU_CBL1) SRCFILE(&lt;<span>CFTPGM</span>&gt;/CFTSRC)</p>
            <p>SRCMBR(TCFTU_CBL1) DBGVIEW(*ALL) REPLACE(*YES)</p>
            <p> </p>
            <p>CRTPGM PGM(&lt;<span>CFTPGM</span>&gt;/TCFTU_CBL1) MODULE(&lt;<strong>CFTPGM</strong>&gt;/TCFTU_CBL1)</p>
            <p>BNDSRVPGM(&lt;CFTPGM&gt;/LIBAPISRV1) REPLACE(*YES)</p>
            <p> </p>
            <p>CRTBNDCL PGM(&lt;<span>CFTPGM</span>&gt;/I_TCFTU_CB) SRCFILE(&lt;<span>CFTPGM</span>&gt;/CFTSRC)</p>
            <p>SRCMBR(I_TCFTU_CB) OPTION(*EVENTF) REPLACE(*YES) DBGVIEW(*SOURCE)</p>
            <p> </p>
            <p>CALL PGM(&lt;<span>CFTPGM</span>&gt;/I_TCFTU_CB)</p>         </td>
      </tr>
   </tbody>
</table>

### <span id="INTCAT"></span>I\_INTCAT program

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CRTCBLMOD MODULE(&lt;<span>CFTPGM</span>&gt;/INTCAT) SRCFILE(&lt;<span>CFTPGM</span>&gt;/CFTSRC)</p>
            <p>SRCMBR(INTCAT) DBGVIEW(*ALL) REPLACE(*YES)</p>
            <p> </p>
            <p>CRTPGM PGM(&lt;<span>CFTPGM</span>&gt;/INTCAT) MODULE(&lt;<span>CFTPGM</span>&gt;/INTCAT)</p>
            <p>BNDSRVPGM(&lt;<span>CFTPGM</span>&gt;/LIBAPISRV1) REPLACE(*YES)</p>
            <p> </p>
            <p>CRTBNDCL PGM(&lt;<span>CFTPGM</span>&gt;/I_INTCAT) SRCFILE(&lt;<span>CFTPGM</span>&gt;/CFTSRC)</p>
            <p>SRCMBR(I_INTCAT) OPTION(*EVENTF) REPLACE(*YES) DBGVIEW(*SOURCE)</p>
            <p> </p>
            <p>CALL PGM(&lt;<span>CFTPGM</span>&gt;/I_INTCAT)</p>         </td>
      </tr>
   </tbody>
</table>

### <span id="ACCNTPGM"></span>I\_ACCNTPGM program for ACCNT V23

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CRTBNDCBL PGM(&lt;<span>CFTPGM</span>&gt;/ACCNTPGM) SRCFILE(&lt;<span>CFTPGM</span>&gt;/CFTSRC) SRCMBR(ACCNTPGM) OPTION(*EVENTF) DBGVIEW(*SOURCE) REPLACE(*YES)</p>
            <p> </p>
            <p>CRTBNDCL PGM(&lt;<span>CFTPGM</span>&gt;/I_ACCNTPGM) SRCFILE(&lt;<span>CFTPGM</span>&gt;/CFTSRC) SRCMBR(I_ACCNTPGM) OPTION(*EVENTF) REPLACE(*YES) DBGVIEW(*SOURCE)</p>
            <p> </p>
            <p>CALL PGM(&lt;CFTPGM&gt;/I_ACCNTPGM)</p>         </td>
      </tr>
   </tbody>
</table>

### <span id="ACCNT24"></span>I\_ACCNT24 program for ACCNT V24

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CRTBNDCBL PGM(&lt;<span>CFTPGM</span>&gt;/ACCNTPGM24) SRCFILE(&lt;<span>CFTPGM</span>&gt;/CFTSRC) SRCMBR(ACCNTPGM24) OPTION(*EVENTF) DBGVIEW(*SOURCE) REPLACE(*YES)</p>
            <p> </p>
            <p>CRTBNDCL PGM(&lt;<span>CFTPGM</span>&gt;/I_ACCNT24) SRCFILE(&lt;<span>CFTPGM</span>&gt;/CFTSRC) SRCMBR(I_ACCNTPGM) OPTION(*EVENTF) REPLACE(*YES) DBGVIEW(*SOURCE)</p>
            <p> </p>
            <p>CALL PGM(&lt;<span>CFTPGM</span>&gt;/I_ACCNT24)</p>         </td>
      </tr>
   </tbody>
</table>
