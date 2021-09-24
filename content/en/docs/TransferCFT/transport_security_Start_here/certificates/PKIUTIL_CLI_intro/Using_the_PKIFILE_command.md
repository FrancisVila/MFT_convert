{
    "title": "Using PKIFILE",
    "linkTitle": "Using PKIFILE",
    "weight": "270"
}# <span id="Using_the_PKIFILE_command"></span>Using the PKIFILE command

Use the PKIFILE command to create, purge, or delete a local
certificate database.

Syntax

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>PKIFILE</p>
<div>[MODE =  {REPLACE | CREATE | DELETE},]</div>
<div>FNAME =  string,</div>
         </td>
      </tr>
   </tbody>
</table>

## Modifying the local certificate database

<table cellspacing="0">
   <col/>
   <col/>
      <tr valign="top">
         <td width="23.085%">
            <p>FNAME = string1..64</p>
         </td>
         <td width="53.793%">
            <p>Name of the local certificate database.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="23.085%">
            <p>[MODE = REPLACE 
 | CREATE | DELETE]</p>
         </td>
         <td colspan="1" rowspan="1" width="53.793%">
            <p>Action on the database.</p>
            <ul>
               <li>REPLACE purges the database               </li>
               <li>CREATE creates the internal datafile if it does 
 not already exist               </li>
               <li>DELETE deletes the database               </li>
            </ul>
         </td>
      </tr>
</table>
