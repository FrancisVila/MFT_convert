{
    "title": "LISTCOM - List the communication medium records",
    "linkTitle": "LISTCOM - List COM",
    "weight": "330"
}This topic describes how to list the communication media records for
FILE type communication medium.

Command syntax: [LISTCOM](../../../command_summary#LISTCOM)

Use the LISTCOM command to lists the communication media
records in non-ciphered text whether these records are ciphered or not.

Only
the file type communication medium is concerned by this command.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameters         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/content">CONTENT</a> </p>         </td>
         <td><p>Results display type:</p>
<ul>
<li>FULL: List of all records (active or
otherwise)</li>
<li>ACTIVE (default): List of records that are not empty, meaning some messages may not display</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>FIRST</p>         </td>
         <td><p>Number of the first record to be displayed or listed.</p>
<p>The maximum number of records is the one defined in the
RECNB parameter of the CFTFILE command at the time the file is created.</p>         </td>
      </tr>
      <tr>
         <td><p>FILE {see
the comment | filename}]</p>         </td>
         <td><p>Communication medium filename.</p>
<ul>
<li>The file type is implicit.</li>
<li>The default value for this parameter is fixed.</li>
</ul>
<p>To designate the current communication file for the Transfer CFT,
set this parameter to the value of the NAME parameter in the CFTCOM TYPE=FILE
command.</p>         </td>
      </tr>
      <tr>
         <td><p>LAST </p>         </td>
         <td><p>Number of the last record to be displayed or listed.</p>
<p>The default value is the maximum number of records defined
in the RECNB parameter of the CFTFILE command at the time the file is
created.</p>
<p>The maximum number of records is the one defined in the
RECNB parameter of the CFTFILE command at the time the file is created.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/verify">VERIFY</a></p>         </td>
         <td><p>Request to verify the validity of each record in the file
at the time it is listed or displayed.</p>         </td>
      </tr>
   </tbody>
</table>
