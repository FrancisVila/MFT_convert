{
    "title": "Configure holiday schedule",
    "linkTitle": "Configure holiday schedules",
    "weight": "220"
}You can specify holiday dates for the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> system and use them later when creating scheduled transfers or tasks. Having set up official holiday dates, you can take one of the following actions when creating a scheduled task or transfer:

-   Ignore the holiday schedule – this is the default option
-   Take no action if the scheduled date happens to be a holiday specified in the holiday schedule

Keep the following items in mind when listing holiday dates:

-   The list of holidays applies to all users on the server – it is not dependent on the time zones of users. The dates specified as scheduled are interpreted in local time by the server.
-   The Holiday Schedule functionality does not allow for executing a scheduled task on the next working day if the specified date happens to be a holiday – when this occurs, the tasks are not executed.
-   Weekend days are treated as holidays by default.

For information about creating scheduled transfers, see <a href="../../accounts/c_st_subscriptions/t_st_subscriptions#Schedule" class="MCXref xref">Scheduled downloads and tasks</a> and <a href="../../accounts/c_st_subscriptions/t_st_subscriptions#Set" class="MCXref xref">Set up a scheduled transfer task for a subscription</a>.

1.  Click **Setup > Holiday Schedule**.  
    The *Holiday Schedule* page is displayed.
2.  Enter one or more holiday dates in the **Holiday Schedule** field.  
    Use the *MM*/*dd*/*yyyy* date format. If you enter more than one date, separate them with commas.
3.  Click **Update**.  
    The configured Holiday Schedule applies to all users of the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> server and is applicable for all accounts and transfers.