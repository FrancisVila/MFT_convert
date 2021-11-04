{
    "title": "selfname",
    "linkTitle": "selfname",
    "weight": "3130"
}<span id="selfname"></span>

### selfname

#### CFTSEND, SEND

\[SELFNAME = *filename*\]  <span style="font-weight: normal;">{string512}</span>

Name of a file that contains a list
of files selected for sending, where all of the files must be contained in the same folder.


    send part=newyork,idf=test,selfname=selfname.txt,fname=#myfolder

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>When using FACTION=DELETE with SELFNAME, the FNAME must be a directory (not a mask).         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)
