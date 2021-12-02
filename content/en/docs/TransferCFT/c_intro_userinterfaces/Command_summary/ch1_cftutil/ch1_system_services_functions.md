{
    "title": "System services functions",
    "linkTitle": "System services functions",
    "weight": "220"
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

#### Values

-   VDATE: Name of a variable of type CHAR, minimum length 8, which receives in return the current system date. Enter the value in upper case.
-   lrc: Name of a long integer variable that receives in return a code execution.

#### Features

The date is expressed in the form YYYYMMDD, where YYYY represents the year, MM is the month and DD is the day of the month. For example, 19910101 represents January 1, 1991.

A positive value of the runtime code expresses the number of days since the beginning of the Christian era. A negative value reflects a problem of execution.

#### Example

### Function \_Time

#### Syntax

The \_Time function returns the current system time.

#### Values

-   VTIME: The name of a CHAR variable, minimum length 8, which receives in return the current system time. Enter the value in upper case.
-   lrc: The name of a long integer variable that receives return code execution.

#### Features

The time is expressed as HHMMSSCC, where HH represents the hours, MM minutes, SS seconds, and CC is hundredths of a second. For example, 13105933 means 13 hours 10 minutes 59 seconds and 33 hundredths.

A positive value of the runtime code expresses the number of hundredths of seconds since the beginning of the day. A negative value reflects a problem in the \_Time function execution.

#### Example

### Function \_DatTim

#### Syntax

The \_DatTim function returns the current system date and current.

#### Values

-   VDATTIM: The name of the CHAR variable, minimum length 16, which receives the date and return the current system time. Enter the value in upper case.
-   lrc: Name of a long integer variable that receives return code execution.

#### Features

The result of the function is the concatenation of the date and time (YYYYMMDDHHMMSS).

A zero value indicates that the runtime code execution \_DatTim function correctly. A negative value reflects a problem.

#### Example

### Function \_DtSplit

#### Syntax

The \_DtSplit function breaks a datetime string into an YYYYMMDDHHMMSS date and hour chain.

#### Parameters

-   Date\_time: The name of the CHAR variable, having a minimum length of 16, which contains a date-time value that is the concatenation of a date and time format YYYYMMDDHHMMSS.
-   Date: The name of the CHAR variable, having a length of 8, that returns the date.
-   Time: The name of the CHAR variable, having a length of 8, that receives an hour.

#### Example

### Function \_DtMerge

#### Syntax

The \_DtMerge function builds a date-time string YYYYMMDDHHMMSS from a date chain and an hour chain.

#### Values

-   Date\_time: The name of a the CHAR variable, minimum length 16, which will be stored in the result of the concatenation of the variable date and time format variable YYYYMMDDHHMMSS.
-   Date: The CHAR variable, length 8, that contains a date in YYYYMMDD format.
-   Time: The CHAR variable, having a length of 8, that contains a time format HHMMSSCC.

#### Example

### Function \_DtAdd

#### Syntax

The \_DtAdd function calculates a new date-time string by adding a date-time number one second.

#### Values

-   Date\_hour\_src: The name of a CHAR type variable having a minimum length of 16, which contains a date-time value that is a concatenation of a date and time format: YYYYMMDDHHMMSS.
-   Date\_hour\_dest: name of a variable of type CHAR, minimum length 16, which will be stored in the new date-time destination.
-   Second: name of a variable of type LONG which contains the number of seconds to add to the date-time source.

#### Example

### Function \_DtDiff

#### Syntax

The \_DtDiff function calculates the difference in hundredths of a second between two date/times.

#### Values

-   date\_time1: name of a variable of type CHAR, minimum length 16, which contains a date-time value that is the concatenation of a date and time format YYYYMMDDHHMMSS.
-   date\_time2: name of a variable of type CHAR, minimum length 16, which contains a date-time value that is the concatenation of a date and time format YYYYMMDDHHMMSS.
-   hundredth\_of\_seconds: name of a variable of type LONG which will be stored in the difference-date-time1 date\_heure2. This difference is calculated in hundredth of seconds.

#### Examples

### Function \_User

#### Syntax

The \_user function returns the name of current user.

> **Note:**
>
> The PARM parameter must be entered in upper case.

#### Values

-   VUSER: name of a variable of type CHAR, minimum length 15, which receives in return the current user name. Enter the value in upper case.
-   lrc: name of a long integer variable that receives return code execution.

#### Features

A value of zero means the runtime code execution \_user function correctly. A negative value indicates a problem.

#### Examples

### Function \_Job

#### Syntax

The \_Job function returns the name of the current process with the operating system.

> **Note:**
>
> The PARM parameter must be entered in upper case.

#### Values

-   VJOB: The name of a CHAR variable, which receives the process name. There is a minimum length of 15. Enter the value in upper case.
-   lrc: The name of a long integer variable that receives the return code execution.

#### Features

A value of zero means the runtime code execution \_Job function correctly. A negative value reflects a problem.

#### Example

### Function \_SmSleep

#### Syntax

The \_SmSleep function puts the current process in standby.

#### Values

-   vsleep: The explicit standby time value.
-   lrc: The name of a long integer variable that receives return code execution.

#### Features

The duration of the standby is expressed in seconds.

A zero value indicates that the runtime code execution \_SmSleep functions correctly. A negative value signals an issue.

#### Example
