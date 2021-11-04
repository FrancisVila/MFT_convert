{
    "title": "nrpart",
    "linkTitle": "nrpart",
    "weight": "2280"
}<span id="nrpart"></span>

### CFTPART

**\[NRPART = {<u>value of the NPART
parameter of CFTPARM</u> | *string*}\]**

-   string24     PeSIT  
-   string25     ODETTE
-   string64     SFTP  

Network identifier by which the
remote partner identifies itself to the local <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> (for incoming calls).

The local partner must retrieve the CFTPART description such that the
associated NSPART parameter corresponds to this value.

The partner must use this name to identify itself to the <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> during the connection phase. On the partner side, this value corresponds to the NSPART parameter of the CFTPART command that describes the local Transfer CFT.

**ODETTE: **In server mode, there
may be several CFTPART objects with the same NRPART. For this purpose,
IMINTIME = IMAXTIME should be specified.

 

 

[Return to Command index](../../)

 
