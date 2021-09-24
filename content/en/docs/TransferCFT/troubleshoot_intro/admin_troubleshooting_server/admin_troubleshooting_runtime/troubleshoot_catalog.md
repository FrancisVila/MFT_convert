{
    "title": "Troubleshoot the catalog",
    "linkTitle": "Troubleshoot the catalog",
    "weight": "420"
}## The catalog is full and Transfer CFT has stopped

Symptom

Transfer CFT stops and you cannot restart it. To remedy this issue, you can execute the cftcatal tool.

Remedy

You can use the cftcatal utility to increase the size of the Transfer CFT catalog file without losing information. In a multi-node environment, this action resizes all nodes.

Example on Windows or Unix

Execute the profile from the runtime directory and then enter the cftcatal command. Modify the number of records when prompted, for example:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><b>cftcatal</b>
</p>
            <p>CFT Catalog file extension</p>
            <p>Current size of catalog file : 1000</p>
            <p>Number of records in catalog : 1000</p>
            <p>Number of records for catalog file (0=cancel,minimum=10) : 2000</p>
            <p>Extracting current catalog records ......</p>
            <p>New catalog extended to 2000 records and cft can be restarted.</p>
         </td>
      </tr>
   </tbody>
</table>
