{
    "title": "maxtime",
    "linkTitle": "maxtime",
    "weight": "1970"
}### <span id="maxtime"></span>maxtime

#### <span id="maxtime_CFTRECV"></span>CFTRECV, CFTSEND, SEND, RECV

**\[MAXTIME = {<u>23595999</u> | *time*}\]**

Only taken into account in requester
mode

Transfer validity limit time for the final date (MAXDATE).

The value time may be expressed:

-   Explicitly
    (absolute time)
-   Or,
    in RECV or SEND commands, relative to the time the command is taken into
    account

In this case, the corresponding absolute time must
be less than 24 hours. The indicated value is expressed in minutes.

MAXTIME must not be equal to MINTIME except if MAXDATE is defined and
is not the current date.

#### START

**\[MAXTIME = {+n}\]**

Maxtime is used in the START command to indicate a relative transfer validity time limit. This means the time that the command is taken into account plus n minutes. The maxtime value is between 1 and the number of minutes in a day minus one, (60 x 24) – 1, and must be less than 24 hours.

Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>start part=part1,maxtime=+10         </td>
      </tr>
   </tbody>
</table>

Example

MAXTIME = +180 means that the maximum time limit for a transfer to be valid is the time from which the command is taken into account plus 180 minutes. The acceptance time for the transfer command must be less than 24 hours.

[Return to Command index](../../)

####  