{
    "title": "After a synchronization point",
    "linkTitle": "Stage After a synchronization point",
    "weight": "420"
}The value of the synchronization point designates:

-   For the sender, the position of
    the last record read in the file
-   For the receiver, the position of the next record to be written

For the receiver, a file type
EXIT (DIRECT = R) with file accessing managed by the user, the
user function has to return to {{< TransferCFT/componentshortname  >}} the value of the synchronization
point, the number of records and the number of bytes written in the file.
This information is used by the monitor to complete the catalog entry
and is supplied to the user function during the RESTART\_TYP stage.

At the sender end for a file type
EXIT (DIRECT = S) or if file accessing is managed by {{< TransferCFT/componentshortname  >}}, the
{{< TransferCFT/componentshortname  >}} has all the information required to set a synchronization
point.

### Fields to define

### Field values
