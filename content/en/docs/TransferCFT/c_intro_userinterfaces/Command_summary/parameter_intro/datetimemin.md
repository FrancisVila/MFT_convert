{
    "title": "datetimemin",
    "linkTitle": "datetimemin",
    "weight": "640"
}### datetimemin

#### LISTLOG

\[ DATETIMEMIN { <u>0</u> | 99123123595999 } \]

Use to display logs that happened on or after this start date and time. The default of <u>0</u> indicates no check.

#### LISTCAT, DISPLAY

\[ DATETIMEMIN { 0 | 99991231235959 } \]

Use to display catalog transfers that happened on or after this start date and time according to the transfer record creation (DATEK, TIMEK). The default value unit is DAY. This parameter accepts either absolute or relative values. Use the syntactical format where:

-   Relative values are: -1, -1M, -1H, -1D
-   Absolute values are: YYYYMMDDhhmmss with a maximum of 14 characters

You can use this parameter in combination with <a href="../datetimemax" class="MCXref xref">datetimemax</a>.

Relative example

Absolute example

[Return to Command index](../../)
