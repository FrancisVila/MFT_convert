{
    "title": "Manually enable Central Governance",
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
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTUTIL uconfset id=cft.instance_id, value=&lt;cft_id&gt;</p>
         </td>
      </tr>
   </tbody>
</table>

## Procedure

The manual procedure consists of the following steps, which are detailed below:

1.  Set the UCONF parameter values for Central Governance.
2.  Enable Central Governance.
3.  Start Copilot to register.

#### Set UCONF values

Use the Central Governance installation values for the following UCONF settings. Transfer CFT uses these values to identify Central Governance.

-   cg.host
-   cg.port
-   cg.mutual\_auth\_port
-   cg.shared\_secret

Use the format:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTUTIL uconfset id=cg.host, value=&lt;host_value&gt;</p>
         </td>
      </tr>
   </tbody>
</table>

#### Enable Central Governance

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTUTIL uconfset id=cg.enable, value=yes</p>
         </td>
      </tr>
   </tbody>
</table>

#### Register

Start the Transfer CFT Copilot to trigger an automatic registration with Central Governance.

You can check in the Central Governance **Product List** to confirm that the registration was successful.
