{
    "title": "Transfer CFT messages  and error codes",
    "linkTitle": "Messages and error codes",
    "weight": "250"
}This section lists the different types of messages that {{< TransferCFT/componentlongname  >}} generates, and corrective actions when applicable. It begins with this section, which describes message formats, severity, and additional conventions used in this documentation.

## Message format

### Format in the documentation

{{< TransferCFT/componentshortname  >}} messages provide information on the status of the {{< TransferCFT/componentshortname  >}}. Messages have the general format and supporting information:

<span id="Message_format"></span>

### Format in the product

Earlier versions of {{< TransferCFT/componentshortname  >}} used a different message format
than the version 3.1.3 and higher. The error messages displayed in this document use the former, or earlier version, format. If your system uses
the CFTLOG parameter Format = V24,
the log display is as shown below:

**Example**

CFTLOG FORMAT=\[V23,V24\]

-   For V23: CFTT57I
    PART=&part IDF=&idf IDT=&idt &str transfer started
-   For V24: CFTT57I
    &str transfer started   &lt;IDTU=&idtu
    PART=&part IDF=&idf IDT=&idt>

### Auto documented messages

Certain messages that are auto-documented, for example CFTA01I, CFTA02W, CFTA03E, CFTA04F, may not appear in this documentation. These messages are considered self-explanatory.

## Writing conventions

Messages are written according to the following conventions.

### Message description

The {{< TransferCFT/componentshortname  >}} messages use the format CFTxnns, for example CFTC01E. The elements that make up the message format are described in the following sections.

Where:

-   x: message source
-   nn: sequence number
-   s: message severity

### Message source

### Sequence number

The sequence number is an index characterizing the message within a given class.

### Severity

The severity code is described in the following table.

### Symbolic variables used in message text

The table below lists the symbolic variables used in message text.
