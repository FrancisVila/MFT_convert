{
    "title": "to be deleted",
    "linkTitle": "to be deleted",
    "weight": "2510"
}### origin

#### All CFTXXX commands

ORIGIN = &lt;C> ('CFTUTIL','C','DESIGNER','D','COPILOT','O')

This parameter indicates the origin of an object. You can use this to determine if an object was created or modified using Central Governance (DESIGNER), CFTUTIL, or Copilot.

To view the ORIGIN parameter, for example:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTUTIL cftext id=test, content=brief
 </p>
            <p>CFTSEND      ID          = 'TEST',
              </p>
            <p>IMPL        = 'NO',
              </p>
            <p>STATE       = 'DISP',
</p>
            <p>              CYCLE       = '0',
              ...</p>
            <p><![CDATA[
]]><b>ORIGIN      = 'CFTUTIL',</b><![CDATA[
]]></p>
            <p>MAXDURATION = '0',
              </p>
            <p>...</p>
            <p>
              MODE        = 'REPLACE'</p>
         </td>
      </tr>
   </tbody>
</table>
