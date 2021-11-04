{
    "title": "Programming interfaces",
    "linkTitle": "Build APIs and exits",
    "weight": "250"
}This section describes the Transfer CFT batch programming interfaces for Transfer CFT.

## Transfer CFT APIs in a z/OS environment

Transfer CFT APIs are described in the sub-book [Using APIs](../../using_apis). This programming interface can be accessed in the Assembler, COBOL and C programming languages.

Transfer CFT APIs use the DLL mode exclusively, with samples located in the following libraries:

-   cftv2.SAMPLEA for Assembler
-   cftv2.SAMPLEC for C
-   cftv2.SAMPLEO for COBOL

The programs are compiled with the main options:

-   RENT, GOFF, LIST(133) for Assembler
-   DLL, LONGNAME, RENT for C
-   DLL, RENT for COBOL NODYNAM

To LINK-EDIT a program that uses Transfer CFT services, you must import references called by the Transfer CFT user. Additionally, you require a JOBLIB/STEPLIB containing the LOAD-MODULE CFTDAPI and CFTDSCP for execution.

The usable imports list is defined in member distlib.CNTL(LINKAPID).

##  Programming examples

Samples are located in the CFTV2.SAMPLEA, SAMPLEO, or SAMPLEC files.

-   Assembler
    -   AAPIDLL: Uses CFTAI CFTAC
    -   AAPIUST: Selection area description ’macro’, catalog returned, and so on
-   COBOL NODYNAM
    -   OAPIC: Uses CFTC
    -   OAPII: Uses CFTI
    -   OAPIW: Deposit a request (using CFTU) and wait for the result (CFTI)
    -   OAPIX: Uses cftaix
    -   OAPISYN: Deposit of requests (VIA synchronous API, or communication)
-   Cobol Copybook
    -   OAPICST: Constants and common descriptions
    -   OAPIINF: Structure returned by function GETXINFO
    -   OAPIMSG: Structure of the message returned by cftau
-   OAPIUST: Global Copy book
    -   OAPISL: Selection area description (for compatibility)
    -   OAPICA: catalog area description returned (for compatibility)
    -   OAPICX: catalog area description returned by cftaix API (for compatibility)
-   OAPI24: Global Copy book - equivalent to OAPIUST (long fields)
    -   OAPISL4 : Selection area description (long fields)
    -   OAPICA4 : catalog area description returned (long fields)
    -   OAPICX4 : catalog area description returned by cftaix API (long fields)
-   Cobol Copybook API 2
    -   OCFTAPI2

### COBOL API subroutines called in static mode

#### COBOL DYNAM

This section describes the special use of COBOL compiled with the DYNAM option.

The DYNAM compile option is incompatible with the DLL option. To be able to use the CFT APIs, an interface (called 'OAPIFC') is provided. You must only call this interface one time, and return function pointers corresponding to DLL API entry points.

Implementation

1.  In the working storage section, add the copy book OCFTAPD2.
2.  In the procedure division, call the module 'OAPIFC' once:

if (ipc-loaded = zero) then

call 'OAPIFC' using ipc-par end-call

end-if

Syntax to call CFT APIs

Call cftu using parameters…

Call cfti using parameters…

Call cftc using parameters…

Etc.

In this case cftu, cfti, and cftc are defined as pointer functions (see OCFTAPD2).

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>If the pointers are not initialized by OAPIFC an abend 0C1 occurs.         </td>
      </tr>
   </tbody>
</table>

-   Delivered samples:  
    OAPIWS, OAPIIS, OAPICS, OPAIXS, OAPI2AS, OAPI2BS
-   Compilation options:  
    CBL DYNAM,RENT,DATA(31),NODLL,PGMNAME(LONGMIXED)
-   Link-edit model:  
    Example OAPIWS sample:  
    INCLUDE USER(OAPIWS)  
    MODE AMODE(31)  
    MODE RMODE(ANY)  
    NAME OAPIWS(R)

1.  To run the sample OAPIWS , use INSTALL(I93APIRN) and replace:  
    //OAPIW EXEC CFTAPI,PROG=OAPIW,APIP='SEND PART=PARIS,IDF=TXT'  
    By  
    //OAPIWS EXEC CFTAPI,PROG=OAPIWS,APIP='SEND PART=PARIS,IDF=TXT'

#### C

-   CAPIX: uses cftaix

<!-- -->

-   CAPII: use cfti

<!-- -->

-   CAPIW: Deposit of a request and wait for the result

<!-- -->

-   CAPIC: Uses CFTAI CFTAC CFTAU

<!-- -->

-   CAPISYN: Deposit of requests (VIA synchronous API, or communication file)

#### C Headers – API-C

-   CFTAPI (CAPIUST): Selection area description, returned catalog area description, and so on

<!-- -->

-   CFTD: Base API-C constants and type definitions 

<!-- -->

-   XTYPE

#### C Headers – API2-C

-   CFTAPI2 (CAPI2UST): Base2 API-C constants and type definitions.

The compile, link-edit, and run JCLs for these samples can be found in the CFTV2.INSTALL file and are called I91APICP, I92APILK and I93APIRN. The compile JOB must be customized to reflect your environment.

**Main delivered samples**

<table>
   <th>
      <tr>
<th>Language         </th>
<th><p>Source file</p>
<p>cftv2.SAMPLE*</p>         </th>
<th><p>Copy,</p>
<p>Macro,</p>
<p>Include used</p>         </th>
<th>API         </th>
<th>LINK EDIT command files (DLL) distlib.CNTL         </th>
<th>Load module         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p> </p>
COBOL NODYNAM
<p> </p>
<p> </p>
<p> </p>
<p> </p>         </td>
         <td><p>OAPIC</p>         </td>
         <td><p>OPAICST</p>         </td>
         <td><p>CFTC</p>         </td>
         <td><p>LINRDACO</p>         </td>
         <td><p>OPAIC</p>         </td>
      </tr>
      <tr>
         <td><p>OAPII</p>         </td>
         <td><p>OAPIUST or OAPI24</p>         </td>
         <td><p>CFTI</p>         </td>
         <td><p>LINRDAIO</p>         </td>
         <td><p>OAPII</p>         </td>
      </tr>
      <tr>
         <td><p>OAPIW</p>         </td>
         <td><p>OAPIUST or OAPI24</p>         </td>
         <td><p>CFTI</p>
<p>CFTU</p>         </td>
         <td><p>LINRDAWO</p>         </td>
         <td><p>OAPIW</p>         </td>
      </tr>
      <tr>
         <td><p>OAPIX</p>         </td>
         <td><p>OAPI24 + OAPICX4 or</p>
<p>OAPIUST + AOPICX</p>         </td>
         <td><p>cftaix</p>         </td>
         <td><p>LINRDAXO</p>         </td>
         <td><p>OAPIX</p>         </td>
      </tr>
      <tr>
         <td><p>OAPI2A</p>         </td>
         <td><p>OCFTAPI2</p>         </td>
         <td><p>API 2</p>         </td>
         <td><p>LINRDA2O</p>         </td>
         <td><p>OAPI2A</p>         </td>
      </tr>
      <tr>
         <td><p>OAPI2B</p>         </td>
         <td><p>OCFTAPI2</p>         </td>
         <td><p>API 2</p>         </td>
         <td><p>LINRDA3O</p>         </td>
         <td><p>OAPI2B</p>         </td>
      </tr>
      <tr>
         <td>OAPISYN         </td>
         <td>OAPICST
OAPIINF
OAPIMSG         </td>
         <td>cftau
or
CFTU         </td>
         <td>LINRDAYO         </td>
         <td>OAPISYN         </td>
      </tr>
      <tr>
         <td><p><strong>C</strong></p>
<p> </p>         </td>
         <td><p>CAPIC</p>         </td>
         <td><p>CAPIUST</p>         </td>
         <td><p>cftai</p>
<p>cftau</p>
<p>cftac</p>         </td>
         <td><p>LINRDACC</p>         </td>
         <td><p>CAPIC</p>         </td>
      </tr>
      <tr>
         <td><p>CAPIW</p>         </td>
         <td><p>CAPIUST</p>         </td>
         <td><p>cftai</p>
<p>cftau</p>         </td>
         <td><p>LINRDAWC</p>         </td>
         <td><p>CAPIW</p>         </td>
      </tr>
      <tr>
         <td><p>CAPIX</p>         </td>
         <td><p>CAPIUST</p>         </td>
         <td><p>cftaix</p>         </td>
         <td><p>LINRDAXC</p>         </td>
         <td><p>CAPIX</p>         </td>
      </tr>
      <tr>
         <td><p>CAPII</p>         </td>
         <td><p>CAPIUST</p>         </td>
         <td><p>cfti</p>         </td>
         <td><p>LINRDAIC</p>         </td>
         <td><p>CAPII</p>         </td>
      </tr>
      <tr>
         <td><p>CAPI2A</p>         </td>
         <td><p>CAPI2UST</p>         </td>
         <td><p>API 2</p>         </td>
         <td><p>LINRDA2C</p>         </td>
         <td><p>CAPI2A</p>         </td>
      </tr>
      <tr>
         <td><p>CAPI2B</p>         </td>
         <td><p>CAPI2UST</p>         </td>
         <td><p>API 2</p>         </td>
         <td><p>LINRDA3C</p>         </td>
         <td><p>CAPI2B</p>         </td>
      </tr>
      <tr>
         <td>ASM         </td>
         <td><p>AAPIDLL</p>         </td>
         <td><p>-</p>         </td>
         <td><p>cftai</p>         </td>
         <td><p>LINKALE</p>         </td>
         <td><p>AAPIDLL</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>AXPIDLL         </td>
         <td>          </td>
         <td>cftaix         </td>
         <td>LINKALEX         </td>
         <td>AXPIDLL         </td>
      </tr>
   </tbody>
</table>
