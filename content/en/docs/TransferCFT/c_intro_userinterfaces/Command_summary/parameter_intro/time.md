{
    "title": "time",
    "linkTitle": "time",
    "weight": "3510"
}### <span id="time"></span>time

#### CFTCRON

TIME =
{ string | @shutdown | @startup
}

Starts batch
commands.

-   string
-   @shutdown - starts a batch procedure after stopping CFT monitor services
-   @startup - starts a batch procedure at the end of the Transfer CFT initialization
    procedure when Transfer CFT starts but before any transfers procedure
