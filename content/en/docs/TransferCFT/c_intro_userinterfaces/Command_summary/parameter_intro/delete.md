{
    "title": "delete",
    "linkTitle": "delete",
    "weight": "660"
}<span id="Delete"></span>

#### delete

#### CFTRECV, CFTSEND

**\[DELETE = {<u>NO</u> | YES}\]**

Automatically deletes the catalog entries in the "X" phase
(done) for the corresponding IDF.

If the user specifies end-of-transfer procedures (EXECSF and EXECRF
parameters of CFTPARM), the catalog entries are only deleted after these
procedures are executed.

If file store and forward is requested (via the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> parameter
setting), none of the catalog entries, associated with terminated transfers,
are deleted.

Select one of the following:

-   NO:
    (default value)
-   YES:
    (automatic deletion)

[Return to Command index](../../)