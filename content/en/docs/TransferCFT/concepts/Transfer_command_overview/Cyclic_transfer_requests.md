{
    "title": "Cyclic  transfer requests",
    "linkTitle": "Cyclic transfer requests",
    "weight": "280"
}A cyclic transfer
request is a periodic, repeated transfer request. The period, the time
between 2 transfer activation cycles, is defined by the CYCLE and TCYCLE parameters.

-   CYCLE: Numeric value for TCYCLE.
-   TCYCLE: The type of period, expressed in minutes (MIN), days (DAY), or months (MONTH).

## Defining the cycle time frame

The time frame for a cyclic transfer request is defined by the MINDATE/MINTIME
and MAXDATE/MAXTIME parameters, and corresponds to the global time during
which the transfers are periodically repeated.

The time slot for activating each basic transfer is defined by the MINDATE/MINTIME
and CYCDATE/CYCTIME parameters, where:

-   CYCDATE: End date for activating
    a transfer in a cycle, where the value is recalculated for each new cycle.
-   CYCTIME: End time for activating a transfer in a cycle, where the value is recalculated for each new cycle.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The CYCDATE/CYCTIME is equivalent to the MAXDATE/MAXTIME for a request. If the request is not executed before the date/time, then the request is not executed (times out).         </td>
      </tr>
   </tbody>
</table>

The start time/date and cycle duration
values are expressed in the following equation:

`CYCLE * TCYCLE >= (CYCDATE,CYCTIME) - (MINDATE,MINTIME)`

**Example**

The example command creates a cyclic transfer request as shown below:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>SEND PART=PARIS, MINDATE=20150703, MINTIME=1000, MAXDATE=20151231, MAXTIME=1000, CYCLE=7, TCYCLE=DAY, CYCDATE=20150705, CYCTIME=1000         </td>
      </tr>
   </tbody>
</table>

-   The request start date and time is July 3, 2015 at 10:00 (MINDATE/MINTIME).
-   A period of inactivity begins on July 5, 2015 at 10:00 (CYCDATE/CYCTIME).
    -   A child transfer of the cyclic request who's execution begins during the period of activity will complete, even if that time extends into time timeout.
    -   Any child transfer of the generic request that is not executed before the timeout is lost.
-   The cycle duration is 7 days (CYCLE/TCYCLE), so activity restarts on July 10, 2015.
-   This pattern repeats itself until the defined end date and time (MAXDATE/MAXTIME).

![](/Images/TransferCFT/new_cyclic_example.png)

A cyclic transfer request results in the creation of a generic virtual
transfer entry for the actual transfers. This generic entry is maintained in the
transfer catalog and gives rise, for each new cycle, to a real transfer. The generic entry is purged at the end of the last
cycle, when MAXDATE is exceeded.

A generic entry is characterized by
one of the values indicated in the table below, for the DIAGP field, at
the time the catalog is queried (LISTCAT CONTENT=BRIEF).

**Generic entry values**

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>            <p>Diagp value </p></th>
         <th>            <p>Cycle </p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="24.312%">            <p>MIN CYC </p>         </td>
         <td data-valign="top" width="75.688%">            <p>Cycle expressed in minutes </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="24.312%">            <p>DAY CYC </p>         </td>
         <td data-valign="top" width="75.688%">            <p>Cycle expressed in days </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="24.312%">            <p>MON CYC </p>         </td>
         <td data-valign="top" width="75.688%">            <p>Cycle expressed in months </p>         </td>
      </tr>
   </tbody>
</table>

Use the CONTENT=FULL option to view all of the parameters for this cyclic
request.

See also, [CYCLE](../../c_intro_userinterfaces/command_summary/parameter_intro/cycle), [CYCTIME](../../c_intro_userinterfaces/command_summary/parameter_intro/cyctime), [CYCDATE](../../c_intro_userinterfaces/command_summary/parameter_intro/cycdate), [TCYCLE](../../c_intro_userinterfaces/command_summary/parameter_intro/tcycle).
