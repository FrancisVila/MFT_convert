{
    "title": "ntype",
    "linkTitle": "ntype",
    "weight": "2360"
}<span id="ntype"></span>

### ntype

#### CFTSEND, SEND

**\[NTYPE = {<u>see comment</u> | c}\]
       ODETTE,
PeSIT D CFT profile, PeSIT E CFT/CFT,  OS**

File type, in protocol terms.

This parameter is used to designate the partner receiver file type.

```
**PeSIT D CFT profile
PeSIT E CFT/CFT**
If this parameter is not defined, Transfer
CFT assigns a default value, as a function of the:

-   local
    file type (FTYPE parameter),
-   operating
    system of the transfer recipient (SYST parameter of CFTPART).

The default values are indicated in *NTYPE sent by default*.
**ODETTE**
The specific value NTYPE = T may be used to request the
sending of a file in ODETTE text format. Refer to Managing Protocols.
```

 

[Return to Command index](../../)
