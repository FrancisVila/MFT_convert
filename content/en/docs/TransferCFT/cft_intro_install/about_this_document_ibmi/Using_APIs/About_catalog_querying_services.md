{
    "title": "Catalog querying services ",
    "linkTitle": "Catalog querying services",
    "weight": "240"
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
