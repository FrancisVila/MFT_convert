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
    ```
    CFTUTIL uconfset id=cft.instance\_id, value=<cft\_id>
    ```

## Procedure

The manual procedure consists of the following steps, which are detailed below:

1.  Set the UCONF parameter values for Central Governance.
2.  Enable {{< TransferCFT/centralgovernancename >}}.
3.  Start Copilot to register.

#### Set UCONF values

Use the {{< TransferCFT/centralgovernancename  >}} installation values for the following UCONF settings. {{< TransferCFT/transfercftname  >}} uses these values to identify {{< TransferCFT/centralgovernancename  >}}.

-   cg.host
-   cg.port
-   cg.mutual\_auth\_port
-   cg.shared\_secret

Use the format:

```
CFTUTIL uconfset id=cg.host, value=<host\_value>
```

#### Enable {{< TransferCFT/centralgovernancename  >}}

```
CFTUTIL uconfset id=cg.enable, value=yes
```

#### Register

Start the {{< TransferCFT/transfercftname  >}} Copilot to trigger an automatic registration with {{< TransferCFT/centralgovernancename  >}}.

You can check in the **Product List** to confirm that the registration was successful.
