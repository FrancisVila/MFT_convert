{
    "title": "Troubleshoot the catalog",
    "linkTitle": "Troubleshoot the catalog",
    "weight": "330"
}## The catalog is full and <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> has stopped

Symptom

Transfer CFT stops and you cannot restart it. To remedy this issue, you can execute the <span class="code">cftcatal </span>tool.

Remedy

You can use the <span class="code">cftcatal </span>utility to increase the size of the Transfer CFT catalog file without losing information. In a multi-node environment, this action resizes all nodes.

Example on Windows or Unix

Execute the <span class="code">profile </span>from the runtime directory and then enter the <span class="code">cftcatal</span> command. Modify the number of records when prompted, for example:



    cftcatal

    CFT Catalog file extension
    Current size of catalog file : 1000
    Number of records in catalog : 1000
    Number of records for catalog file (0=cancel,minimum=10) : 2000
    Extracting current catalog records ......
    New catalog extended to 2000 records and cft can be restarted.