{
    "title": "Manage commands",
    "linkTitle": "Manage commands",
    "weight": "180"
}This section describes all of the command available to manage your Transfer CFT product.

## Standard commands

<table>
   <th>
      <tr>
<th><p>Command</p>         </th>
<th><p>Comment</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>CFTSTART</p>         </td>
         <td><p>Start Transfer CFT</p>         </td>
      </tr>
      <tr>
         <td><p>CFTSTOP</p>         </td>
         <td><p>Stop Transfer CFT</p>         </td>
      </tr>
      <tr>
         <td><p>COPSTART</p>         </td>
         <td><p>Start the UI server</p>         </td>
      </tr>
      <tr>
         <td><p>COPSTOP</p>         </td>
         <td><p>Stop the UI server</p>         </td>
      </tr>
      <tr>
         <td><p>CFTMN</p>         </td>
         <td><p>This is the procedure to manage Transfer CFT and to configure multi-node. Add
the following action(s) to manage your product:</p>
<ul>
<li>START</li>
<li>STOP</li>
<li>RESTART</li>
<li>ADD_NODE</li>
<li>REMOVE_NODE</li>
<li>ADD_HOST</li>
<li>REMOVE_HOST</li>
<li>REMOVE_NODE</li>
<li>ENABLE_NODE</li>
<li>DISABLE_NODE</li>
</ul>
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>CFTMN is the equivalent of <span class="code">cft script</span> for UNIX or
Windows.         </td>
      </tr>
   </tbody>
</table>         </td>
      </tr>
   </tbody>
</table>

## Deprecated commands

<table>
<th>
      <tr>
<th>Replace this command...         </th>
<th>With the new command...         </th>
      </tr>
   </thead>
<tbody data-xmlns="">
      <tr>
         <td><p>SHUT</p>         </td>
         <td><p>CFTSTOP + COPSTOP</p>         </td>
      </tr>
      <tr>
         <td><p>CFTMGSBM</p>         </td>
         <td><p>CFTSTART</p>         </td>
      </tr>
      <tr>
         <td><p>STARTCOPB</p>         </td>
         <td><p>COPSTART</p>         </td>
      </tr>
      <tr>
         <td><p>COPSMNG</p>         </td>
         <td><p>COPSTART</p>         </td>
      </tr>
      <tr>
         <td><p>COPSTOPM</p>         </td>
         <td><p>COPSTOP</p>         </td>
      </tr>
      <tr>
         <td><p>STOPCOPL</p>         </td>
         <td><p>COPSTOP</p>         </td>
      </tr>
      <tr>
         <td><p>BACKGROUND_C</p>         </td>
         <td><p>BACKGROUND</p>         </td>
      </tr>
      <tr>
         <td>SNDCFTF         </td>
         <td>CFTUTIL (See <strong>Example 1</strong>)         </td>
      </tr>
      <tr>
         <td>SNDCFTSPLF         </td>
         <td>CFTUTIL (See <strong>Example 2</strong>)         </td>
      </tr>
      <tr>
         <td>MAJSECINI         </td>
         <td>No replacement         </td>
      </tr>
      <tr>
         <td>MAJSECENVG         </td>
         <td>No replacement         </td>
      </tr>
      <tr>
         <td>GENEDICT         </td>
         <td>No replacement         </td>
      </tr>
   </tbody>
</table>

**Example 1**

Send a member:


    CFTUTIL send PART=<PART>, IDF=<IDF>, FNAME=&LIB/&FILE(&MBR)

**Example 2**

Send a spool file:


    CFTUTIL send PART=<PART>, IDF=<IDF>, FNAME=&FILE/&SPLNBR/&WORK/&JOBNBR

 
