{
    "title": "time",
    "linkTitle": "time",
    "weight": "3490"
}<span id="time"></span>

### 

#### CFTCRON

`TIME =   { string | @shutdown | @startup   }`

Starts batch
commands.

- string
- @shutdown - starts a batch procedure after stopping CFT monitor services
- @startup - starts a batch procedure at the end of the {{< TransferCFT/componentshortname >}} initialization
    procedure when {{< TransferCFT/componentshortname >}} starts but before any transfers procedure
