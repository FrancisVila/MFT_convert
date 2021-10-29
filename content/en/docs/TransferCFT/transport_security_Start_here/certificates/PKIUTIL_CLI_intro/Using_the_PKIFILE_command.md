{
    "title": "Using  the PKIFILE command",
    "linkTitle": "Using PKIFILE",
    "weight": "270"
}Use the PKIFILE command to create, purge, or delete a local
certificate database.

Syntax

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>PKIFILE</p>
<div>
[MODE =  {REPLACE | CREATE | DELETE},]
</div>
<div>
FNAME =  string,
</div>         </td>
      </tr>
   </tbody>
</table>

## Modifying the local certificate database

<table data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="23.085%">            <p>FNAME = string1..64</p>         </td>
         <td width="53.793%">            <p>Name of the local certificate database.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="23.085%">            <p>[MODE = REPLACE
| CREATE | DELETE]</p>         </td>
         <td width="53.793%">            <p>Action on the database.</p>
            <ul>
               <li>REPLACE purges the database               </li>
               <li>CREATE creates the internal datafile if it does
not already exist               </li>
               <li>DELETE deletes the database               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>
