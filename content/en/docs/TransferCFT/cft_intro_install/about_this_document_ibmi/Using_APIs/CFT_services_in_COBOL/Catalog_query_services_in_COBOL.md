{
    "title": " Transfer CFT  catalog query services",
    "linkTitle": "Catalog query services in COBOL",
    "weight": "320"
}This service provides access to the  {{< TransferCFT/componentshortname  >}} catalog entries, for
querying and modification, and enables you to sort the selected catalog
entries. Additionally, you can sort the current selection in memory.

> **Note**
>
> The communication structure
> in Transfer CFT enables you to recuperate catalog fields, such
> as an identifier, that exceed 8 to 32 characters.

```

Function

Use

OPEN
Open catalog file
This function:

-   Allocates
    the catalog file
-   Opens
    the file
-   Reserves
    an internal control block
-   Initializes
    the internal block parameter

SELECT
Specify the selection criteria
This function:

-   Checks
    the syntax used
-   Stores
    the selection criteria in the internal control block

SELECT240
Specify the selection criteria
This function:

-   Is available
    in CFT v2.4 and higher
-   Retrieves
    identifiers that are longer than 8 to 32 characters
-   Checks
    the syntax used
-   Stores
    the selection criteria in the internal control block

NEXT
Read next entry in the catalog
This function:

-   Reads
    the next entry
-   Sets
    the "catalog entry data" area

The first call to this function must be preceded by a SELECT.
NEXT240
Read next entry in the catalog
This function:

-   Is available
    in CFT v2.4 and higher
-   Retrieves
    identifiers that are longer than 8 to 32 characters
-   Reads
    the next entry
-   Sets
    the "catalog entry data" area

MODIFY
Modify the state of the current catalog entry or delete
this entry from the catalog
This function:

-   Retrieves
    the last entry read from the internal control block
-   Checks
    the state of this entry
-   Sends
    the modification request to  {{< TransferCFT/componentshortname >}}

SORT
Sort the selected catalog entries
This function:

-   Close
    the catalog file
-   De-allocates
    the file
-   Frees
    the internal control block
-   Resets
    the internal control block parameter

DO
Execute the current selection and the requested sort in
memory
CLOSE
Close catalog file
```
<span id="Call Syntax"></span>

## Call syntax

```
CALL     "CFTI"    
USING     <verb>       <blk>    
  <param>    
<rc>
```

Where:

-   &lt;verb> is
    the command that you want to process
-   &lt;blk> is
    a
-   &lt;param> is
    a character string of variable length that contains the command parameters.
    The end of the field is defined by a character initially set to low-value
-   &lt;rc> is the
    return code

The available &lt;verbs> are listed in the following table.


           |  &lt;verb&gt;  |  Value  |  Service  |
 --- | --- | --- | --- |
|  F-OPEN  |  OPEN  |  Open catalog  |
|  F-SELECT  |  SELECT  |  Define selection criteria  |
|  F-NEXT  |  NEXT  |  Read next entry  |
|  F-MODIFY  |  MODIFY  |  Modify catalog entry state  |
|  F-CLOSE  |  CLOSE  |  Close catalog  |


The available &lt;param> are listed in the following table.


           |  &lt;verb&gt;  |  &lt;param&gt;  |  Explanation  |
 --- | --- | --- | --- |
|  F-OPEN  |  D-CAT  |  Path name or logical name of the catalog file. If the name is blank, Transfer CFTI uses a default name.  |
|  F-SELECT  |  Z-SEL  |  Selection criteria according to the format described in the "S*election data description"* in the **cft.apicop** file. If a field is blank or equal to binary zeros, it is considered not selective.<br/>This field can contain:<br/> • the size of the selection criteria field (SLENTGTH) and the size of the field supporting the catalog entry (CLENGTH) in order to avoid recompiling the application program if these two fields are extended.<br/> • the transfer start and end date (BDATE and EDATE) to select transfers performed between these two dates.<br/> • a mask with the special characters "?" and *". The "?" character replaces any character. The "*" character replaces a character string of any length.<br /> <br /> Examples:<br /> A*D replaces ABCD, ABCED or AID<br /> A??D replaces ABCD, AXYD or AQZD<br /> *CD replaces ABECD, YXZCDor TYUICD<br /> ?CD replaces ACD, XCD or ZCD<br /> ?B* replaces ABCDEF, XBZWEO or *KBWXCV<br /> ???? replaces  ABCD, XYZW or HGFD</li>  |
|  F-NEXT  |  Z-CAT  |  Next catalog entry according to the format described in the "S<span >election data description</span>" in the <span >cft.apicop</span> file.<br/>The length of this field is defined by the SELECT service. See the CLENGTH field in the Selection data description.  |
|  F-MODIFY  |  M-STATE  |  New state of a transfer to be placed in the catalog entry previously read:<br/> • ‘D’ at Disposal: only valid if the former state is H or K<br/> • ‘H’ Hold: only valid if the former state is D, C or K<br/> • ‘K’ Keep: only valid if the former state is D, C or H<br/> • ‘X’ eXecuted: only valid if the former state is T<br/> • ‘P’ Purge: deletes the catalog entry</li>  |
|  F-CLOSE  |   |  No &lt;param&gt; needed  |


## Return codes

The return codes listed below apply to all services.

<table>
         
         
         
   
   <thead>
      <tr>
<th ><p>Mnemonic</p>         </th>
<th ><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-NOERR</p>         </td>
         <td   data-valign="top" width="71.863%"><p>No error</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-FUNC-UNDEF</p>         </td>
         <td   data-valign="top" width="71.863%"><p>Command not valid</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-INT-BLK</p>         </td>
         <td   data-valign="top" width="71.863%"><p>&lt;blk&gt; parameter invalid</p>         </td>
      </tr>
      <tr>
         <td colspan="2"   data-valign="top" width="28.137%"><p>OPEN code only</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-MEM-GET</p>         </td>
         <td   data-valign="top" width="71.863%"><p>Memory allocation error</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-CAT-ALLOC</p>         </td>
         <td   data-valign="top" width="71.863%"><p>Catalog file allocation error</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-CAT-OPEN</p>         </td>
         <td   data-valign="top" width="71.863%"><p>Catalog file opening problem</p>         </td>
      </tr>
      <tr>
         <td colspan="2"   data-valign="top" width="28.137%"><p>SELECT code only</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-SEL-DIRECT</p>         </td>
         <td   data-valign="top" width="71.863%"><p>DIRECTION criterion incorrect</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-SEL-TYPE</p>         </td>
         <td   data-valign="top" width="71.863%"><p>TYPE criterion incorrect</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-SEL-STATE</p>         </td>
         <td   data-valign="top" width="71.863%"><p>STATE criterion incorrect</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-CAT-EMPTY</p>         </td>
         <td   data-valign="top" width="71.863%"><p>Catalog empty</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-SEL-DATE</p>         </td>
         <td   data-valign="top" width="71.863%"><p>EDATE value &lt; BDATE value</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-SEL-FDATE</p>         </td>
         <td   data-valign="top" width="71.863%"><p>FDATE criterion incorrect</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-SEL-CDATE</p>         </td>
         <td   data-valign="top" width="71.863%"><p>CDATE criterion incorrect</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-SEL-BDATE</p>         </td>
         <td   data-valign="top" width="71.863%"><p>BDATE criterion incorrect</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-SEL-DATE</p>         </td>
         <td   data-valign="top" width="71.863%"><p><span >EDATE
criterion incorrect</span></p>         </td>
      </tr>
      <tr>
         <td colspan="2"   data-valign="top" width="28.137%"><p>NEXT code only</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-CAT-EOF</p>         </td>
         <td   data-valign="top" width="71.863%"><p>End of catalog file</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-CAT-READ</p>         </td>
         <td   data-valign="top" width="71.863%"><p>Catalog file read error</p>         </td>
      </tr>
      <tr>
         <td colspan="2"   data-valign="top" width="28.137%"><p>MODIFY code only</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-MOD-OSTATE</p>         </td>
         <td   data-valign="top" width="71.863%"><p>State invalid</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-MOD-NSTATE</p>         </td>
         <td   data-valign="top" width="71.863%"><p>Requested new state incorrect</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-INT-ERR2</p>         </td>
         <td   data-valign="top" width="71.863%"><p>Internal error</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPIO-COM-OPEN</p>         </td>
         <td   data-valign="top" width="71.863%"><p>Communication medium opening error</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-COM-WRITE</p>         </td>
         <td   data-valign="top" width="71.863%"><p>Communication medium write error</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-COM-CLOSE</p>         </td>
         <td   data-valign="top" width="71.863%"><p>Communication medium closing problem</p>         </td>
      </tr>
      <tr>
         <td colspan="2"   data-valign="top" width="28.137%"><p>CLOSE code only</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-MEM-FREE</p>         </td>
         <td   data-valign="top" width="71.863%"><p>Memory de-allocation error</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-CAT-FREE</p>         </td>
         <td   data-valign="top" width="71.863%"><p>Catalog file de-allocation error</p>         </td>
      </tr>
      <tr>
         <td   data-valign="top" width="28.137%"><p>CAPI-CAT-CLOSE</p>         </td>
         <td   data-valign="top" width="71.863%"><p>Catalog file closing error</p>         </td>
      </tr>
   </tbody>
</table>
