{
    "title": "Manually enable Central Governance ",
    "linkTitle": "Manually enable Central Governance",
    "weight": "230"
}This section describes how to manually modify the Transfer CFT configuration to enable Central Governance connectivity in command line.

## Prerequisites

1.  Stop Transfer CFT and Copilot if running.

2.  Ensure that all UCONF values used to identify a Transfer CFT instance are defined. These parameters include:

    -   cft.full\_hostname
    -   cft.instance\_id
    -   cft.instance\_group

      
    Use the format:  



        CFTUTIL uconfset id=cft.instance_id, value=<cft_id>

## Procedure

The manual procedure consists of the following steps, which are detailed below:

1.  Set the UCONF parameter values for Central Governance.
2.  Enable <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>.
3.  Start Copilot to register.

#### Set UCONF values

Use the <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> installation values for the following UCONF settings. <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> uses these values to identify <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>.

-   cg.host
-   cg.port
-   cg.mutual\_auth\_port
-   cg.shared\_secret

Use the format:



    CFTUTIL uconfset id=cg.host, value=<host_value>

#### Enable <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>



    CFTUTIL uconfset id=cg.enable, value=yes

#### Register

Start the <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> Copilot to trigger an automatic registration with <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>.

You can check in the <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> **Product List** to confirm that the registration was successful.
