{
    "title": "Exits in Transfer CFT z/OS",
    "linkTitle": "Exits in Transfer CFT z/OS",
    "weight": "270"
}When running under Central Governance, you can use but not manage your Transfer CFT exits. To manage exits, use the information to manually configure as described in this section.

##  Using the DLL mode for Transfer CFT exits 

Transfer CFT exits that are written in COBOL, C language, or Assembler must be used in DLL mode. The advantages of this mode are:

-   You do not need to recreate the LINK-EDIT when you change Transfer CFT versions
-   You can mix using Assembler COBOL and C programs
-   All Transfer CFT API are supported
-   The ETEBAC3 protocol is obsolete, so samples for the ETEBAC3 exits are no longer available

## Create exits in Assembler

To create exits with Assembler, access the following files:

-   cftv2.SAMPLEA(AEX\*DLL):

    Samples for the ACCESS (AEXADLL), CATALOG (AEXEDLL), or FILE (AEXFDLL) are provided, and contain the steps required for a Transfer CFT EXIT:

> -   The main entry point, called ‘callexig\*’, is exported and is called by the Transfer CFT EXIT loader.
> -   The init function, the name is free, and samples are using EXEAINI, EXEINI, and EXFINI names. The init function returns the Transfer CFT EXIT run function address.
> -   The run function, the name is free, and samples use EXAXMP1, EXEXMP1, and EXFXMP1 names.
> -   Exits must be compiled with the GOFF assembler option.
> -   An example of the call to Transfer CFT APIs within an exit is provided in the AEXEDLL sample.

-   distlib.MAC (AEX\*UST):
    -   Macro containing the DSECTs of the exchange areas with the Transfer CFT. Macros AEXAUST, AEXEUST, and AEXFUST are provided. Be sure to use the same value for VERSION= in the CFTEXIT as in the macro expansion.
-   distlib.CNTL(LINKEXDL):
    -   Imports functions for a LINK-EDIT DLL.
-   distlib.CNTL (LINRDXGn):
    -   Transfer CFT modules for various Transfer CFT exits. The value for ‘n’ may vary from 0 to 9. Use the naming conventions in the following table.

 

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Main exported EPA</th>
         <th>DLL name </th>
         <th>CFTEXIT PROG=value</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>calllexig0	         </td>
         <td>CFTDXG0	         </td>
         <td>CFTEXIG0         </td>
      </tr>
      <tr>
         <td>callexig1	         </td>
         <td>CFTDXG1	         </td>
         <td>CFTEXIG1         </td>
      </tr>
      <tr>
         <td>And up to callexig9         </td>
         <td>And up to CFTDXG9         </td>
         <td>up to CFTEXIG9         </td>
      </tr>
   </tbody>
</table>

-   Exits must be linked with CALL,REUS=RENT,DYNAM=DLL,CASE=MIXED options.
-   Only the customer code is linked, and the Transfer CFT interfaces imported. For example:

`*  CFT/MVS file EXIT - DLL versionSETOPT  PARM(CALL,REUS=RENT,DYNAM=DLL,CASE=MIXED)* Customer codeINCLUDE   USER(AEXFDLL) ** the exit* Import EXIT support codeIMPORT    CODE,CFTDMAI,'exfrun1'MODE       AMODE(31)MODE       RMODE(ANY)NAME       CFTDXG5(R)`

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>File </th>
         <th>Definition</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>AEX*DLL</p>
         </td>
         <td>
            <p>Sample  program in Assembler. This sample provides the 3 steps needed in a Transfer CFT exit.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>AEX*UST </p>
         </td>
         <td>
            <p>Macro containing the DSECTs of the exchange areas with the Transfer CFT.</p>
         </td>
      </tr>
   </tbody>
</table>

## Create exits in C

To create exits with C, access the following files:

-   cftv2.SAMPLEC(CEX\*DLL):

    Samples for the ACCESS (CEXADLL), Beginning-of-Transfer(CEXBDLL), CATALOG (CEXEDLL), or FILE (CEXFDLL) are provided, and contain the steps required for a Transfer CFT EXIT:

    -   The main entry point, ‘`callexig*`’, is exported and is called by the Transfer CFT EXIT loader.
    -   The init function, where the name is free, and samples use the EXAINI, EXEINI, EXFINI and EXBINI names. The `init `function returns the Transfer CFT EXIT run function address.
    -   The run function, where the name is free, and samples use the EXAXMP1, EXEXMP1, EXFXMP1, and EXBXMP1 names.
    -   Exits must be compiled with the options: LANG(EXTENDED), RENT, DLL, LONGNAME.
    -   An example of a call to Transfer CFT APIs within an exit is provided in the CEXEDLL sample.

-   distlib.H (\*xeus)

-   distlib.CNTL(LINKEXDL):
    -   Sample import functions for a LINK-EDIT DLL

-   distlib.CNTL (LINRDXGn):
    -   Transfer CFT modules for various Transfer CFT exits. The value for ‘n’ may vary from 0 to 9. Use the naming conventions in the following table.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Main exported EPA</th>
         <th>DLL name</th>
         <th>CFTEXIT PROG=value</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>calllexig0 	         </td>
         <td>CFTDXG0          </td>
         <td>	CFTEXIG0         </td>
      </tr>
      <tr>
         <td>callexig1         </td>
         <td>CFTDXG1         </td>
         <td>CFTEXIG1         </td>
      </tr>
      <tr>
         <td>And up to callexig9         </td>
         <td>And up to CFTDXG9         </td>
         <td>Up to CFTEXIG9         </td>
      </tr>
   </tbody>
</table>

-   Exits must be linked with CALL, REUS=RENT, DYNAM=DLL, CASE=MIXED options.
-   Only the customer code is linked, and the Transfer CFT interface imported. For example:

**`* CFT/zos exit TYPE=FILE- DLL version`**  
**`SETOPT PARM(CALL,REUS=RENT,DYNAM=DLL,CASE=MIXED)`**  
**`* Customer code`**  
**`INCLUDE USER(CEXFDLL) ** the exit`**  
**`* Import EXIT support code`**  
**`IMPORT CODE,CFTDMAI,'exfrun1'`**  
**`MODE AMODE(31)`**  
**`MODE RMODE(ANY)`**  
**`NAME CFTDXG5(R)`**

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>File 	</th>
         <th>Definition</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>CEX*DLL	         </td>
         <td>Sample program in C. This sample provides the 3 steps needed in a Transfer CFT exit.         </td>
      </tr>
      <tr>
         <td>*XEUS          </td>
         <td>The 	header containing the structure of the exchange areas with the Transfer CFT.         </td>
      </tr>
   </tbody>
</table>

## Create exits in COBOL

To create exits with Cobol, access the following files:

-   cftv2.SAMPLEO(OEX\*DLL):

    Samples for the ACCESS (OEXADLL), CATALOG (OEXEDLL), or FILE (OEXFDLL) are provided, and contain the steps required for a Transfer CFT EXIT:

    -   The main entry point, called ‘callexig\*’, is exported and is called by the Transfer CFT EXIT loader.

    -   The init function, the name is free, and samples are using EXAINI, EXEINI, and EXFINI names. The init function returns the Transfer CFT EXIT run function address.

    -   The run function, the name is free, and samples use EXAXMP1, EXEXMP1, and EXFXMP1 names.

    -   Exits must be compiled with options:

        NODYNAM,RENT,LIB,DLL,OBJECT,APOST,DATA(31)

        PGMNAME(LONGMIXED),EXPORTALL

    -   An example of the call to Transfer CFT APIs within an exit is provided in the OEXEDLL sample.

-   distlib.COPY(OEX\*UST): for exit format V23

-   distlib.COPY(OEX\*240): for exit format V24

<!-- -->

-   distlib.CNTL(LINKEXDL):
    -   sample Imports functions for a LINK-EDIT DLL
-   distlib.CNTL (LINRDXGn):
    -   Transfer CFT modules for various Transfer CFT exits. The value for ‘n’ may vary from 0 to 9. Use the naming conventions in the following table.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Main exported EPA</th>
         <th>DLL name</th>
         <th>CFTEXIT PROG=value</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>calllexig0          </td>
         <td>CFTDXG0         </td>
         <td>CFTEXIG0         </td>
      </tr>
      <tr>
         <td>callexig1         </td>
         <td>CFTDXG1         </td>
         <td>CFTEXIG1         </td>
      </tr>
      <tr>
         <td>And up to callexig9         </td>
         <td>And up to CFTDXG9         </td>
         <td>Up to CFTEXIG9         </td>
      </tr>
   </tbody>
</table>

-   Exits must be linked with CALL,REUS=RENT,DYNAM=DLL,CASE=MIXED options.
-   Only the customer code is linked, and the Transfer CFT interfaces imported. For example:

`* CFT/zos exit TYPE=FILE- DLL versionSETOPT PARM(CALL,REUS=RENT,DYNAM=DLL,CASE=MIXED)* Customer codeINCLUDE USER(OEXFDLL) ** the exit* Import EXIT support codeIMPORT CODE,CFTDMAI,'exfrun1'MODE AMODE(31)MODE RMODE(ANY)NAME CFTDXG5(R)`

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>File 	</th>
         <th>Definition</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>	OEX*DLL	         </td>
         <td>Sample program in C. This sample provides the 3 steps needed in a Transfer CFT exit.         </td>
      </tr>
      <tr>
         <td>OEX*UST	         </td>
         <td>Copy book containing the structure of the exchange areas with the Transfer CFT (format V23).         </td>
      </tr>
      <tr>
         <td>OEX*240	         </td>
         <td>Copy book containing the structure of the exchange areas with the Transfer CFT (format V24).         </td>
      </tr>
   </tbody>
</table>

## Call APIs in exits

Calls to APIs, for catalog query and request deposits to Transfer CFT, are supported in exits. It is recommended that you use DLL support.

Calls to a Transfer CFT synchronous API are only supported in DLL.

**Exit examples summary for COBOL**

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <td>
            <p>Source file</p>
            <p>cftv2.</p>
            <p>SAMPLEx</p>
         </td>
         <td>
            <p>Jcl compilation</p>
            <p>cftv2.</p>
            <p>INSTALL </p>
         </td>
         <td>
            <p>Command file </p>
            <p>for link-edit </p>
            <p>distlib.CNTL</p>
         </td>
         <td>
            <p>Jcl for link-edit cftv2.</p>
            <p>INSTALL</p>
         </td>
         <td>
            <p>DLL name</p>
         </td>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>OEXADLL</p>
         </td>
         <td>
            <p>I91APICP</p>
         </td>
         <td>
            <p>LINRDXG6</p>
         </td>
         <td>
            <p>LINKEXLE</p>
         </td>
         <td>
            <p>CFTDXG6</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>OEXEDLL</p>
         </td>
         <td>
            <p>I91APICP</p>
         </td>
         <td>
            <p>LINRDXG7</p>
         </td>
         <td>
            <p>LINKEXLE</p>
         </td>
         <td>
            <p>CFTDXG7</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>OEXFDLL</p>
         </td>
         <td>
            <p>I91APICP</p>
         </td>
         <td>
            <p>LINRDXG8</p>
         </td>
         <td>
            <p>LINKEXLE</p>
         </td>
         <td>
            <p>CFTDXG8</p>
         </td>
      </tr>
   </tbody>
</table>

**Exit examples summary for C language**

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <td>
            <p>Source file</p>
            <p>cftv2.</p>
            <p>SAMPLEx</p>
         </td>
         <td>
            <p>Jcl compilation</p>
            <p>cftv2.</p>
            <p>INSTALL </p>
         </td>
         <td>
            <p>Command file </p>
            <p>for link-edit </p>
            <p>distlib.CNTL</p>
         </td>
         <td>
            <p>Jcl for link-edit cftv2.</p>
            <p>INSTALL</p>
         </td>
         <td>
            <p>DLL name</p>
         </td>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>CEXADLL</p>
         </td>
         <td>
            <p>I91APICP</p>
         </td>
         <td>
            <p>LINRDXG0</p>
         </td>
         <td>
            <p>LINKEXLE</p>
         </td>
         <td>
            <p>CFTDXG0</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CEXEDLL</p>
         </td>
         <td>
            <p>I91APICP</p>
         </td>
         <td>
            <p>LINRDXG1</p>
         </td>
         <td>
            <p>LINKEXLE</p>
         </td>
         <td>
            <p>CFTDXG1</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CEXFDLL</p>
         </td>
         <td>
            <p>I91APICP</p>
         </td>
         <td>
            <p>LINRDXG2</p>
         </td>
         <td>
            <p>LINKEXLE</p>
         </td>
         <td>
            <p>CFTDXG2</p>
         </td>
      </tr>
      <tr>
         <td>CEXBDLL            </td>
         <td>I91APICP            </td>
         <td>LINRDXG9            </td>
         <td>LINKEXLE             </td>
         <td>CFTDXG9         </td>
      </tr>
   </tbody>
</table>

**Exit examples summary for Assembler**

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <td>
            <p>Source file</p>
            <p>cftv2.</p>
            <p>SAMPLEx</p>
         </td>
         <td>
            <p>Jcl compilation</p>
            <p>cftv2.</p>
            <p>INSTALL </p>
         </td>
         <td>
            <p>Command file </p>
            <p>for link-edit </p>
            <p>distlib.CNTL</p>
         </td>
         <td>
            <p>Jcl for link-edit cftv2.</p>
            <p>INSTALL</p>
         </td>
         <td>
            <p>DLL name</p>
         </td>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>AEXADLL</p>
         </td>
         <td>
            <p>I91APICP</p>
         </td>
         <td>
            <p>LINRDXG4</p>
         </td>
         <td>
            <p>LINKEXLE</p>
         </td>
         <td>
            <p>CFTDXG4</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>AEXEDLL</p>
         </td>
         <td>
            <p>I91APICP</p>
         </td>
         <td>
            <p>LINRDXG3</p>
         </td>
         <td>
            <p>LINKEXLE</p>
         </td>
         <td>
            <p>CFTDXG3</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>AEXFDLL</p>
         </td>
         <td>
            <p>I91APICP</p>
         </td>
         <td>
            <p>LINRDXG5</p>
         </td>
         <td>
            <p>LINKEXLE</p>
         </td>
         <td>
            <p>CFTDXG5</p>
         </td>
      </tr>
   </tbody>
</table>
