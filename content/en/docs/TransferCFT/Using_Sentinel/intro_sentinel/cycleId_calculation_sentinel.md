{
    "title": "CycleId calculation",
    "linkTitle": "CycleId calculation",
    "weight": "250"
}The internal CycleId is an XFBTransfer Tracked Object attribute. This field has the structure described in the following table.

Internal CycleID structure PeSIT

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Offset</p>
</th>
         <th>
            <p>Length</p>
</th>
         <th>
            <p>PI</p>
</th>
         <th>
            <p>Description</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>1</p>
         </td>
         <td>
            <p>4</p>
         </td>
         <td>
            <p>“SUIV”</p>
         </td>
         <td>
            <p>Eye catcher</p>
         </td>
      </tr>
      <tr>
         <td rowspan="2">
            <p>5</p>
         </td>
         <td rowspan="2">
            <p>24</p>
         </td>
         <td>
            <p>PI3 CONNECT</p>
         </td>
         <td>
            <p>For transmission</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>PI4 CONNECT</p>
         </td>
         <td>
            <p>For reception</p>
         </td>
      </tr>
      <tr>
         <td rowspan="2">
            <p>29</p>
         </td>
         <td rowspan="2">
            <p>24</p>
         </td>
         <td>
            <p>PI4 CONNECT</p>
         </td>
         <td>
            <p>For transmission</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>PI3 CONNECT</p>
         </td>
         <td>
            <p>For reception</p>
         </td>
      </tr>
      <tr>
         <td rowspan="3">
            <p>53</p>
         </td>
         <td rowspan="3">
            <p>5</p>
         </td>
         <td>
            <p>"0"</p>
         </td>
         <td rowspan="3">
            <p>"0"</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>"65535"</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>"REPLY"</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>58</p>
         </td>
         <td>
            <p>76</p>
         </td>
         <td>
            <p>PI12</p>
         </td>
         <td>
            <p>Virtual filename</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>134</p>
         </td>
         <td>
            <p>8</p>
         </td>
         <td>
            <p>PI13</p>
         </td>
         <td>Sequence number         </td>
      </tr>
      <tr>
         <td>
            <p>142</p>
         </td>
         <td>
            <p>12</p>
         </td>
         <td>
            <p>PI51</p>
         </td>
         <td>
            <p>Date YYMMDD padded to 12 with spaces on the right</p>
         </td>
      </tr>
      <tr>
         <td rowspan="2">
            <p>154</p>
         </td>
         <td rowspan="2">
            <p>1</p>
         </td>
         <td>
            <p>E</p>
         </td>
         <td>
            <p>For transmission</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>R</p>
         </td>
         <td>
            <p>For reception</p>
         </td>
      </tr>
   </tbody>
</table>

 

Internal CycleID structure SFTP

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Offset</p>
</th>
         <th>
            <p>Length</p>
</th>
         <th>Value</th>
         <th>
            <p>Description</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>1</p>
         </td>
         <td>
            <p>4</p>
         </td>
         <td>
            <p>“SUIV”</p>
            <p>"TEMP"</p>
         </td>
         <td>
            <p>Eye catcher</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>5</p>
         </td>
         <td>
            <p>24</p>
         </td>
         <td>Sender identifier         </td>
         <td>
            <p>Sender account login name.</p>
            <ul>
               <li>SEND: System login of the process that runs the SFTP client               </li>
               <li>RECV: SFTP login name sends by the client to connect to the SFTP server               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>
            <p>29</p>
         </td>
         <td>
            <p>24</p>
         </td>
         <td>Receiver identifier	         </td>
         <td>
            <p>Receiver login name</p>
            <ul>
               <li>SEND: SFTP login name sends by the client to connect to the SFTP server               </li>
               <li>RECV: System login of the process that runs the SFTP client               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>
            <p>53</p>
         </td>
         <td>
            <p>5</p>
         </td>
         <td>"0"         </td>
         <td>
            <p>For file transfer</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>58</p>
         </td>
         <td>
            <p>76</p>
         </td>
         <td>Virtual Filename         </td>
         <td>
            <p>Logical file name, NIDF for Transfer CFT</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>134</p>
         </td>
         <td>
            <p>8</p>
         </td>
         <td>Sequence number         </td>
         <td>
            <p>Unique number identifying the transfer sent, NIDT for Transfer CFT</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>142</p>
         </td>
         <td>
            <p>12</p>
         </td>
         <td>Date YYMMDD padded to 12 with spaces on the right         </td>
         <td>
            <p>Only the date is used (YYMMDD), and the time is filled in 6 spaces</p>
         </td>
      </tr>
      <tr>
         <td rowspan="2">
            <p>154</p>
         </td>
         <td rowspan="2">
            <p>1</p>
         </td>
         <td>E         </td>
         <td>
            <p>For transmission</p>
         </td>
      </tr>
      <tr>
         <td>R         </td>
         <td>
            <p>For reception</p>
         </td>
      </tr>
   </tbody>
</table>
