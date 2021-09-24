{
    "title": "selfname",
    "linkTitle": "selfname",
    "weight": "3160"
}### <span id="selfname"></span>selfname

#### CFTSEND, SEND

\[SELFNAME = *filename*\]  {string512}

Name of a file that contains a list
of files selected for sending, where all of the files must be contained in the same folder.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>send part=newyork,idf=test,selfname=selfname.txt,fname=#myfolder         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When using FACTION=DELETE with SELFNAME, the FNAME must be a directory (not a mask).         </td>
      </tr>
</table>

[Return to Command index](../../)
