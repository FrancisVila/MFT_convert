{
    "title": "filtertype",
    "linkTitle": "filtertype",
    "weight": "1190"
}\[ filtertype = { <u>STRJCMP</u> | EREGEX } \]

Defines the type of filter to be applied when sending a generic transfer.

-   STRJCMP: internally filter matches with \* and ?
-   EREGEX: applies a regular expression filter

To replicate the filter behavior of previous Transfer CFT versions, select STRJCMP (default) as the filtertype and leave the [filter](../filter) parameter empty.

See also Sending a group of files &gt; [Create filters using CFTSEND](../../../../concepts/using_the_send_command/send_group_of_files_cl).

[Return to Command index](../../)