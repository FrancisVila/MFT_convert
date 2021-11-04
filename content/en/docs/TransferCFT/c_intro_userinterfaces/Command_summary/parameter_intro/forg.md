{
    "title": "forg",
    "linkTitle": "forg",
    "weight": "1250"
}<span id="forg"></span>

### forg

<span id="forg_CFTRECV"></span><span id="forg_CFTSEND"></span>

#### CFTRECV, RECV, CFTSEND, SEND

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

For further information, refer to the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> *"Operations
Guide"* corresponding to your OS.

[Return to Command index](../../)