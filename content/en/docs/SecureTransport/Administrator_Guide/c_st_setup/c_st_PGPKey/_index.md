{
    "title": "PGP key encryption and signing",
    "linkTitle": "PGP key encryption and signing",
    "weight": "90"
}SecureTransport supports PGP encryption. The system handles the generation and storing of PGP keys and the management of the stored keys. The PGP keys are managed from the Administration Tool.

PGP signature verification, encryption, and signing do not work properly when the PGP key has expired. However, SecureTransport continues to decrypt files successfully even when the PGP key has expired.

PGP encryption and signing only support ZIP, BZIP2, and ZLIB compression.

PGP verification is performed using the current time on the computer, not the time when signing occurred.

The following topics describe how to manage the PGP keys and provide the PGP key transfer dependencies:

-   [Manage PGP keys](t_st_pgpkey)
-   [PGP transfer settings dependencies](r_st_pgptransfersettingsdependencies)
