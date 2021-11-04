{
    "title": "time",
    "linkTitle": "time",
    "weight": "3480"
}<span id="time"></span>

### <span class="mc-variable System.Title variable">time</span>

#### CFTCRON

TIME =
{ string | @shutdown | @startup
}

Starts batch
commands.

-   string
-   @shutdown - starts a batch procedure after stopping CFT monitor services
-   @startup - starts a batch procedure at the end of the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> initialization
    procedure when <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> starts but before any transfers procedure
