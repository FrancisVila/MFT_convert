{
    "title": "Using  the PKIFILE command",
    "linkTitle": "Using PKIFILE",
    "weight": "260"
}Use the PKIFILE command to create, purge, or delete a local
certificate database.

Syntax



    PKIFILE
    [MODE =  {REPLACE | CREATE | DELETE},]
    FNAME =  string,

## Modifying the local certificate database

<table>
   <tbody>
      <tr>
         <td><p>FNAME = string1..64</p>         </td>
         <td><p>Name of the local certificate database.</p>         </td>
      </tr>
      <tr>
         <td><p>[MODE = REPLACE
| CREATE | DELETE]</p>         </td>
         <td><p>Action on the database.</p>
<ul>
<li>REPLACE purges the database</li>
<li>CREATE creates the internal datafile if it does
not already exist</li>
<li>DELETE deletes the database</li>
</ul>         </td>
      </tr>
   </tbody>
</table>
