{
    "title": "General Transfer CFT protocol diagnostics",
    "linkTitle": "General protocol diagnostics",
    "weight": "450"
}<span id="Diagnostics_format"></span>

## Diagnostics format

The following table defines the DIAGP formats.

DIAGP Formats

## "Mnemonic"-Type DIAGP Codes

A "Mnemonic"-type DIAGP is a "character string"
value providing information on the type of catalog entry or the status
of the transfer associated with this entry. Some codes are specific to
a single protocol.

Specific codes

## "L HH HHH"-Type DIAGP Codes

"L HH HHH"-type DIAGP codes correspond to network connection
rejection diagnostics. The character L indicates a local rejection. H
represents a hexadecimal digit.

The two hexadecimal numbers respectively represent:

-   REASON:
    a reason code according to the network context
-   DIAGN:
    a diagnostic code according to the network context

For the meaning of these codes, refer to the Network
Codes that correspond with the type of network used in the transfer.

## "R HH HHH"-Type DIAGP Codes

"R HH HHH"-type DIAGP codes correspond to network connection
rejection diagnostics. The character "R" indicates a remote
rejection. H represents a hexadecimal digit.

The two hexadecimal digits respectively represent:

-   REASON:
    a reason code according to the network context
-   DIAGN:
    a diagnostic code according to the network context

For the meaning of these codes, refer to the section Network
Codes corresponding to the type of network used by the transfer.

<span id="HHHHHHHH___Type_DIAGP_Codes"></span>

## "HHHHHHHH"-Type DIAGP Codes

"HHHHHHHH"-type DIAGP codes correspond to the error diagnostics
specific to the network or system access software.

They are the "CS" or "NCS" codes.

Refer to
the manufacturer's documentation (system code or network codes, depending
on the type of occurrence).

<span id="eNNsNN___Type_PeSIT_DIAGP_Codes"></span>

## "eNNsNN"-Type PeSIT DIAGP Codes

"eNNsNN"-type PeSIT DIAGP codes correspond to the diagnostics
representing an unexpected event in the protocol automaton (where N represents
a digit).

The two numbers respectively represent:

-   The
    event code for all protocols

For the meaning of this code, refer to [Event Codes (All
Protocols)](../event_codes#Event_codes_for_all_protocols).

-   The
    status code according to the protocol

For the meaning of this code, see
Status Codes for the appropriate
transfer protocol.

<span id="PDU_iNN___Type_PeSIT_DIAG_Codes"></span>

## "PDU iNN"-Type PeSIT DIAGP Codes

"PDU iNN"-type PeSIT DIAGP codes correspond to the Transfer
CFT diagnostics representing the reception of a PeSIT FPDU that does not
conform to protocol specifications (where N represents a digit).

The code NN specifies the FPDU build error code.

For the meaning of this code, see [FPDU
Build Error Codes (PESIT).](#)

<span id="XXX_NNN___Type_PeSIT_DIAG_Codes"></span>

## "XXX NNN"-Type PeSIT DIAGP Codes

"XXX NNN"-type PeSIT DIAGP codes correspond to the Transfer
CFT diagnostics representing the reception of an FPDU with an error diagnostic
code, where X represents a character and N a digit:

-   NNN
    indicates the PeSIT protocol diagnostic in the FPDU
    -   For the meaning of this code, refer to the section
        PESIT Protocol Diagnostic Code.
-   XXX
    represents the mnemonic code of the received FPDU - PeSIT protocol
    -   For the meaning of this code, refer to the section

<span id="NNN_HHHH_Type_ODETTE_DIAGP_Codes"></span>

## "NNN HHHH"-Type ODETTE DIAGP Codes

{{< TransferCFT/componentshortname  >}} diagnostic codes corresponding to the reception of an FPDU
with an error diagnostic code. H represents a hexadecimal digit and N
a digit:

-   NNN
    is a numeric value corresponding to the ODETTE protocol diagnostic code

For the meaning of this code, refer to the section
[Protocol Diagnostic Codes](../protocol_diagnostic_codes).

-   HHHH
    is a hexadecimal value corresponding to the {{< TransferCFT/componentshortname >}} numeric code
    ODETTE protocol

See also{{< TransferCFT/componentshortname  >}} Numeric Codes ODETTE Protocol.

<span id="XXX_HHHH_Type_ODETTE_DIAGP_Codes"></span>

## "XXX HHHH"-Type ODETTE DIAGP Codes

{{< TransferCFT/componentshortname  >}} diagnostic code identifying an FPDU negotiation or send
error in the ODETTE protocol (where H represents a hexadecimal digit and
X a letter):

-   XXX is a Transfer
    CFT mnemonic code - ODETTE protocol. This is an alphanumeric
    value describing the origin of the anomaly or phase during which it occurred.

See also,
{{< TransferCFT/componentshortname  >}} Mnemonic Codes ODETTE Protocol.

-   HHHH
    is a {{< TransferCFT/componentshortname >}} numeric code - ODETTE protocol. This is a hexadecimal
    value corresponding to the internal protocol code.

See also
"[{{< TransferCFT/componentshortname  >}} ODETTE](../../../protocols_start_here/start_here_odette)"
