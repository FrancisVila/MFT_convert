{
    "title": "Use the communication structure",
    "linkTitle": "Using the communication structure",
    "weight": "360"
}The following topics describe the stages in a file transfer. These are:

-   [Before
    the file is allocated](#Before_the_File_is_Allocated)
-   [Before
    the file is opened](#Before_the_File_is_Opened)
-   [Before
    the start of the transfer](#Before_the_Start_of_the_Transfer)
-   [Before
    a record is sent or after it is received](#Before_a_Record_is_Sent_or_After_it_is_Received)
-   Before
    repositioning
-   After
    a synchronization point
-   Before
    the end of the file
-   Before
    the file is closed
-   Before
    the end of the transfer
-   After
    a transfer interruption

Each stage is explained in a table as follows:

-   Fields to define - the first table indicates the fields that you must update
-   Field values - the second table indicates the
    values for each field of the communication area as seen from the sender
    or the receiver side before and after the call.  

The symbols used are indicated in the following table.

The return code (ret1) must always be defined.

<span id="Before_the_File_is_Allocated"></span>

## Before the file is allocated

This is the first stage in a file transfer. During this stage, you indicate
the stages at which you want to take control by defining the masc parameter.

<span id="Fields_to_define"></span>

### Fields to define

<span id="Field_values"></span>

### Field values

<span id="Before_the_File_is_Opened"></span>

## Before the file is opened

If the user function manages file accessing, it must open the file at
this stage.

### Fields to define

### Field values

<span id="Before_the_Start_of_the_Transfer"></span>

## Before the start of the transfer

Only a File type EXIT at the sender end, DIRECT = S’ can process this
stage.

### Fields to define

### Field values

<span id="Before_a_Record_is_Sent_or_After_it_is_Received"></span>

## Before a record is sent or after it is received

At the sender end, DIRECT =
S, the user function is called before the record is sent to the
remote site, and after the record is read if {{< TransferCFT/componentshortname  >}} manages file
accessing. If file accessing is managed by the user function, the latter
has to read the record and define the ldata field as well as the zdata
parameter before handing back control to {{< TransferCFT/componentshortname  >}}.

At the receiver end, DIRECT = R,
the user function is called after the record is received, and before the
record is written if {{< TransferCFT/componentshortname  >}} manages file accessing. If file accessing
is managed by the user function, the latter has to write the record before
handing back control to {{< TransferCFT/componentshortname  >}}.

At this stage (DATA\_TYP) and before the record is sent or after it is
received, the user function can perform the following operations:

-   Modify the record
    sent or to be sent
-   Insert one or more
    records
-   Delete the record
-   Set the "END
    of FILE" event

### Fields to define

#### Compression

Records are compressed as a result of a negotiation between the sender
partner and the receiver partner. At the
sender end, records are compressed before being sent by the {{< TransferCFT/componentshortname  >}}. At the receiver end, the
records are decompressed by the {{< TransferCFT/componentshortname  >}} immediately after
they are received. The records {{< TransferCFT/componentshortname  >}} supplies to the user function
are never in compressed form.

The ncomp field designates the compression algorithm used. The default
value of this field is the value specified in the NCOMP parameter of the
CFTSEND or CFTRECV command associated with the File type EXIT.

The user function can modify the ncomp field at the first stage in the
transfer (ALLOC\_TYP). A zero value inhibits compression.

### Field values
