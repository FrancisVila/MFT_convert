{
    "title": "Test STONITH configuration",
    "linkTitle": "Test STONITH configuration",
    "weight": "240"
}To test the STONITH configuration, run the **crm node fence &lt;hostname>** command from the shell.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><code>#crm node fence &lt;hostname&gt;</code>
</p>
         </td>
      </tr>
   </tbody>
</table>

Where `<hostname>` is the hostname of the node.

The command will fence the node and causing a reboot.
