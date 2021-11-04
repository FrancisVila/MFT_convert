{
    "title": "ctrlpart",
    "linkTitle": "ctrlpart",
    "weight": "520"
}<span id="ctrlpart"></span>

### ctrlpart

#### CFTPART

\[ CTRLPART = { <span style="text-decoration: underline;">IGNORE</span>
| ALL | RPART | SPART } \]

Optional parameter that is relevant only in server mode. When a transfer is initiated by a remote partner, <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> always controls its identity. If the remote sender is not the initial sender, store and forward mode, the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> can choose to control the initial sender identity according to CTRLPART parameter.

-   IGNORE (default): No control of the remote sender identity.
-   ALL: Control of the remote sender identity. If the partner is unknown, the transfer is rejected with message
-   RPART
-   SPART

CFTT15E NPART=&part \_ Not found

 

[Return to Command index](../../)