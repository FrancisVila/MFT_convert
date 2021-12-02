{
    "title": "UCONF: Configuration scheduling",
    "linkTitle": "Configuration scheduling",
    "weight": "330"
}In {{< TransferCFT/componentshortname  >}} you can define daily periods where dynamic configuration variables can be changed. For example, you might want to schedule that the value for cft.purge.sx can be modified during the period between 15:30 and 19:30.

Steps overview

1.  Access the Unified Configuration using either command line or the UI.
2.  Create the configuration alias by adding a new alias name to the `cft.scheduled_values` list. Do not use spaces or periods (.) in the alias name.
3.  Configure the remaining parameters as described in the following table to define the new alias.

<span id="Details, days"></span>Details

DAYS\_OF\_WEEK:

-   A star ‘\*’ indicates every day of the week.
-   Indicate one or several days between Monday (0) and Sunday (6) using the digits separated by a comma (,).
-   Indicate a range of days using the minus (-) sign.
-   Examples of start\_time using different of DAY\_OF\_WEEK formats:
    -   10:11:\* : 11h10 indicates every day of the week
    -   10:11:1 : 11h10 indicates every Tuesday
    -   10:11:0,2,4-6 : 11h10 indicates every Monday, Wednesday, Friday, Saturday and Sunday

Example

This example defines a schedule where the value of cft.purge.sx can be changed during the period that begins at 15:30 and has a duration of 4 hours on Saturday and Sunday.

1.  Add the new alias name to the `scheduled_values` list. This example creates a new alias called .
2.  Configure the new alias, .
3.  Activate the configuration modification. Enter:

> **Note:**
>
>  

-   The same configuration value can be scheduled several times in a day.
-   Scheduled periods for the same value can be contiguous, but they should not overlap.

Related topics

-   [About the Unified Configuration interface](../)
-   [Using Unified configuration (UCONF) in the GUI](../uconf_interface_actions)
-   [Using Unified configuration (UCONF) in CFTUTIL](../uconf_w_cftutil)
