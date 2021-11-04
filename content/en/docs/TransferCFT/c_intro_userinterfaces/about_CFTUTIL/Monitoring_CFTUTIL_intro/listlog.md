{
    "title": "LISTLOG - List the log content ",
    "linkTitle": "LISTLOG - List log content",
    "weight": "340"
}This topic describes how to use the LISTLOG command to display the log content according to certain defined criteria, such as date or node. Additionally, you can filter the log depending on multiple criteria, or view a merged log for several nodes in cluster mode.

Command syntax: <span class="code">listlog &lt;filter list></span>

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Default         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>loglevel         </td>
         <td>I         </td>
         <td><p>Minimum severity level for the log lines to display.</p>
<ul>
<li>I: INFORMATION</li>
<li>E: ERROR</li>
<li>W: WARNING</li>
<li>F: FATAL</li>
</ul>         </td>
      </tr>
      <tr>
         <td>lines         </td>
         <td>-100         </td>
         <td><p>Defines the number of lines to display from all log files, both current and backup.</p>
<ul>
<li>A positive value displays the <em>x</em> oldest lines.</li>
<li>The value zero (0) displays all of the lines.</li>
<li>A negative value displays the <strong>x</strong> most recent lines.</li>
</ul>
<p>Enter zero (0), or a positive or negative value between 1 and 10,000.</p>         </td>
      </tr>
      <tr>
         <td>datemin         </td>
         <td>0         </td>
         <td><p>There are multiple formats to use to define the minimum date for log display.</p>
<ul>
<li>Use the format YYMMDD to display logs that happened on or after this date.</li>
<li>Use  a partial date for a more generic display. For example, <span class="code">1604 </span>displays the log since April 2016.</li>
<li>Use a negative value to display logs for x number of days prior to today. For example, entering -2 displays the log since the day before yesterday, and -0 displays today’s log.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>datetimemin</p>         </td>
         <td>0         </td>
         <td>Use to display logs that happened on or after this start date and time.         </td>
      </tr>
      <tr>
         <td><p>datetimemax</p>         </td>
         <td>99123123595999         </td>
         <td>Use to display logs that happened on or before this end date and time.         </td>
      </tr>
      <tr>
         <td>datemax         </td>
         <td>991231         </td>
         <td><p>There are multiple formats to use to define the maximum date for log display.</p>
<ul>
<li>Use to display logs that happened on or before this date. Use the format: YYMMDD</li>
<li>You can also enter a partial date. For example, <span class="code">16 </span>displays the log prior to 2016.</li>
<li>A negative value is interpreted as a number of days before today. For example, -1 displays the log till yesterday (included).</li>
</ul>         </td>
      </tr>
      <tr>
         <td>timemin         </td>
         <td>0         </td>
         <td><ul>
<li>Logs only happened at this time or after this time during the day. Use the format HHMMSSss.</li>
<li>A negative value is interpreted as a number of minutes before the current time. For example, -20 displays the log for the last 20 minutes.</li>
</ul>
<p><span style="color: #000000;">See also </span><a href="#Time" class="MCXref xref">Time log precision</a><span style="color: #000000;">.</span></p>         </td>
      </tr>
      <tr>
         <td>timemax         </td>
         <td>23595999         </td>
         <td><ul>
<li>Logs only happened at this time or before this time during the day. Use the format HHMMSSss.</li>
<li><span style="color: #000000;">A negative value is interpreted as a number of minutes before current time. For example , -20 displays the log with the last 20 minutes filtered out.</span></li>
</ul>
<p><span style="color: #000000;">See also </span><a href="#Time" class="MCXref xref">Time log precision</a><span style="color: #000000;">.</span></p>         </td>
      </tr>
      <tr>
         <td>pattern         </td>
         <td>          </td>
         <td>Only displays the log lines that match this specific pattern. Enter any pattern with a maximum of 63 characters.         </td>
      </tr>
      <tr>
         <td>displaynodeid         </td>
         <td>YES         </td>
         <td><p>Defines if the node ID displays at the beginning of each line in the log. Enter:</p>
<ul>
<li>YES: display</li>
<li>NO: does not display</li>
</ul>         </td>
      </tr>
      <tr>
         <td>node         </td>
         <td>-         </td>
         <td><p>Defines which nodes you want to display the log for. Specify the node by entering the node number :</p>
<ul>
<li>Empty: if you do not define this parameter LISTLOG displays all nodes</li>
<li>Enter the node number(s) and separate with a comma. Node numbers cannot be more than two digits. For example: 00, 01, 02</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

Example

To display the 10 most recent lines in the log:


    CFTUTIL listlog lines=-10

To list the log for nodes 0 through 3, use any one of the following formats:


    CFTUTIL listlog node='(0,1,2,3)'
    CFTUTIL listlog node='(00,01,02,03)'
    CFTUTIL listlog node='('0','1','2','3')'
    CFTUTIL listlog node='('00','01','02','03')'

To display the fatal errors since yesterday:


    CFTUTIL listlog loglevel=F, datemin=110807 or CFTUTIL listlog loglevel=F, datemin=-1

To display the errors that match the pattern \*TEST\*:


    CFTUTIL listlog loglevel=E, pattern="*TEST*"

Command parameter types



    COMMAND LISTLOG USAGE
    LOGLEVEL          D S 12     <I> 'FATAL','ERROR','WARNING','INFORMATION','F','E','W','I'
    LINES             N X 4      Number <-100> min=-10000 max=10000
    DATETIMEMIN       N N 14     Number <0> min=0 max=99123123595999
    DATETIMEMAX       N N 14     Number <99123123595999> min=0 max=99123123595999
    DATEMIN           N N 6      Number <0> min=-3660 max=991231
    DATEMAX           N N 6      Number <991231> min=-3660 max=991231
    TIMEMIN           N N 8      Number <0> min=-1440 max=23595999
    TIMEMAX           N N 8      Number <23595999> min=-1440 max=23595999
    PATTERN           s S 64     string max_length=63
    DISPLAYNODEID     S N 1      <YES> 'YES','NO'
    NODE              S L 2 *99  STRING LIST max_length=1 max_entries=99

<span id="Time"></span>

### Time log precision

By default, the data sent to Sentinel as the EventTime has the format HH:MM:SS. To add milliseconds to the format, HH:MM:SS.sss, set the Transfer CFT UCONF <span class="code">cft.cftlog.time\_precision</span> parameter, where:

-   1 (default): the time in CFTLOG displays in seconds
-   10: the time in CFTLOG displays in tenths of seconds
-   100: the time in CFTLOG displays in hundredths of seconds

If the<span class="code"> cft.cftlog.time\_precision</span> value is greater than 1, the Transfer CFT EventTime message sent to Sentinel has the HH:MM:SS.dh0 format.

**Example**



    uconfset id=cft.cftlog.time_precision, value=10
