{
    "title": "Restart a SAG",
    "linkTitle": "Restart an SAG",
    "weight": "320"
}This procedure explains the steps to restart a SAG (SWIFT Alliance Gateway):

1.  Before shutting down the SAG/SNL, stop the active SWIFTNet Remote Sites linked to this SAG/SNL.
2.  After the SAG/SNL is restarted and their status is up and running, restart the previously stopped SWIFTNet remote sites.
3.  Once the SWIFTNet remote sites are restarted, check the status of the SnF queue.  
    Use the command <span class="code">peldsp status\_swoutputsession </span>  
    See <a href="../../swiftnet_input_channels/swiftnet_output_channels" class="MCXref xref">SWIFTNet queues and output channels</a>
4.  If a queue status is not acquired, then either:
    -   restart the related SWIFTNet remote site, or
    -   use the Gateway command to do the reacquisition, such as:  
        <span class="code">pelctl acquire\_swqueue -qn queue\_name -si remote\_site -f</span>

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
