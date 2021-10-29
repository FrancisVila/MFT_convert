{
    "title": "Customize the z/OS installation",
    "linkTitle": "Customize the z/OS installation",
    "weight": "230"
}Each target environment corresponds to a Transfer CFT. This topic describes the specific Transfer CFT customization. Transfer CFT customization is application dependent, as opposed to the target environment, which is system dependent.

## JCL CFTENV (include member)

This member is customized during installation phase. It contains a list of JCL SET commands concerning the current instance, CFTENV must be included when PCFTUTIL and PCFTUTL procedures are used.

For z/OS 2.1, you can export JCL variables:

Export Global

Uncomment //\* EXPORT SYMLIST=\* in CFTENV member

Or

Before INCLUDE MEMBER=CFTENV add directives

// EXPORT SYSMLIST=\*

// INCLUDE MEMBER=CFTENV

Example:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>// LIB JCLLIB ORDER=(MY.CFTPROD.PROCLIB)</p>
<blockquote>
            <p>// EXPORT SYSMLIST=*</p>
            <p>// INCLUDE MEMBER=CFTENV</p>
            <p>//CFTSND EXEC PCFTUTIL,PARM='',QUAL=&amp;CFTENV,OUT=&amp;OUT</p>
            <p>//CFTPARM DD DUMMY to optimize</p>
            <p>//CFTIN DD *,SYMBOLS=(CNVTSYS,SUBSLOG)</p>
            <p>SEND PART=PARIS,IDF=BIN,</p>
            <p>FNAME=&amp;CFTENV..FTEST,</p>
            <p>IDA=’&amp;SYSNAME-&amp;ZOSLVL-&amp;SYSCLONE’</p>
            <p>/*</p>
</blockquote>         </td>
      </tr>
   </tbody>
</table>

## JCL CFTINC (include member)

You can use the CFTINC member in an INCLUDE statement to reference a list of Transfer CFT file allocation statements.

Example:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>// LIB JCLLIB ORDER=(MY.CFTPROD.PROCLIB</p>
            <p>//  INCLUDE MEMBER=CFTENV</p>
            <p>//STREX EXEC PGM=IKJEFT01,REGION=32M,PARM='%REX4CFT'</p>
            <p>//STEPLIB DD DISP=SHR,DSN=&amp;CFTLOAD</p>
            <p>//SYSPROC DD DISP=SHR,</p>
            <p>//  DSN=MY.SYSPROC</p>
            <p>//SYSTSPRT DD SYSOUT=&amp;OUT</p>
            <p>//SYSTSIN DD DUMMY</p>
            <p>//    SET QUAL=&amp;CFTENV</p>
            <p>//    <span>INCLUDE MEMBER=CFTINC</span></p>         </td>
      </tr>
   </tbody>
</table>

## PCFTUTIL / PCFTUTL procedures

It is recommended that you use only procedures to access the Transfer CFT utilities.

We provide two procedure examples:

-   PCFTUTIL: All Transfer CFT files are allocated, except for the PKI database and LOG.
-   PCFTUTL: Same procedure that PCFTUTIL, but CATALOG, COM, PART, PARM file are not allocated.

These procedures are customized during installation phase.

To run a CFTUTIL executable (default), for example:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>//LIB JCLLIB ORDER=(MY.CFTPROD.PROCLIB)</p>
            <p>//   INCLUDE MEMBER=CFTENV</p>
            <p>//ABOUT EXEC PCFTUTL,PARM='ABOUT TYPE=CFT',</p>
            <p>//   QUAL=&amp;CFTENV</p>         </td>
      </tr>
   </tbody>
</table>

To run another CFTUTIL executable, for example CFTPKI:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>//LIB JCLLIB ORDER=(MY.CFTPROD.PROCLIB)</p>
            <p>//  INCLUDE MEMBER=CFTENV</p>
            <p>//LISPKI EXEC PCFTUTL,PG=CFTPKI,PARM='',</p>
            <p>//  QUAL=&amp;CFTENV</p>
            <p>//MYPKI DD DISP=SHR,DSN=&amp;CFTENV..PKIFILE</p>
            <p>//CFTIN DD *</p>
            <p>LISTPKI PKIFNAME = $MYPKI,CONTENT=FULL</p>
            <p>/*</p>         </td>
      </tr>
   </tbody>
</table>

### Recommendations to ease application migration

This section describes the migration of applications using Transfer CFT utilities.

It is recommended as far as possible not to point directly to the product libraries and work through procedures.

To do this, copy the following members into a specific PROCLIB:

-   CFTENV
-   CFTINC
-   PCFTUTIL
-   PCFTUTL

When changing the Transfer CFT version, you should get the new version of these members. A rollback is done by copying the backups of these members. This also applies to the end-of-transfer procedures.

## <span id="JOB H80EXEC"></span>Miscellaneous JCL templates

The target.EXEC library contains an example of Transfer CFT procedures:

-   EXECSF: End of file send procedure
-   EXECRF: End of file reception procedure
-   SWIACC: Procedure submitted when SWITCHING the Transfer CFT accounting file
-   SWILOG: Procedure submitted when switching the Transfer CFT log file
-   EXECCRON: Procedure submitted by a CFTCRON command
-   COPXLOG: Sample of JCL submitted by Transfer CFT Navigator (with dynamic parameter)
-   COPEXT: Sample of JCL submitted by Transfer CFT Navigator to extract Transfer CFT parameter in a file
-   CFTHEART: HEARTBEAT JCL for SENTINEL dashboards
-   SNTLEXEC: End of file reception procedure including SENTINEL
-   TFCIPH: Transfer CFT Preprocessing script for TrustedFile
-   TFDCIPH: Transfer CFT End of transfer script for TrustedFile
-   TFDELFIL: Transfer CFT Send exec script for TrustedFile
-   CA7POST: Indicates to CA7 that the creation of a data set has completed
-   COPYFILR and COPYFILS: templates that use the COPYFILE command
-   CRONSTAR: Sample of the JCL that is submitted at Transfer CFT STARTUP
-   CRONSHUT: Sample of the JCL that is submitted at Transfer CFT shutdown
-   EXECIDF: End of file reception procedure sample with conditional steps
-   EXECIFD2: The value of the IDF is checked among a list of values ​​by a REXX that sets a return code
-   EXECIDF3: The JCL is conditional and uses the )SEL and )ENDSEL syntax - see [Syntax for )SEL and )ENDSEL](#Syntax)

These procedures are customized during the A00CUSTO phase.

### <span id="Syntax"></span>Syntax for )SEL and )ENDSEL

#### )SEL argument1 op argument2

At least one space is mandatory between the arguments and operator.

The test is systematically performed on the length of the first argument, enabling generic arguments to be compared if necessary.

The maximum number of nested )SELs is 32, where:

-   argument = constant, variable in the &xxx format
-   op = condition operator

> = EQU or EQ: equal to

> &gt; or GT: greater than
>
> &lt; or LT: less than
>
> &gt;= or GTE: greater than or equal to
>
> &lt;= or LTE: less than or equal to
>
> &lt;&gt; or != or |= or NEQ: different from

Examples

)SEL &P1 = SITE1: includes the following cards if parameter 1 is equal to SITE1

)SEL AG = &P1: includes the following cards if parameter 1 starts with AG

)SEL AG &lt;&gt; &P2: includes the following cards if parameter 2 does not start with AG

#### )ENDSEL

The )ENDSEL card does not contain any arguments.

The appropriate number of )ENDSELs required to terminate all active )ENDSELs are automatically added at the end of the JCL.

## Update the unified configuration file CFT$SET

The JCL CFT$SET, located in the target.INSTALL library, updates the unified configuration file and creates a Transfer CFT parameters sample (..SAMPLE(CFTPARM)) from a template (..SAMPLE(ZCFTPARM)).

The parameters in this JCL were customized during the (A00CUSTO) process, while customizing the CFTENV file (JCL variables).

List of updated variables:

-   cft.runtime\_dir
-   cft.full\_hostname
-   cft.state\_compat
-   cft.listcat\_compat
-   cft.instance\_id
-   cft.instance\_group
-   samples.pesitany\_sap.value
-   samples.pesitssl\_sap.value
-   samples.coms\_port.value

You can run the JCL multiple times, once to create the member .. SAMPLE (CFTPARM), which the procedure does not modify.

## <span id="D40INIT"></span>Format Transfer CFT work files <span id="kanchor40"></span>D40INIT

The JOB D40INIT prepares the Transfer CFT z/OS files. Before submitting this JOB, adapt the following points to the requirements of the operating service:

-   File names (if the default values in the samples are not usable)
    -   By default file names are defined in JCL INCLUDE=CFTENV

<!-- -->

-   The values of the parameters RECNB and FSPACE

The following data is required to use the basic Transfer CFT installation customization parameters. These work files are:

-   CFTPARM: VSAM KSDS file, Transfer CFT parameters descriptions

<!-- -->

-   CFTPART: VSAM KSDS file, Transfer CFT partners description

<!-- -->

-   CFTCAT: VSAM ESDS file, Transfer CFT catalog

<!-- -->

-   CFTLOG1: Sequential file used as the log file by Transfer CFT

<!-- -->

-   CFTLOG2: Sequential file used by Transfer CFT as the alternate log file

<!-- -->

-   CFTACNT1: Sequential file used as the account file by Transfer CFT

<!-- -->

-   CFTACNT2:  Sequential file used by Transfer CFT as the alternate account file

<!-- -->

-   CFTCOM: VSAM ESDS file used by Transfer CFT as a buffer for the Transfer CFT commands submitted by CFTUTIL, a BATCH program, a TSO user, the Transfer CFT Copilot, or the Transfer CFT UI

## <span id="JOB E50PARM CFTPARM"></span>CFTPARM configuration update <span id="kanchor41"></span>E50PARM

The JCL E50PARM, located in the target.INSTALL library, updates the Transfer CFT configuration PARAM and PART files (PARM step).

To activate the SFTP parameters:

1.  -   In the CFTPARM MEMBER, uncomment the `/*   sftp,sftpcli, */` line.

2.  -   Uncomment the following:
        -   //\* DD DISP=SHR,
        -   //\* DSN=<u>&QUAL</u>..SAMPLE(CFTSFTP)

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>E50PARM</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>//PARM EXEC PCFTUTIL,</p>
            <p>// PARM='',</p>
            <p>// QUAL=&amp;CFTENV,OUT=&amp;OUT</p>
            <p>//CFTIN DD DISP=SHR,</p>
            <p>// DSN=&amp;QUAL..SAMPLE(CFTPARM)</p>
            <p>//*     DD DISP=SHR,</p>
            <p>//* DSN=&amp;QUAL..SAMPLE(CFTSFTP)</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>The underlined parameters are substituted during the submit phase.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Use the JCL SAMPLE(PKIKEY) as an example for handling keys required for SFTP.
