{
    "title": " Transfer CFT  catalog query services",
    "linkTitle": "Catalog query services in C",
    "weight": "360"
}This service provides access to the Transfer CFT catalog entries, for
querying and modification, and enables you to sort the selected catalog
entries. Additionally, you can sort the current selection in memory.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The communication structure
in Transfer CFT enables you to recuperate catalog fields, such
as an identifier, that exceed 8 to 32 characters.         </td>
      </tr>
   </tbody>
</table>

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>            <p>Function</p></th>
         <th>            <p>Use</p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="28.255%">            <p>OPEN</p>         </td>
         <td width="71.745%">            <p>Open catalog file</p>
            <p>This function:</p>
            <ul>
               <li>Allocates
the catalog file               </li>
               <li>Opens
the file               </li>
               <li>Reserves
an internal control block               </li>
               <li>Initializes
the internal block parameter               </li>
            </ul>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="28.255%">            <p>SELECT</p>         </td>
         <td width="71.745%">            <p>Specify the selection criteria</p>
            <p>This function:</p>
            <ul>
               <li>Checks
the syntax used               </li>
               <li>Stores
the selection criteria in the internal control block               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="28.255%">            <p>SELECT240</p>         </td>
         <td width="71.745%">            <p>Specify the selection criteria</p>
            <p>This function:</p>
            <ul>
               <li>Is available
in CFT v2.4 and higher               </li>
               <li>Retrieves
identifiers that are longer than 8 to 32 characters               </li>
               <li>Checks
the syntax used               </li>
               <li>Stores
the selection criteria in the internal control block               </li>
            </ul>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="28.255%">            <p>NEXT</p>         </td>
         <td width="71.745%">            <p>Read next entry in the catalog</p>
            <p>This function:</p>
            <ul>
               <li>Reads
the next entry               </li>
               <li>Sets
the "catalog entry data" area               </li>
            </ul>
            <p>The first call to this function must be preceded by a SELECT.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="28.255%">            <p>NEXT240</p>         </td>
         <td width="71.745%">            <p>Read next entry in the catalog</p>
            <p>This function:</p>
            <ul>
               <li>Is available
in CFT v2.4 and higher               </li>
               <li>Retrieves
identifiers that are longer than 8 to 32 characters               </li>
               <li>Reads
the next entry               </li>
               <li>Sets
the "catalog entry data" area               </li>
            </ul>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="28.255%">            <p>MODIFY</p>         </td>
         <td width="71.745%">            <p>Modify the state of the current catalog entry or delete
this entry from the catalog</p>
            <p>This function:</p>
            <ul>
               <li>Retrieves
the last entry read from the internal control block               </li>
               <li>Checks
the state of this entry               </li>
               <li>Sends
the modification request to <span>Transfer CFT</span>               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="28.255%">            <p>SORT</p>         </td>
         <td width="71.745%">            <p>Sort the selected catalog entries</p>
            <p>This function:</p>
            <ul>
               <li>Close
the catalog file               </li>
               <li>De-allocates
the file               </li>
               <li>Frees
the internal control block               </li>
               <li>Resets
the internal control block parameter               </li>
            </ul>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="28.255%">            <p>DO</p>         </td>
         <td width="71.745%">            <p>Execute the current selection and the requested sort in
memory</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="28.255%">            <p>CLOSE</p>         </td>
         <td width="71.745%">            <p>Close catalog file</p>         </td>
      </tr>
   </tbody>
</table>

## <span id="Call_Syntax"></span>Call syntax

These services enable you to query the catalog either with or without
specific criteria.

rc = cftai (verb,&ptr,param)

rc = cftaix (verb,&ptr,param)

Where:

-   rc is the return
    code (int)
-   verb is the command
    that you want to process (char \*)
-   ptr contains the
    address of an internal control block (char \*) completed on return of an
    OPEN service call. It must be provided and defined to call other functions
-   param points to
    the parameters specific to each function

The available verbs are listed in the following table.

<table data-bgcolor="#FFFFFF" data-cellspacing="0" width="90%">
   <thead>
      <tr class="header">
         <th>            <p>&lt;verb&gt;</p></th>
         <th>            <p>Service</p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td data-valign="top" width="23.306%">            <p>OPEN</p>         </td>
         <td data-valign="top" width="76.694%">            <p>Open catalog</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="23.306%">            <p>SELECT</p>         </td>
         <td data-valign="top" width="76.694%">            <p>Define selection criteria</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="23.306%">            <p>NEXT</p>         </td>
         <td data-valign="top" width="76.694%">            <p>Read next entry</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="23.306%">            <p>MODIFY</p>         </td>
         <td data-valign="top" width="76.694%">            <p>Modify catalog entry state</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="23.306%">            <p>SORT</p>         </td>
         <td data-valign="top" width="76.694%">            <p>cftaix only</p>
            <p><span>Sort
the selected catalog entries</span></p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="23.306%">            <p>DO</p>         </td>
         <td data-valign="top" width="76.694%">            <p>cftaix only</p>
            <p>Do the current selection and the requested
sort in memory</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="23.306%">            <p>CLOSE</p>         </td>
         <td data-valign="top" width="76.694%">            <p>Close catalog</p>         </td>
      </tr>
   </tbody>
</table>

The available &lt;param> are listed in the following table.

<table data-bgcolor="#FFFFFF" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-bgcolor="#C0C0C0" data-valign="top" width="20.005%">            <p>&lt;verb&gt;</p>         </td>
         <td data-bgcolor="#C0C0C0" data-valign="top">            <p>&lt;param&gt;</p>         </td>
         <td data-bgcolor="#C0C0C0" data-valign="top">            <p>Explanation</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="20.005%">            <p>OPEN</p>         </td>
         <td data-valign="top">            <p>cat</p>         </td>
         <td data-valign="top">            <p>Path name or logical name of the catalog file. If the name
is blank, Transfer CFT uses a default name.</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="20.005%">            <p>SELECT</p>
            <p>and SELECT240</p>         </td>
         <td data-valign="top">            <p>&amp;cftsel</p>         </td>
         <td data-valign="top">            <p>Selection criteria according to the format described in
the "<span>Selection data description</span>"
in the <span>cftapi.h</span> file.</p>
            <ul>
               <li>cftsel230T for SELECT service               </li>
               <li>cftsel240T for SELECT240 service               </li>
            </ul>
            <p>All the
fields must be defined by left-aligned character strings. If a field is
equal to binary zeros, it is considered not selective.</p>
            <p>This structure can contain:</p>
            <ul>
               <li>The size
of the selection criteria field (slength) and the size of the field supporting
the catalog entry (clength) in order to avoid recompiling the application
program if these two fields are extended.               </li>
               <li>The transfer
start and end date (BDATE and EDATE) to select transfers performed between
these two dates.               </li>
               <li>A field
can be composed of a mask with the special characters "?" and
*". The "?" character replaces any character. The "*"
character replaces a character string of any length.<br />
<br />
Examples:<br />
A*D replaces ABCD, ABCED or AID<br />
A??D replaces ABCD, AXYD or AQZD<br />
*CD replaces ABECD, YXZCDor TYUICD<br />
?CD replaces ACD, XCD or ZCD<br />
?B* replaces ABCDEF, XBZWEO or *KBWXCV<br />
???? replaces ABCD, XYZW or HGFD               </li>
            </ul>
            <p>You should initialize the following:</p>
            <ul>
               <li>The param
field to binary zero before defining it               </li>
               <li>The slength
and clength by  "itoa()"               </li>
            </ul>
            <p>cftaix only</p>
            <p>The selection is only taken into account at the time the
DO service is called.</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="20.005%">            <p>NEXT</p>
            <p>and</p>
            <p>NEXT240</p>         </td>
         <td data-valign="top">            <p>&amp;cftcat</p>         </td>
         <td data-valign="top">            <p>Next catalog entry according to the format described in
the "<span>Selection data description</span>"
in the <span>cftapi.h</span> file.</p>
            <ul>
               <li>cftcatT for NEXT service               </li>
               <li>cftcat240T for NEXT240 service               </li>
            </ul>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="20.005%">            <p>MODIFY</p>         </td>
         <td data-valign="top">            <p>&amp;nstate</p>         </td>
         <td data-valign="top">            <p>New state of a transfer to be placed in the catalog entry
previously read:</p>
            <ul>
               <li>‘D’ at
Disposal: only valid if the former state is H or K               </li>
               <li>‘H’ Hold:
only valid if the former state is D, C
or K               </li>
               <li>‘K’ Keep:
only valid if the former state is D, C or H               </li>
               <li>‘X’ eXecuted:
only valid if the former state is T               </li>
               <li>‘P’ Purge:
 deletes
the catalog entry*. It is only valid if the current state is D, H, K,
T or X               </li>
            </ul>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="20.005%">            <p>SORT</p>         </td>
         <td data-valign="top">            <p>param</p>         </td>
         <td data-valign="top">            <p>cftaix only</p>
            <p>Sort options as described in the "<span>Sort structure of the selected catalog entries</span>"
in the <span>cftapi.h</span> file.</p>
            <p>The function is only taken into account at
the time the DO service is called.</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="20.005%">            <p>DO</p>         </td>
         <td data-valign="top">            <p>" "</p>         </td>
         <td data-valign="top">            <p> </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="20.005%">            <p>CLOSE</p>         </td>
         <td data-valign="top">            <p>" "</p>         </td>
         <td data-valign="top">            <p> </p>         </td>
      </tr>
   </tbody>
</table>

## Return codes

The following return codes apply to all services.

<table data-bgcolor="#FFFFFF" data-cellspacing="0" width="89.513%">
   <tbody>
      <tr class="odd">
         <td data-bgcolor="#C0C0C0" data-valign="top" width="28.137%">            <p>Mnemonic</p>         </td>
         <td data-bgcolor="#C0C0C0" data-valign="top" width="71.863%">            <p>Description</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="28.137%">            <p>CAPI_NOERR</p>         </td>
         <td data-valign="top" width="71.863%">            <p>No error</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="28.137%">            <p>CAPI_FUNC_UNDEF</p>         </td>
         <td data-valign="top" width="71.863%">            <p>Command not valid or service refused by the operating security
system</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="28.137%">            <p>CAPI_INT_PTR</p>         </td>
         <td data-valign="top" width="71.863%">            <p>&lt;ptr&gt; parameter invalid</p>         </td>
      </tr>
      <tr class="odd">
         <td colspan="2" data-valign="top" width="28.137%">            <p>OPEN code only</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="28.137%">            <p>CAPI_MEM_GET</p>         </td>
         <td data-valign="top" width="71.863%">            <p>Memory allocation error</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="28.137%">            <p>CAPI_CAT_ALLOC</p>         </td>
         <td data-valign="top" width="71.863%">            <p>cftai only</p>
            <p>Catalog file allocation error</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="28.137%">            <p>CAPI_CAT_OPEN</p>         </td>
         <td data-valign="top" width="71.863%">            <p>Catalog file opening problem</p>         </td>
      </tr>
      <tr class="odd">
         <td colspan="2" data-valign="top" width="28.137%">            <p>SELECT code only</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="28.137%">            <p>CAPI_SEL_DIRECT</p>         </td>
         <td data-valign="top" width="71.863%">            <p>DIRECTION criterion incorrect</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="28.137%">            <p>CAPI_SEL_TYPE</p>         </td>
         <td data-valign="top" width="71.863%">            <p>TYPE criterion incorrect</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="28.137%">            <p>CAPI_SEL_STATE</p>         </td>
         <td data-valign="top" width="71.863%">            <p>STATE criterion incorrect</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="28.137%">            <p>CAPI_CAT_EMPTY</p>         </td>
         <td data-valign="top" width="71.863%">            <p>Catalog empty</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="28.137%">            <p>CAPI_CAT_SELECT</p>         </td>
         <td data-valign="top" width="71.863%">            <p>cftaix only</p>
            <p>Selection incorrect</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="28.137%">            <p>CAPI_SEL_DATE</p>         </td>
         <td data-valign="top" width="71.863%">            <p>EDATE value &lt; BDATE value</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="28.137%">            <p>CAPI_SEL_FDATE</p>         </td>
         <td data-valign="top" width="71.863%">            <p>FDATE criterion incorrect</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="28.137%">            <p>CAPI_SEL_CDATE</p>         </td>
         <td data-valign="top" width="71.863%">            <p>CDATE criterion incorrect</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="28.137%">            <p>CAPI_SEL_BDATE</p>         </td>
         <td data-valign="top" width="71.863%">            <p>BDATE criterion incorrect</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="28.137%">            <p>CAPI_SEL_DATE</p>         </td>
         <td data-valign="top" width="71.863%">            <p><span>EDATE
criterion incorrect</span></p>         </td>
      </tr>
      <tr class="even">
         <td colspan="2" data-valign="top" width="28.137%">            <p>NEXT code only</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="28.137%">            <p>CAPI_CAT_EOF</p>         </td>
         <td data-valign="top" width="71.863%">            <p>End of catalog file</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="28.137%">            <p>CAPI_CAT_READ</p>         </td>
         <td data-valign="top" width="71.863%">            <p>Catalog file read error</p>         </td>
      </tr>
      <tr class="odd">
         <td colspan="2" data-valign="top" width="28.137%">            <p>MODIFY code only</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="28.137%">            <p>CAPI_CAT_MODIFY</p>         </td>
         <td data-valign="top" width="71.863%">            <p>cftaix only</p>
            <p>Modification error</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="28.137%">            <p>CAPI_MOD_OSTATE</p>         </td>
         <td data-valign="top" width="71.863%">            <p>State invalid</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="28.137%">            <p>CAPI_MOD_NSTATE</p>         </td>
         <td data-valign="top" width="71.863%">            <p>Requested new state incorrect</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="28.137%">            <p>CAPI_INT_ERR2</p>         </td>
         <td data-valign="top" width="71.863%">            <p>Internal error</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="28.137%">            <p>CAPIO_COM_OPEN</p>         </td>
         <td data-valign="top" width="71.863%">            <p>Communication medium opening error</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="28.137%">            <p>CAPI_COM_WRITE</p>         </td>
         <td data-valign="top" width="71.863%">            <p>Communication medium write error</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="28.137%">            <p>CAPI_COM_CLOSE</p>         </td>
         <td data-valign="top" width="71.863%">            <p>Communication medium closing problem</p>         </td>
      </tr>
      <tr class="odd">
         <td colspan="2" data-valign="top" width="28.137%">            <p>SORT code only (cftaix only)</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="28.137%">            <p>CAPI_CATSORT</p>         </td>
         <td data-valign="top" width="71.863%">            <p>sort incorrect</p>         </td>
      </tr>
      <tr class="odd">
         <td colspan="2" data-valign="top" width="28.137%">            <p>DO code only (cftaix only)</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="28.137%">            <p>CAPI_CAT_CLOSE</p>         </td>
         <td data-valign="top" width="71.863%">            <p>Error on closing the catalog</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="28.137%">            <p>CAPI_CAT_OPEN</p>         </td>
         <td data-valign="top" width="71.863%">            <p>Error on opening the catalog</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="28.137%">            <p>CAPI_CAT_EMPTY</p>         </td>
         <td data-valign="top" width="71.863%">            <p>Catalog empty or no record selected</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="28.137%">            <p>CAPI_ERREXEC</p>         </td>
         <td data-valign="top" width="71.863%">            <p>Execution error</p>         </td>
      </tr>
      <tr class="even">
         <td colspan="2" data-valign="top" width="28.137%">            <p>CLOSE code only</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="28.137%">            <p>CAPI_MEM_FREE</p>         </td>
         <td data-valign="top" width="71.863%">            <p>Memory de-allocation error</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="28.137%">            <p>CAPI_CAT_FREE</p>         </td>
         <td data-valign="top" width="71.863%">            <p>Catalog file de-allocation error</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="28.137%">            <p>CAPI_CAT_CLOSE</p>         </td>
         <td data-valign="top" width="71.863%">            <p>Catalog file closing error</p>         </td>
      </tr>
   </tbody>
</table>
