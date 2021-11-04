{
    "title": "serial",
    "linkTitle": "serial",
    "weight": "3140"
}### serial

#### SEND/RECV CFTSEND/CFTRECV

\[SERIAL ={ <u>' '</u> | Y | X } \]

When sending files sequentially, this value is the processing phase that a serialized transfer must reach before Transfer CFT begins executing the next transfer. For details on processing phases, see <a href="../../../../concepts/phase_and_phasestep" class="MCXref xref">About phase and phasestep</a>.

Use this parameter to define file transfer serialization in flows, where:

-   ' ' : no serialization occurs (default)
-   Y: Post-processing
-   X: Done

See also, [Transfer serialization](../../../../app_integration_intro/transfer_serialization).

[Return to Command index](../../)