{
    "title": "Before repositioning",
    "linkTitle": "Stage Before repositioning",
    "weight": "400"
}At the receiver end (DIRECT = R)
with file accessing managed by the user, the user function has to reposition
using the information (rpos, frecs and fcars) the {{< TransferCFT/componentshortname  >}} provides.

At the sender end (DIRECT = S) or
if file accessing is managed by {{< TransferCFT/componentshortname  >}}, the {{< TransferCFT/componentshortname  >}}
has all the information it requires for repositioning.

In both cases, you can request the restart of the transfer  from
the beginning of the file by setting the ret1 field to 1.

### Fields to define

### Field values
