{
    "title": "Using Base64 or PEM data ",
    "linkTitle": "Using base64",
    "weight": "310"
}The {{< TransferCFT/transfercftname  >}} PKICER command can use Base64 or PEM data instead of a file in order to, for example, send a certificate and key by REST API.

## Importing

The IDATA and INAME parameters and the IKDATA and IKNAME parameters are mutually exclusive.

## Exporting

When exporting data from the PKI database, you can extract the data in Base64 instead of files. By doing this, no files are created other than the command file.

For instance, with the following base:

By default, PKIEXT uses INAME/IKNAME to create the PKICER/PKIKEY objects:

This exports a `FOO.cmd` file, where additional files are created containing the following data:

-   ROOT0001: the ROOT DER certificate
-   USER0002: the INTER DER certificate
-   USER0003: the USER DER certificate
-   USERK003: the USER private key in KPRIV format
-   KPRIV004: the PRIV private key in KPRIV format
-   KPUB0004: the PRIV public key in ssh-rsa format

By contrast, the Base64 option uses the IDATA/IKDATA parameters to extract a single `BAR.cmd` file instead of files.
