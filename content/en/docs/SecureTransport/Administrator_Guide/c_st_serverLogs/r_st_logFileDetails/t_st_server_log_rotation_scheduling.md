{
    "title": "Server log rotation and monitor scheduling",
    "linkTitle": "Server log rotation scheduling",
    "weight": "360"
}> **Note:**
>
> For another way to schedule server log rotation, see Transfer Log Maintenance application and Log Entry Maintenance application.

Log files are rotated so that you do not lose any information because you have reached a file size limit. The log rotation schedule for log4j files is specified in the log4j configuration files. All other log files are rotated on a regular schedule as directed by a log rotation scheduling tool.

To update schedule of monitor and rotate scripts, the administrator must edit the `<FILEDRIVEHOME>/conf/monitor.schedule.properties` file.

The syntax for schedule is:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field name         </th>
<th style="text-align: center;" class="HeadE-Column1-Header1">Mandatory         </th>
<th class="HeadE-Column1-Header1">Allowed values         </th>
<th class="HeadD-Column1-Header1">Allowed special characters         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Seconds         </td>
         <td>yes         </td>
         <td>0-59         </td>
         <td>, - * /         </td>
      </tr>
      <tr>
         <td>Minutes         </td>
         <td>yes         </td>
         <td>0-59         </td>
         <td>, - * /         </td>
      </tr>
      <tr>
         <td>Hours         </td>
         <td>yes         </td>
         <td>0-23         </td>
         <td>, - * /         </td>
      </tr>
      <tr>
         <td>Day of month         </td>
         <td>yes         </td>
         <td>1-31         </td>
         <td>, - * ? / L W         </td>
      </tr>
      <tr>
         <td>Month         </td>
         <td>yes         </td>
         <td>1-12 or JAN-DEC         </td>
         <td>, - * /         </td>
      </tr>
      <tr>
         <td>Day of week         </td>
         <td>yes         </td>
         <td>1 to 7 or SAT-SUN         </td>
         <td>, - * ? / L #         </td>
      </tr>
      <tr>
         <td>Year         </td>
         <td>no         </td>
         <td>Empty, 1970-2099         </td>
         <td>, - * /         </td>
      </tr>
   </tbody>
</table>

 

Example usage of special characters:

-   (“all values”) – represents all values within a field. For example, \* in the minute field means “every minute”.  
    Example use: \* \* \* \* \* \* \* – will fire the job every second, every minute, every hour, every day, every day-of-week, every month, every year.  
-   (“no specific value”) – use this operator when you don't want to specify a day of month or day in week; it basically means "any", as in "any day-of-week".  
    Example use: \* \* \* \* \* ? \* – will fire that job every second, every minute, every hour, every day, every month, any day-of-week, every year.  
-   – use the hyphen to specify ranges. For example, “1-3” in the day field means “first, second and third day in the month”.  
    Example use: \* \* \* 1-3 \* ? \* – will fire that job every second, every minute, every hour, days 1, 2 and 3 of the month, every month, any day-of-week, every year.  
-   – use the comma as a divider between values. For example, “TUE, THU” in the day-of-week field means “On Tuesday and Thursday”.  
    Example use: \* \* \* \* \* TUE, THU \* – will fire that job every second, every minute, every hour, any day of the month, every month, Tuesday and Thursday, every year.  
-   – use the slash to specify increments. For example, “0/10” in the seconds field means “the seconds 0, 10, 20, 30, 40 and 50”. And “5/15” in the seconds field means “the seconds 5, 20, 35, and 50”. You can also specify ‘/’ after the ‘’ character – in this case ‘’ is equivalent to having ‘0’ before the ‘/’. ‘1/3’ in the day-of-month field means “fire every 3 days starting on the first day of the month”.  
    Example use: \* 15/30 \* \* \* \* \* – will fire the job every second, every 15<sup>th</sup> and 45<sup>th</sup> minute in the hour, every hour, every day, every month, every day-of-week, every year.  
-   (“last”) – is contextual to each of the two fields in which it is allowed. With day-of-month, "L" means “the last day of the month”: so its 31<sup>st</sup> for January, 28<sup>th</sup> for February (on non-leap years). With the day-of-week field by itself, it simply means the 7<sup>th</sup> day, which is “SAT”.  
    **Note:** If used in the day-of-week field after another value, it means “the last xxx day of the month” – for example “6L” means “the last Friday of the month”. You can also specify an offset from the last day of the month, such as “L-3” which would mean the third-to-last day of the calendar month. Do not specify lists, or ranges of values when using the ‘L’ option.  
    Example use: \* \* \* L \* \* \* – will fire the job every second, every minute, every hour, every day, last day of every month, every month, every day-of-week, every year.  
-   (“weekday”) – specifies the weekday (any day, Monday to Friday) that is nearest to the given day. For example, “8W” for the day-of-month field, means: “the nearest weekday to the 8<sup>th</sup> of the month”. If the 8<sup>th</sup> is on Saturday, then Friday the 7<sup>th</sup> is closest. If the 8<sup>th</sup> happens to be a Sunday, the trigger will fire on Monday the 9<sup>th</sup> as it is closer to Sunday.  
    **Note:** If you specify “1W” as the value for day-of-month, and the 1<sup>st</sup> happens to be a Saturday, the trigger will fire on Monday the 3<sup>rd</sup>, and not Friday, as it is in fact the last day of the previous month. Do not specify lists, or ranges of values when using the ‘W’ option.  
    Example use: \* \* \* 10w \* \* \* – will fire the job every second, every minute, every hour, every 10<sup>th</sup> day of month (or closest weekday if 10<sup>th</sup> is a weekend day), every month, any day-of-week (that matches the other criteria), every year.  
-   – specifies “the n<sup>th</sup>” XXX day of the month but is used in context with the respective values. For example, “6#3” in the day-of-week field means “the third Friday of the month” (day 6 = Friday and “#3” = the 3<sup>rd</sup> one in the month). Other examples: “2#1” = the first Monday of the month and “4#5” = the fifth Wednesday of the month.  
    **Note:** If you specify “#5” and there is not 5 of the given day-of-week in the month, then no firing will occur that month.  
    Example use: \* \* \* \* \* 1#3 \* – will fire the job every second, every minute, every hour, any day of the month, every month, any day-of-week, every third Sunday of the month, every year.  

 
