{
    "title": "Starting Transfer CFT in batch mode",
    "linkTitle": "Start the Transfer CFT IBM i Manager",
    "weight": "270"
}The CFTSTART program is used to start Transfer CFT IBM i without any required user action.

CFTSTART comprises:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>ADDLIBLE LIB(CFTPGM) POSITION(*FIRST)</p>
            <p>ADDLIBLE LIB(CFTPROD) POSITION(*FIRST)</p>
            <p>CALL PGM(CFTSTART)</p>
            <p>RMVLIBLE LIB(CFTPGM)</p>
            <p>RMVLIBLE LIB(CFTPROD)</p>         </td>
      </tr>
   </tbody>
</table>
