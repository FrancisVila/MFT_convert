{
    "title": "Transport security and PKIUTIL commands",
    "linkTitle": "Transport security and PKIUTIL commands",
    "weight": "260"
}This section describes SSL security parameters. For more information on transport security concepts, refer to the Security sub-book in the *Transfer* CFT documentation.

## Certificates

Refer to the [Transfer CFT User Guide](https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/AxwayStartPage.htm) for more information on certificates.

## Configuration changes

You must define certain elements in the product configuration if you want to use transfer security. See the delivered samples in CFTPGM/CFTSRC(TCPPARAM).

To use the PKIUTIL utility:

1.  Access the Transfer CFT Main Menu screen. In the Main Menu enter the command cft and press Enter to open the Manager Menu.
2.  Select option **2. Security commands**. Then select option **2. Interpret Security configuration** and enter the member you want to interpret. By default this is the PKIBASE member in the UTIN file in CFTPROD library.
3.  To edit the security configuration file selection option 2. Security commands then option 1. Edit Security configuration file and enter the member you want to edit. By default it is the PKIBASE member in the UTIN file in CFTPROD library.

## Submitting PKIUTIL commands

Select option **2. Security commands**, and then** 3. PKIUTIL operation** in the Operations screen to start the PKUTIL session.

This option allows you to use the keyboard to enter and execute PKIUTIL commands.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>PKIU20I</p>
<p>PKIU20I PKI</p>
<p>PKIU20I Version 3.2.4 2017/02/02</p>
<p>PKIU20I (C) Copyright AXWAY 1989-2017</p>
<p>PKIU20I ====&gt; Starting Session on 03/03/2017 Time is 16:20:37</p>
<p>PKIU20I</p>
<p> </p>
<p>===&gt; LISTPKI</p></td>
</tr>
</tbody>
</table>

## Create a database

Use the following commands, in order, to create a database:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>PKIFILE MODE=CREATE, FNAME= 'CFTPROD/PKIBASE'</td>
</tr>
</tbody>
</table>

 

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>PKICER ID=NEWCA, MODE=CREATE, PKIFNAME=CFTPROD/PKIBASE, ITYPE=ROOT,</p>
<p>INAME=CFTPROD/AXWRCA, IFORM=DER, STATE=ACT</p></td>
</tr>
</tbody>
</table>

 

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>PKICER ID=NEWUSER,MODE=CREATE, PKIFNAME=CFTPROD/PKIBASE, INAME=CFTPROD/MFTUSRCA, IKNAME=CFTPROD/MFTUSRCAK, ITYPE=USER,</p>
<p>IKPASSW=user, STATE=ACT, ROOTCID=NEWCA, IKFORM=DER</p></td>
</tr>
</tbody>
</table>

### List PKI Internal datafiles contents

1.  To list the PKI internal datafiles  contents, enter the command: LISTPKI
2.  Press ENTER to execute the command.

A correct execution displays the following messages:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>&gt; LISTPKI<br />
1:¬PKU|<br />
Date = 03/03/2017 Time = 16:24:43<br />
PKI Fname =</p>
<p> </p>
<p>Id.     Root   T S C K E   Exp.Date   Delivered to   Delivered by<br />
------- -----  - - - - -  ---------- ------------- ---------------</p>
<p>CAXMP CAXMP   R A x      19/12/2017 CA SAMPLE FOR CA SAMPLE FOR CLIENT</p>
<p>CAXMP         U A x x    18/12/2017 CLIENT SAMPLE CA SAMPLE FOR SERVER</p>
<p>CAXMP         U A x x    18/12/2017 SERVER SAMPLE CA SAMPLE</p>
<p> </p>
<p>PKIU00I LISTPKI _ Correct ()</p></td>
</tr>
</tbody>
</table>
