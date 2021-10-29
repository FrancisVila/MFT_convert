{
    "title": "Rollback upgrade and restore the catalog",
    "linkTitle": "Rollback upgrade and restore catalog",
    "weight": "250"
}## Prerequisites

-   You must have made a backup of the environment prior to the upgrade you are rolling back.
-   Upgraded from Transfer CFT 3.4 or higher to Transfer CFT 3.9

## Procedure

1.  Export all catalogs. Base your export procedure on the following example:  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>// EXPORT SYMLIST=(CFTCAT)</p>
                <p>// SET CFTCAT=current.CFT.CATALOG (to be customized)</p>
                <p>// SET TMPCAT=CFTWRK.TMPCAT (to be customized)</p>
                <p>//* -------------------</p>
                <p>//* Export catalog</p>
                <p>//* -------------------</p>
                <p>//EXPCAT EXEC PGM=CFTMI24B,REGION=32M</p>
                <p>//STEPLIB DD DISP=SHR,DSN=current.CFT.LOAD</p>
                <p>//TMPCAT DD DISP=(,CATLG),</p>
                <p>// DSN=&amp;TMPCAT</p>
                <p>// DCB=(LRECL=4120,RECFM=VB,BLKSIZE=27998),</p>
                <p>// SPACE=(CYL,(50,10),RLSE) (to be customized)</p>
                <p>//CEEDUMP DD SYSOUT=*</p>
                <p>//CFTOUT DD SYSOUT=*</p>
                <p>//CFTIN DD DATA,SYMBOLS=(JCLONLY)
    MIGR TYPE=CAT,DIRECT=FROMCAT,OFNAME=DD:TMPCAT,
    IFNAME='&amp;CFTCAT'</p>
                <p>/*</p>         </td>
          </tr>
       </tbody>
    </table>
2.  Perform a version rollback as described in [Upgrade version rollback](#Upgrade) below.
3.  Recreate the catalogs and re-import the catalogs. Base your procedure on the following example:  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>// EXPORT SYMLIST=(CFTCAT)</p>
                <p>// SET CFTCAT=current.CFT.CATALOG (to be customized)</p>
                <p>// SET TMPCAT=CFTWRK.TMPCAT (to be customized)</p>
                <p>//* -----------------</p>
                <p>//* Import catalog</p>
                <p>//* -----------------</p>
                <p>//IMPCAT EXEC PGM=CFTMI24B,REGION=32M</p>
                <p>//STEPLIB DD DISP=SHR,DSN=&amp;LOAD</p>
                <p>//TMPCAT DD DISP=SHR,DSN=&amp;TMPCAT</p>
                <p>//CEEDUMP DD SYSOUT=*</p>
                <p>//CFTOUT DD SYSOUT=*</p>
                <p>//CFTIN DD DATA,SYMBOLS=(JCLONLY)
    MIGR TYPE=CAT,DIRECT=TOCAT,IFNAME=DD:TMPCAT,
    OFNAME='&amp;CFTCAT'</p>
                <p>/*</p>         </td>
          </tr>
       </tbody>
    </table>

## <span id="Upgrade"></span>Upgrade version rollback

The following procedure enables you to rollback to the previous state if you have applied a SP or patch. This is useful if there is an incident during the application of a PTF, or when validating a patch.

1.  Use the A13RBACK
2.  Use the A13RBACK to restore the executable file library, USS Copilot and USS Secure Relay environment. This JCL executes the following three JCLs:
    -   A13RSTOR: Restores the Transfer CFT Load library.
    -   A13UCOPR: Restores the Transfer CFT USS Copilot environment.
    -   A13UXSRR: Restores the Transfer CFT USS Secure Relay environment.
