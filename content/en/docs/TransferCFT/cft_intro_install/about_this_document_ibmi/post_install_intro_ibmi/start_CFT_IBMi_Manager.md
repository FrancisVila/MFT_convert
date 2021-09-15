{
    "title": "Start the Transfer CFT IBM i Manager",
    "linkTitle": "Start the Transfer CFT IBM i Manager",
    "weight": "260"
}The CFTSTART program is used to start Transfer CFT IBM i without any required user action.

CFTSTART comprises:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>ADDLIBLE LIB(CFTPGM) POSITION(*FIRST)</p>
            <p>ADDLIBLE LIB(CFTPROD) POSITION(*FIRST)</p>
            <p>CALL PGM(CFTSTART)</p>
            <p>RMVLIBLE LIB(CFTPGM)</p>
            <p>RMVLIBLE LIB(CFTPROD)</p>
         </td>
      </tr>
   </tbody>
</table>
