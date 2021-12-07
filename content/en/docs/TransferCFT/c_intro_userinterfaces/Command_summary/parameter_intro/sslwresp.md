{
    "title": "sslwresp",
    "linkTitle": "sslwresp",
    "weight": "3350"
}<span id="sslwresp"></span>

### sslwresp

#### CFTPARM

**\[SSLWRESP =   {1...32767
} \]**

The timeout granted to an SSL task to start and return
its initialization status, which can be any
value from <span style="font-weight: bold;">1</span> to <span style="font-weight: bold;">32767</span> seconds.

Default values per operating system:

-   60:  Windows
-   100:  UNIX
-   600:  z/OS (MVS)
-   1000:  OS/400 (IBM i)

If no status is returned within this time limit,  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> considers
that the task could not be initialized and defers the transfer in requester
mode, or closes the network connection in server mode.

 

[Return to Command index](../../)
