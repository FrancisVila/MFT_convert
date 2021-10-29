{
    "title": "selfname",
    "linkTitle": "selfname",
    "weight": "3160"
}### <span id="selfname"></span>selfname

#### CFTSEND, SEND

\[SELFNAME = *filename*\]  {string512}

Name of a file that contains a list
of files selected for sending, where all of the files must be contained in the same folder.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>send part=newyork,idf=test,selfname=selfname.txt,fname=#myfolder         </td>
      </tr>
   </tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">When using FACTION=DELETE with SELFNAME, the FNAME must be a directory (not a mask).         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../)
