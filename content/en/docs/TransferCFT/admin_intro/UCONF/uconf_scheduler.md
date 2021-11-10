{
    "title": "UCONF: Configuration scheduling",
    "linkTitle": "Configuration scheduling",
    "weight": "330"
}In <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> you can define daily periods where dynamic configuration variables can be changed. For example, you might want to schedule that the value for cft.purge.sx can be modified during the period between 15:30 and 19:30.

Steps overview

1.  Access the Unified Configuration using either command line or the UI.
2.  Create the configuration alias by adding a new alias name to the <span class="code">cft.scheduled\_values</span> list. Do not use spaces or periods (.) in the alias name.
3.  Configure the remaining parameters as described in the following table to define the new alias.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameters         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>cft.scheduled_values         </td>
         <td>List of scheduled aliases. Use a space to separate alias names.         </td>
      </tr>
      <tr>
         <td>cft.scheduled_values.(alias-id).start_time         </td>
         <td>Start time using the format MM:HH:DAYS_OF_THE_WEEK. This is the begin time for when a value switches from its existing value to the <span class="italic_in_para">temporary value</span>. See <a href="#Details,%20days">Details</a> below.         </td>
      </tr>
      <tr>
         <td>cft.scheduled_values.(alias-id).delay         </td>
         <td><p>Delay using the format MM:HH.</p>
<p>This is the length of time during which the value can be changed.</p>         </td>
      </tr>
      <tr>
         <td>cft.scheduled_values.(alias-id).id         </td>
         <td>The configuration entity id (uconf parameter) that you want to provide scheduling for.         </td>
      </tr>
      <tr>
         <td>cft.scheduled_values.(alias-id).value         </td>
         <td><p><span class="italic_in_para">Temporary value</span>. This value replaces the existing configuration value for the defined uconf parameter.</p>
<p>To find the existing value, in command line enter:</p>
<p>CFTUTIL uconfget id=&lt;uconf_parameter&gt;</p>         </td>
      </tr>
   </tbody>
</table>

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

1.  Add the new alias name to the <span class="code">scheduled\_values</span> list. This example creates a new alias called <span class="italic_in_para">alias04</span>.

        CFTUTIL uconfset id=cft.scheduled_values,value='"alias01 alias02 alias03 alias04"'

2.  Configure the new alias, <span class="italic_in_para">alias04</span>.

        CFTUTIL uconfset id=cft.scheduled_values.alias04.start_time,value='”30:15:5,6”'
        CFTUTIL uconfset id=cft.scheduled_values.alias04.delay,value=00:04
        CFTUTIL uconfset id=cft.scheduled_values.alias04.id,value= cft.purge.sx
        CFTUTIL uconfset id=cft.scheduled_values.alias04.value,value=2

3.  Activate the configuration modification. Enter:

        CFTUTIL reconfig type=UCONF

> **Note:**
>
>  

-   The same configuration value can be scheduled several times in a day.
-   Scheduled periods for the same value can be contiguous, but they should not overlap.

Related topics

-   [About the Unified Configuration interface](../)
-   [Using Unified configuration (UCONF) in the GUI](../uconf_interface_actions)
-   [Using Unified configuration (UCONF) in CFTUTIL](../uconf_w_cftutil)
