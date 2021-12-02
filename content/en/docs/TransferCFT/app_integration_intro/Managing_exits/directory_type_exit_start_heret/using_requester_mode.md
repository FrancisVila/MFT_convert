{
    "title": "Using requester mode",
    "linkTitle": "Using requester mode",
    "weight": "390"
}The communication structure is defined by the interface before
the user function is called. You must provide, complete, or modify the
parameters that {{< TransferCFT/componentshortname  >}} needs to establish network and protocol connections.

The initialization function and the user function, if needed, are called
when connection requests are made, even for network and protocol connection
attempts (retries) or store and forward operations.

If the partner is:

-   Known to Transfer
    CFT: the communication structure fields indicate the values of the CFTPART
    and CFTTCP corresponding to the partner
-   Not known to Transfer
    CFT: the only fields containing valid data are the general information
    fields and the fields contained in the following table (partner information
    fields)

### Partner information fields

 

When {{< TransferCFT/componentshortname  >}} does not know the partner, the following fields are
empty:

-   ipart: intermediate
    partner local identifier
-   sap: remote Sap
    (Service Access Point)
-   addr: remote partner
    address

The **ret1** return code field must
be defined when the user function is returned from.

If there is a connection refusal (return code value of 2), the ret2
field may be defined to make the cause of the refusal appear in the DIAGI
field of the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> catalog.

The content of the diag field appears with the appropriate error message
if the return code is not 0 and 1.

If the msg field is defined, its content is sent to the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>
standard output.

If the return code value is 0 or 1, you can modify all the fields
except the general information fields or the ptype and ntype fields.

Field descriptions

During network and protocol connection attempts, the fields that can
be modified and whose values are kept relative to the last call of the
user function are:

-   part: partner local
    identifier
-   idprot: protocol
    identifier
-   nrpart: remote
    partner name

Users can query an electronic directory (X500, DNS, ...) or their own
bases to locate their information (network name, password, remote sap,
remote partner address, and so on).
