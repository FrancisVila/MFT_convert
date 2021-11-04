{
    "title": "Test STONITH configuration",
    "linkTitle": "Test STONITH configuration",
    "weight": "240"
}To test the STONITH configuration, run the **crm node fence &lt;hostname>** command from the shell.



    #crm node fence <hostname>

Where `<hostname>` is the hostname of the node.

The command will fence the node and causing a reboot.
