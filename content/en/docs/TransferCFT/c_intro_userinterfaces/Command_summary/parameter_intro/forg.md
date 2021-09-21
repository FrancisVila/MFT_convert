{
    "title": "forg",
    "linkTitle": "forg",
    "weight": "1280"
}### <span id="forg"></span>forg

#### <span id="forg_CFTRECV"></span>CFTRECV, RECV, <span id="forg_CFTSEND"></span>CFTSEND, SEND

\[FORG = {SEQ | DIRECT | INDEXED}\]
  

Organization of the file to be transferred:

-   SEQ:
    sequential
-   INDEXED:
    indexed
-   DIRECT:
    direct access (relative)

With certain operating systems, the sequential reception mechanism may
allow data to be loaded into a non-sequential organization file (normally
pre-existing). Depending on the case, the explicit use of parameters such
as FTYPE, FKEYLEN, FKEYPOS and FORG may be required.

For further information, refer to the Transfer CFT *"Operations
Guide"* corresponding to your OS.

[Return to Command index](../../)