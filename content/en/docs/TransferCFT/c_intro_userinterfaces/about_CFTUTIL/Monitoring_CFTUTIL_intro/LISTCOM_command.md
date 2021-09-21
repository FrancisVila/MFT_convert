{
    "title": "LISTCOM - List COM",
    "linkTitle": "LISTCOM - List COM",
    "weight": "340"
}This topic describes how to list the communication media records for
FILE type communication medium.

Command syntax: [LISTCOM](../../../command_summary)

Use the LISTCOM command to lists the communication media
records in non-ciphered text whether these records are ciphered or not.

Only
the file type communication medium is concerned by this command.

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameters</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">
         <td>
            <p><a href="../../../command_summary/parameter_intro/content">CONTENT</a> </p>
         </td>
         <td width="59.777%">
            <p>Results display type:</p>
            <ul>
               <li>FULL: List of all records (active or 
 otherwise)               </li>
               <li>ACTIVE (default): List of records that are not empty, meaning some messages may not display                </li>
            </ul>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="first.htm">FIRST</a>
</p>
         </td>
         <td colspan="1" rowspan="1" width="59.777%">
            <p>Number of the first record to be displayed or listed.</p>
            <p>The maximum number of records is the one defined in the 
 RECNB parameter of the CFTFILE command at the time the file is created.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>FILE {see 
 the comment | filename}]</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Communication medium filename.</p>
            <ul>
               <li>The file type is implicit.               </li>
               <li>The default value for this parameter is fixed.               </li>
            </ul>
            <p>To designate the current communication file for the Transfer CFT, 
 set this parameter to the value of the NAME parameter in the CFTCOM TYPE=FILE 
 command.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="20.241%">
            <p><a href="last.htm">LAST</a> </p>
         </td>
         <td colspan="1" rowspan="1" width="59.777%">
            <p>Number of the last record to be displayed or listed.</p>
            <p>The default value is the maximum number of records defined 
 in the RECNB parameter of the CFTFILE command at the time the file is 
 created.</p>
            <p>The maximum number of records is the one defined in the 
 RECNB parameter of the CFTFILE command at the time the file is created.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="20.241%">
            <p><a href="../../../command_summary/parameter_intro/verify">VERIFY</a>
</p>
         </td>
         <td colspan="1" rowspan="1" width="59.777%">
            <p>Request to verify the validity of each record in the file 
 at the time it is listed or displayed.</p>
         </td>
      </tr>
   </tbody>
</table>
