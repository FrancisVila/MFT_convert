{
    "title": "Housekeeping for statistical files",
    "linkTitle": "SWITCH - Switch files manually",
    "weight": "360"
}Transfer CFT extracts certain details for each transfer that you perform if you have defined the account (ACCNT) feature. This information is stored in a statistical file if you have defined TYPE = FILE. To manage the contents of this file, you can specify two criteria in the CFTACCNT object to trigger a switch (MAXREC and SWITCH).

#### Automatic SWITCH 

You can customize the switch procedure depending on your production needs. The symbolic variable &FACCNT
represents the statistical file.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">At least one of the two files (either the statistical or alternate statistical file) must be empty prior to starting Transfer CFT.         </td>
      </tr>
   </tbody>
</table>

This example automatically executes the switch procedure at noon.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTACCNT ID=ACCNT0,TYPE=FILE,EXEC=&lt;switch_procedure&gt;,SWITCH=120000         </td>
      </tr>
   </tbody>
</table>

#### Manual SWITCH 

To manually execute the switch procedure, use the command:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>SWITCH TYPE=ACCNT         </td>
      </tr>
   </tbody>
</table>
