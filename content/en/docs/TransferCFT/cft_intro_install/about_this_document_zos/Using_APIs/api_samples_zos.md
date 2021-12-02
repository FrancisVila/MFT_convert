{
    "title": "Delivered templates for z/OS",
    "linkTitle": "Delivered samples for z/OS",
    "weight": "220"
}This topic lists the {{< TransferCFT/companyname  >}} {{< TransferCFT/componentshortname  >}} API templates that are delivered for the z/OS platform. You may decide to use the delivered samples as a basis for integrating APIs, or as a model to create your own. Templates include samples in:

-   [Assembler language](#Assembl)
-   [C language](#C)
-   [COBOL language](#COBOL)

The {{< TransferCFT/componentshortname  >}} z/OS templates are located in the installed {{< TransferCFT/componentshortname  >}} distribution library.

<span id="Assembl"></span>

## Assembler language

```

Template

Function

Services

AAPIDLL
cftai - cftac - cftinit
COM - SEND - OPEN - CLOSE - (SELECT - NEXT) or (SELECT240 - NEXT240)
AXPIDLL
cftaix - cftac - cftinit
COM - SEND - OPEN - CLOSE - DO - SELECT (NEXT or NEXT240)
```
<span id="C"></span>

## C language

```

Template

Function

Services

Description

CAPI2A
ipcai2\_\*

-   ipcai2\_initialize-ipcai2\_catalog\_open-ipcai2\_catalog\_selection\_new
-   ipcai2\_catalog\_selection\_set
-   ipcai2\_catalog\_selection\_sortby
-   ipcai2\_catalog\_selection\_skip
-   ipcai2\_catalog\_selection\_next
-   ipcai2\_catalog\_record\_get
-   ipcai2\_catalog\_info\_get
-   ipcai2\_catalog\_selection\_delete
-   ipcai2\_catalog\_close-ipcai2\_finalize-
-   ipcai2\_get\_errno\_str

{{< TransferCFT/componentshortname >}} catalog API sample program, listing all catalog content.
CAPI2B
ipcai2\_\*

-   ipcai2\_initialize
-   ipcai2\_catalog\_open
-   ipcai2\_catalog\_selection\_new
-   ipcai2\_catalog\_selection\_set
-   ipcai2\_catalog\_selection\_sortby
-   ipcai2\_catalog\_selection\_skip
-   ipcai2\_catalog\_selection\_next
-   ipcai2\_catalog\_record\_get
-   ipcai2\_catalog\_info\_get
-   ipcai2\_catalog\_selection\_delete
-   ipcai2\_catalog\_close
-   ipcai2\_finalize
-   ipcai2\_get\_errno\_str

{{< TransferCFT/componentshortname >}} catalog API sample program, which changes all Terminated transfers to Ended.
CAPIC
cftai - cftac - cftau
OPEN- SELECT - NEXT - MODIFY - CLOSE - SEND -RECV - HALT - START - DELETE
C Sample for {{< TransferCFT/componentshortname >}} API.
CAPISYN
cftau
COM - SEND - GETXINFO - SWAITCAT
{{< TransferCFT/componentshortname >}} communication sample program using
Synchronous Communication media (multiple send commands are possible).
CAPIW
cftai - cftau
SEND - OPEN - CLOSE - (SELECT - NEXT) or (SELECT240 - NEXT240)
Perform a SEND request with an IDA and wait for the transfer to end (completed) until the timer expires or the transfer is aborted.
CAPIX
cftaix
OPEN - CLOSE - SELECT (NEXT - NEXT240) - SORT - DO - COUNT
A C language template for a catalog list with selection and sorting.
```
<span id="COBOL"></span>

## COBOL language

```

Template

Function

Services

Description

OAPI2A
ipcai2\_\*

-   ipcai2\_initialize
-   ipcai2\_catalog\_open
-   ipcai2\_catalog\_selection\_new
-   ipcai2\_catalog\_selection\_set
-   ipcai2\_catalog\_selection\_sortby
-   ipcai2\_catalog\_selection\_skip
-   ipcai2\_catalog\_selection\_next
-   ipcai2\_catalog\_record\_get
-   ipcai2\_catalog\_info\_get
-   ipcai2\_catalog\_selection\_delete
-   ipcai2\_catalog\_close
-   ipcai2\_finalize
-   ipcai2\_get\_errno\_str

{{< TransferCFT/componentshortname >}} catalog API template program, which lists all catalog content.
OAPI2AS
ipcai2\_\*

-   ipcai2\_initialize
-   ipcai2\_catalog\_open
-   ipcai2\_catalog\_selection\_new
-   ipcai2\_catalog\_selection\_set
-   ipcai2\_catalog\_selection\_sortby
-   ipcai2\_catalog\_selection\_skip
-   ipcai2\_catalog\_selection\_next
-   ipcai2\_catalog\_record\_get
-   ipcai2\_catalog\_info\_get
-   ipcai2\_catalog\_selection\_delete
-   ipcai2\_catalog\_close
-   ipcai2\_finalize
-   ipcai2\_get\_errno\_str

{{< TransferCFT/componentshortname >}} catalog API template program, which lists all of the catalog content.
OAPI2B
ipcai2\_\*

-   ipcai2\_initialize-
-   ipcai2\_catalog\_open
-   ipcai2\_catalog\_selection\_new
-   ipcai2\_catalog\_selection\_set
-   ipcai2\_catalog\_selection\_sortby
-   ipcai2\_catalog\_selection\_skip
-   ipcai2\_catalog\_selection\_next
-   ipcai2\_catalog\_record\_get
-   ipcai2\_catalog\_info\_get
-   ipcai2\_catalog\_selection\_delete
-   ipcai2\_catalog\_close
-   ipcai2\_finalize
-   ipcai2\_get\_errno\_str

{{< TransferCFT/componentshortname >}} catalog API template program, which changes all successful transfers to a completed state.
OAPI2BS
ipcai2\_\*

-   ipcai2\_initialize
-   ipcai2\_catalog\_open
-   ipcai2\_catalog\_selection\_new
-   ipcai2\_catalog\_selection\_set
-   ipcai2\_catalog\_selection\_sortby
-   ipcai2\_catalog\_selection\_skip
-   ipcai2\_catalog\_selection\_next
-   ipcai2\_catalog\_record\_get-
-   ipcai2\_catalog\_info\_get-
-   ipcai2\_catalog\_selection\_delete-
-   ipcai2\_catalog\_close-
-   ipcai2\_finalize-
-   ipcai2\_get\_errno\_str

{{< TransferCFT/componentshortname >}} catalog API template program, which changes all successful transfers to the completed state.
OAPIC
CFTC
SEND -RECV - HALT - START - DELETE
Issue {{< TransferCFT/componentshortname >}} commands.
OAPICS
CFTC
SEND -RECV - HALT - START - DELETE
Issue {{< TransferCFT/componentshortname >}} commands
OAPII
CFTI
OPEN - CLOSE - (SELECT - NEXT) or (SELECT240 - NEXT240)
List the {{< TransferCFT/componentshortname >}} catalog.
OAPIIS
CFTI
OPEN - CLOSE - (SELECT - NEXT) or (SELECT240 - NEXT240)
List the {{< TransferCFT/componentshortname >}} catalog.
OAPISYN
cftau
COM - SEND - GETXINFO - SWAITCAT
{{< TransferCFT/componentshortname >}} communication sample program using
the synchronous communication media, where multiple SEND commands are possible.
OAPIW
CFTI - CFTU
SEND, OPEN, CLOSE , (SELECT - NEXT), or (SELECT240 - NEXT240)
Perform a SEND request with an IDA and wait for the transfer to complete successfully, reach the time out, or abort the transfer.
OAPIWS
CFTI - CFTU
SEND - OPEN - CLOSE - (SELECT - NEXT) or (SELECT240 - NEXT240)
Perform a SEND request with an IDA and wait for the transfer to complete successfully, reach the time out, or abort the transfer.
```

 

```

Template

Function

Services

OAPI2A
ipcai2\_\*

-   ipcai2\_initialize
-   ipcai2\_catalog\_open
-   ipcai2\_catalog\_selection\_new
-   ipcai2\_catalog\_selection\_set
-   ipcai2\_catalog\_selection\_sortby
-   ipcai2\_catalog\_selection\_skip
-   ipcai2\_catalog\_selection\_next
-   ipcai2\_catalog\_record\_get
-   ipcai2\_catalog\_info\_get
-   ipcai2\_catalog\_selection\_delete
-   ipcai2\_catalog\_close
-   ipcai2\_finalize
-   ipcai2\_get\_errno\_str

OAPI2AS
ipcai2\_\*

-   ipcai2\_initialize
-   ipcai2\_catalog\_open
-   ipcai2\_catalog\_selection\_new
-   ipcai2\_catalog\_selection\_set
-   ipcai2\_catalog\_selection\_sortby
-   ipcai2\_catalog\_selection\_skip
-   ipcai2\_catalog\_selection\_next
-   ipcai2\_catalog\_record\_get
-   ipcai2\_catalog\_info\_get
-   ipcai2\_catalog\_selection\_delete
-   ipcai2\_catalog\_close
-   ipcai2\_finalize
-   ipcai2\_get\_errno\_str

OAPI2B
ipcai2\_\*

-   ipcai2\_initialize-
-   ipcai2\_catalog\_open
-   ipcai2\_catalog\_selection\_new
-   ipcai2\_catalog\_selection\_set
-   ipcai2\_catalog\_selection\_sortby
-   ipcai2\_catalog\_selection\_skip
-   ipcai2\_catalog\_selection\_next
-   ipcai2\_catalog\_record\_get
-   ipcai2\_catalog\_info\_get
-   ipcai2\_catalog\_selection\_delete
-   ipcai2\_catalog\_close
-   ipcai2\_finalize
-   ipcai2\_get\_errno\_str

OAPI2BS
ipcai2\_\*

-   ipcai2\_initialize
-   ipcai2\_catalog\_open
-   ipcai2\_catalog\_selection\_new
-   ipcai2\_catalog\_selection\_set
-   ipcai2\_catalog\_selection\_sortby
-   ipcai2\_catalog\_selection\_skip
-   ipcai2\_catalog\_selection\_next
-   ipcai2\_catalog\_record\_get-
-   ipcai2\_catalog\_info\_get-
-   ipcai2\_catalog\_selection\_delete-
-   ipcai2\_catalog\_close-
-   ipcai2\_finalize-
-   ipcai2\_get\_errno\_str

OAPIC
CFTC
SEND -RECV - HALT - START - DELETE
OAPICS
CFTC
SEND -RECV - HALT - START - DELETE
OAPII
CFTI
OPEN - CLOSE - (SELECT - NEXT) or (SELECT240 - NEXT240)
OAPIIS
CFTI
OPEN - CLOSE - (SELECT - NEXT) or (SELECT240 - NEXT240)
OAPISYN
cftau
COM - SEND - GETXINFO - SWAITCAT
OAPIW
CFTI - CFTU
SEND, OPEN, CLOSE , (SELECT - NEXT), or (SELECT240 - NEXT240)
OAPIWS
CFTI - CFTU
SEND - OPEN - CLOSE - (SELECT - NEXT) or (SELECT240 - NEXT240)
```
