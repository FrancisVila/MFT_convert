{
    "title": "Map Transfer CFT and Sentinel states",
    "linkTitle": "Mapping Transfer CFT and Sentinel states",
    "weight": "250"
}You can use the **Mapping states** table to find equivalent states and phases as described below.

-   Phase: The phase indicates where you are in your transfer.
-   Phasestep: Within each phase there is a phase step, which is either a process or a step.
-   Diag: Diagnostic codes provide a explanation of the source of the error detected or the refusal.
-   {{< TransferCFT/componentshortname >}} state: The {{< TransferCFT/componentshortname >}} status as displayed in the catalog.
-   Compatibility state: The {{< TransferCFT/componentshortname >}} status as displayed in the catalog when using the backward compatibility mode.
-   Sentinel state: The state attribute identifies the step of the transfer process.

For details on Sentinel states, see XFBTransfer Tracked Objects.

Mapping states

In the following table, the state that is sent to Sentinel when the COMPAT parameter is set to NO, is displayed in the Sentinel state column. When COMPAT is set to YES, the state listed in the Compatible Sentinel state column is sent to Sentinel. For more information on the COMPAT settings, see [{{< TransferCFT/componentshortname  >}} backward compatibility](../../../concepts/phase_and_phasestep/processing_compatability).
