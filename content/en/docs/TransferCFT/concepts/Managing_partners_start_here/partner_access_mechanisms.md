{
    "title": "Partner access mechanisms",
    "linkTitle": "Partner access mechanisms",
    "weight": "240"
}# <span id="About_Direct_or_Indirect_partner_access_transfers"></span><span id="Partner_access_mechanisms"></span>Partner access mechanisms

A SEND/RECV transfer command can perform one or more transfers with:

A single partner
via a direct connection

A single partner
via an intermediate partner or store and forward site with a transfer
in store and forward mode transfer type

Several partners
via a direct connection, where the transfer type can be:

-   Broadcasting: for sending
    (SEND command)
-   Collecting: for receiving (RECV command)

Send transfers (SEND command) can also:

-   Combine store and
    forward and broadcasting
-   Activate broadcasting
    on a store and forward site

### Direct transfer - partner recognition

The Transfer CFT mechanisms to be used to connect a requester to a server
are:

-   Network and protocol
    connection
-   Application connection -
    the SAP

The Transfer CFT reciprocal recognition mechanism is then defined.

This mechanism is based on the names of each of the parties involved.
To optimize use of the parameter setting possibilities, the following
is indicated:

-   The Transfer CFT
    parameters defining the names of the parties involved
-   The recognition
    mechanism itself, based on the network names
-   In
    generic examples that display the various parameter settings possible
    for using this mechanism
