{
    "title": "Upgrade a multi-node architecture",
    "linkTitle": "Upgrade multi-node architecture",
    "weight": "240"
}This section describes the upgrade of an instance of Transfer CFT z/OS configured in multi-node.

## Prerequisite

You must first perform Steps 1 through 5 as described in the [Upgrade](transfercft/cft_intro_install/about_this_document_zos/upgrade_prereqs_zos/upgrade) section to the target instance.

## Upgrade the CATALOG files (MIGRCAT)

The MIGRCAT procedure migrates one catalog file at a time. The procedure must be modified and executed for each of the nodes.

Customize the PMIGR2 step of the JCL MIGRCAT as follows, where you define RECNB, NODE, OLDFIL, TMPFIL and NEWFIL, replacing X with the node number.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p><span>//PMIGR</span><span>2  EXEC</span><span> PMIGR2,XEXPORT=&amp;XEXPORT,</span></p>
            <p>//     OUT=&amp;OUT,</p>
            <p>//     UNIT=&amp;CFTUNIT,</p>
            <p>//     CFTLOAD=&amp;CFTLOAD,</p>
            <p>//     OLDEXEC=&amp;OLDEXEC,</p>
            <p>//     SPACE=&amp;SEP&amp;TMPSCAT&amp;SEP,</p>
            <p>//     SER='DK231F',</p>
            <p>//     SPACE=&amp;SEP&amp;TMPSCAT&amp;SEP,</p>
            <p><span>//   <span>  NODE='X',                  =&gt; node id x   </span></span></p>
            <p><span>//     </span><span>OLDFIL=Source.CATALOG.N0</span><span>X</span><span>, =&gt; Source CATALOG </span><span>node</span><span> 0X       </span></p>
            <p><span>//     </span><span>TMPFIL=</span><span>Prefix.WORK.CATALOG.N0</span><span>X</span><span>,   </span><span>=&gt; Temporary file (size defined by &amp;TMPSCAT)</span></p>
            <p><span>//     </span><span>NEWFIL=Target.CATALOG.N0</span><span>X</span><span>, =&gt; Target CATALOG node 0X    </span></p>
            <p><span>//     </span><span>RECNB=</span><span>50000</span><span>,   </span><span>            =&gt; Target CATALOG records number (to be customized)</span></p>
            <p>//     DISPFIL=&amp;DISPCAT,</p>
            <p>//     HABFNAME='NO'</p>
            <p> </p>         </td>
      </tr>
   </tbody>
</table>

Submit the procedure ..INSTALL(MIGRCAT).

## Upgrade the communication media files

The MIGRCOM procedure migrates one media file at a time. The procedure must therefore be modified and executed for each of the nodes and for the main communication medium.

### Upgrade the main communication media file

Customize the PMIGR2 step of the MIGRCOM procedure and set the variables RECNB, OLDFIL, TMPFIL and NEWFIL as follows:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>//PMIGR2  EXEC PMIGR2,XEXPORT=&amp;XEXPORT,</p>
            <p>//     OUT=&amp;OUT,</p>
            <p>//     UNIT=&amp;CFTUNIT,</p>
            <p>//     CFTLOAD=&amp;CFTLOAD,</p>
            <p>//     OLDEXEC=&amp;OLDEXEC,</p>
            <p>//     SPACE=&amp;SEP&amp;TMPSCOM&amp;SEP,</p>
            <p>//     SER='DK231F',</p>
            <p>//     OLDFIL=Source.COM,   =&gt; Source MAIN COM</p>
            <p>//     TMPFIL=Prefix.WORK.COM,     =&gt; Temporary file (size defined by &amp;TMPSCOM)</p>
            <p>//     NEWFIL=Target.COM,   =&gt; Target MAIN COM </p>
            <p>//     RECNB=5000,          =&gt; Target MAIN COM records number (to be customized)</p>
            <p>//     DISPFIL=&amp;DISPCOM,</p>
            <p>//     HABFNAME='NO'</p>         </td>
      </tr>
   </tbody>
</table>

Submit the procedure ..INSTALL(MIGRCOM).

## Upgrade the nodes (node x) communication media file

The following steps must be performed for each of the nodes.

Customize the PMIGR2 parameters in the JCL MIGRCOM:

Define the variables RECNB, OLDFIL, TMPFIL and NEWFIL. Replace X with the node number.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>//PMIGR2  EXEC PMIGR2,XEXPORT=&amp;XEXPORT,</p>
            <p>//     OUT=&amp;OUT,</p>
            <p>//     UNIT=&amp;CFTUNIT,</p>
            <p>//     CFTLOAD=&amp;CFTLOAD,</p>
            <p>//     OLDEXEC=&amp;OLDEXEC,</p>
            <p>//     SPACE=&amp;SEP&amp;TMPSCOM&amp;SEP,</p>
            <p>//     SER='DK231F',</p>
            <p>//     OLDFIL=Source.COM.N0<span>X</span>,  =&gt; Source COM node <span>0X </span>       </p>
            <p>//     TMPFIL=Prefix.WORK.MCOM.N0X, =&gt; Temporary file (size defined by &amp;TMPSCOM) </p>
            <p>//     NEWFIL=Target.COM.N0X,  =&gt; Target COM node <span>0X</span></p>
            <p>//     RECNB=5000,             =&gt; Target COM node <span>0X</span> records number (to be customized)</p>
            <p>//     DISPFIL=&amp;DISPCOM,</p>
            <p>//     HABFNAME='NO'</p>         </td>
      </tr>
   </tbody>
</table>

Submit the procedure ..INSTALL(MIGRCOM).

## Customize the JCL ..INSTALL(MNRMON)

Set the Transfer CFT submission option, by STC or JCL, as for the source instance.

## Customize the procedure ..INSTALL(PCFTUTIL) and INCLUDE(CFTINC)

Comment the following lines:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>//*CFTCAT DD DISP=SHR,
            <p>//* DSN=&amp;QUAL..CATALOG</p>         </td>
      </tr>
   </tbody>
</table>
