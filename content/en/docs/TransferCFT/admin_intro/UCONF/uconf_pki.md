{
    "title": "UCONF: PKI and PassPort PS options",
    "linkTitle": "PKI and PassPort PS",
    "weight": "300"
}This topic presents the parameters to set to define Transfer CFT{{< TransferCFT/componentshortname  >}} to PassPort PS server connectivity.  You can define this connectivity in Transfer CFT{{< TransferCFT/componentshortname  >}} using
a command line window.

****PassPort PS parameters****

To enable Transfer CFT{{< TransferCFT/componentshortname  >}} to PassPort PS server connectivity, use the UCONFSET
command to set the following parameters:

```
CFTUTIL
UCONFSET ID= pki.type, value=”passport”
CFTUTIL
UCONFSET ID= pki.passport.hostname, value=”xxxx”
CFTUTL
UCONFSET ID= pki.passport.port, value=”xxxx”
```

Refer to the [UCONF parameters](../uconf_directory) table for information on the `pki.passport `type parameters.
