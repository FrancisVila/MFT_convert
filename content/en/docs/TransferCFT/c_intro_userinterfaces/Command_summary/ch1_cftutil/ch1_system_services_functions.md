{
    "title": "System services functions",
    "linkTitle": "System services functions",
    "weight": "240"
}System services functions include:

-   \_Date: Returns the current date.
-   \_Time: Returns the current time.
-   \_lTime: Returns the current time as along integer.
-   \_DatTim: Returns the date and the current time.
-   \_SmSleep: Standby current process
-   \_Job: Returns the name of current process
-   \_User: Returns the user name.
-   \_DtSplit: Breaks down a timestamp to a date and a time.
-   \_DtDiff: Calculates the difference in hundredths of a second between two date/times.
-   \_DtAdd: Adds seconds to a date/time.

## Using the system services functions

### Function \_DATE

#### Syntax

The \_DATE function returns the current system date.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>_Date PARM = VDATE,</p>
            <p>      RC = lrc</p>
         </td>
      </tr>
   </tbody>
</table>

#### Values

-   VDATE: Name of a variable of type CHAR, minimum length 8, which receives in return the current system date. Enter the value in upper case.
-   lrc: Name of a long integer variable that receives in return a code execution.

#### Features

The date is expressed in the form YYYYMMDD, where YYYY represents the year, MM is the month and DD is the day of the month. For example, 19910101 represents January 1, 1991.

A positive value of the runtime code expresses the number of days since the beginning of the Christian era. A negative value reflects a problem of execution.

#### Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CHAR	name=DATE,size=8</p>
            <p>LONG	name=RCL</p>
            <p>_Date	parm=DATE=,rc=RCL</p>
            <p>PRINT	msg='Today's date is %DATE%'</p>
            <p>PRINT 	msg='The number of days is: %RCL%'</p>
         </td>
      </tr>
   </tbody>
</table>

### Function \_Time

#### Syntax

The \_Time function returns the current system time.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>_Time	PARM	= VTIME,</p>
            <p>      RC	= lrc</p>
         </td>
      </tr>
   </tbody>
</table>

#### Values

-   VTIME: The name of a CHAR variable, minimum length 8, which receives in return the current system time. Enter the value in upper case.
-   lrc: The name of a long integer variable that receives return code execution.

#### Features

The time is expressed as HHMMSSCC, where HH represents the hours, MM minutes, SS seconds, and CC is hundredths of a second. For example, 13105933 means 13 hours 10 minutes 59 seconds and 33 hundredths.

A positive value of the runtime code expresses the number of hundredths of seconds since the beginning of the day. A negative value reflects a problem in the \_Time function execution.

#### Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CHAR name = TIME, size = 8</p>
            <p>LONG name = RCL</p>
            <p>_time Parm = TIME = rc = RCL</p>
            <p>PRINT msg = 'The current time is% TIME%'</p>
            <p>PRINT msg = 'Number of hundredths elapsed:%% RCL</p>
         </td>
      </tr>
   </tbody>
</table>

### Function \_DatTim

#### Syntax

The \_DatTim function returns the current system date and current.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>_DatTim PARM = VDATTIM,</p>
            <p>        RC = lrc</p>
         </td>
      </tr>
   </tbody>
</table>

#### Values

-   VDATTIM: The name of the CHAR variable, minimum length 16, which receives the date and return the current system time. Enter the value in upper case.
-   lrc: Name of a long integer variable that receives return code execution.

#### Features

The result of the function is the concatenation of the date and time (YYYYMMDDHHMMSS).

A zero value indicates that the runtime code execution \_DatTim function correctly. A negative value reflects a problem.

#### Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CHAR	name = DATETIME, size = 16</p>
            <p>LONG	name = RCL</p>
            <p>_DatTim	parm = DATETIME, rc = RCL</p>
            <p>PRINT	msg = 'The current time is %DATETIME[8]%'</p>
         </td>
      </tr>
   </tbody>
</table>

### Function \_DtSplit

#### Syntax

The \_DtSplit function breaks a datetime string into an YYYYMMDDHHMMSS date and hour chain.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>. _DtSplit DATIME = date_time,</p>
            <p>           DATE = date,</p>
            <p>           TIME = time</p>
         </td>
      </tr>
   </tbody>
</table>

#### Parameters

-   Date\_time: The name of the CHAR variable, having a minimum length of 16, which contains a date-time value that is the concatenation of a date and time format YYYYMMDDHHMMSS.
-   Date: The name of the CHAR variable, having a length of 8, that returns the date.
-   Time: The name of the CHAR variable, having a length of 8, that receives an hour.

#### Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CHAR	name = DTSTART, size = 16</p>
            <p>CHAR	name = DATE_START, size = 8</p>
            <p>CHAR	name = TIME_START,size = 8</p>
            <p>_DTSPLIT	DATIME = DTSTART, DATE = DATE_START, TIME = TIME_START</p>
            <p>PRINT	msg = 'The date is %DATE_START%'</p>
            <p>PRINT	msg = 'The time is %TIME_START%'</p>
         </td>
      </tr>
   </tbody>
</table>

### Function \_DtMerge

#### Syntax

The \_DtMerge function builds a date-time string YYYYMMDDHHMMSS from a date chain and an hour chain.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>_DtMerge DATIME = date_time,</p>
            <p>           DATE = date,</p>
            <p>           TIME = time</p>
         </td>
      </tr>
   </tbody>
</table>

#### Values

-   Date\_time: The name of a the CHAR variable, minimum length 16, which will be stored in the result of the concatenation of the variable date and time format variable YYYYMMDDHHMMSS.
-   Date: The CHAR variable, length 8, that contains a date in YYYYMMDD format.
-   Time: The CHAR variable, having a length of 8, that contains a time format HHMMSSCC.

#### Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CHAR		name = DTDEBUT, size = 16
</p>
            <p>CHAR		name = DATE, size = 8, init = 19930101
</p>
            <p>CHAR		name = HOUR,size = 8, init = 12000000
</p>
            <p>_DTMERGE	DATIME = DTDEBUT, DATE = DATE_DEBUT, HOUR = HOUR_START     </p>
            <p>PRINT		msg = 'The date is %DTDEBUT%'
</p>
         </td>
      </tr>
   </tbody>
</table>

### Function \_DtAdd

#### Syntax

The \_DtAdd function calculates a new date-time string by adding a date-time number one second.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>_DtAdd FROMDT = date_time_src,</p>
            <p>TODT = date_time_dest,</p>
            <p>SEC = second</p>
         </td>
      </tr>
   </tbody>
</table>

#### Values

-   Date\_hour\_src: The name of a CHAR type variable having a minimum length of 16, which contains a date-time value that is a concatenation of a date and time format: YYYYMMDDHHMMSS.
-   Date\_hour\_dest: name of a variable of type CHAR, minimum length 16, which will be stored in the new date-time destination.
-   Second: name of a variable of type LONG which contains the number of seconds to add to the date-time source.

#### Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CHAR	name = DT_DEBUT, size = 16
</p>
            <p>LONG	name = DUREE
</p>
            <p>CHAR	name = DT_FIN, size = 16
</p>
            <p>_DTADD	FROMDT = DT_DEBUT, TODT = DT_FIN,SEC = DUREE</p>
            <p>
PRINT	msg = 'La date-heure de début est %DT_DEBUT%'</p>
            <p>
PRINT	msg = 'La date-heure de fin est %DT_FIN%'
</p>
         </td>
      </tr>
   </tbody>
</table>

### Function \_DtDiff

#### Syntax

The \_DtDiff function calculates the difference in hundredths of a second between two date/times.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>_DtDiff FROMDT = date_time1,</p>
            <p>TODT = date_time2,</p>
            <p>SEC = hundredth_of_seconds</p>
         </td>
      </tr>
   </tbody>
</table>

#### Values

-   date\_time1: name of a variable of type CHAR, minimum length 16, which contains a date-time value that is the concatenation of a date and time format YYYYMMDDHHMMSS.
-   date\_time2: name of a variable of type CHAR, minimum length 16, which contains a date-time value that is the concatenation of a date and time format YYYYMMDDHHMMSS.
-   hundredth\_of\_seconds: name of a variable of type LONG which will be stored in the difference-date-time1 date\_heure2. This difference is calculated in hundredth of seconds.

#### Examples

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CHAR	name = DT_START, size = 16
</p>
            <p>CHAR	name = DT_END, size = 16
</p>
            <p>LONG	name = DURATION
</p>
            <p>_DTDIFF	FROMDT = DT_END, TODT = DT_START, SEC = DURATION
</p>
            <p>PRINT	msg = 'The length of the session is %duration% seconds'
</p>
         </td>
      </tr>
   </tbody>
</table>

### Function \_User

#### Syntax

The \_user function returns the name of current user.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The PARM parameter must be entered in upper case.         </td>
      </tr>
</table>

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>PARM = _user VUSER,</p>
            <p>RC = lrc</p>
         </td>
      </tr>
   </tbody>
</table>

#### Values

-   VUSER: name of a variable of type CHAR, minimum length 15, which receives in return the current user name. Enter the value in upper case.
-   lrc: name of a long integer variable that receives return code execution.

#### Features

A value of zero means the runtime code execution \_user function correctly. A negative value indicates a problem.

#### Examples

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CHAR	name=USERNAME,size=16
</p>
            <p>LONG	name=RCL
</p>
            <p>_User	parm=USERNAME,rc=RCL
</p>
            <p>PRINT	 msg='The current user is %USERNAME%'
</p>
         </td>
      </tr>
   </tbody>
</table>

### Function \_Job

#### Syntax

The \_Job function returns the name of the current process with the operating system.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The PARM parameter must be entered in upper case.         </td>
      </tr>
</table>

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>_Job PARM = VJOB,</p>
            <p>RC = lrc</p>
         </td>
      </tr>
   </tbody>
</table>

#### Values

-   VJOB: The name of a CHAR variable, which receives the process name. There is a minimum length of 15. Enter the value in upper case.
-   lrc: The name of a long integer variable that receives the return code execution.

#### Features

A value of zero means the runtime code execution \_Job function correctly. A negative value reflects a problem.

#### Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CHAR	JOBNAME,size=16
</p>
            <p>LONG	name=RCL
</p>
            <p>_Job	parm=JOBNAME=,rc=RCL
</p>
            <p>PRINT	 msg='Processus courant %JOBNAME%'
</p>
         </td>
      </tr>
   </tbody>
</table>

### Function \_SmSleep

#### Syntax

The \_SmSleep function puts the current process in standby.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>_DatTim PARM = vsleep,</p>
            <p>RC = lrc</p>
         </td>
      </tr>
   </tbody>
</table>

#### Values

-   vsleep: The explicit standby time value.
-   lrc: The name of a long integer variable that receives return code execution.

#### Features

The duration of the standby is expressed in seconds.

A zero value indicates that the runtime code execution \_SmSleep functions correctly. A negative value signals an issue.

#### Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>LONG	name=LSLEEP,INIT=200
</p>
            <p>LONG	name=RCL
</p>
            <p>_SmSleep	parm=%LSLEEP%,rc=RCL	/* Standby 2 seconds */
</p>
         </td>
      </tr>
   </tbody>
</table>
