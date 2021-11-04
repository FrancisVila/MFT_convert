{
    "title": "Command syntax for Scheduling Event Models",
    "linkTitle": "Command syntax for Scheduling Event Models",
    "weight": "210"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Events

[Introduction](#intro)

[Elements of the TEM: Descriptors and calendars](#Elements)

[Assembling the TEM](#Assembling_TEMs)

<span id="intro"></span>

## Introduction

When you create or update a Scheduling-type Rule Table using command lines, use the <span style="font-style: italic;">Temporal Event Model (TEM) syntax</span> to set a value for the <span class="code">temporal\_event\_model (-tem)</span> parameter. TEM enables you to describe one or more instances in time.

<span id="Elements"></span>

## Elements of the TEM: Descriptors and calendars

A TEM consists of one or more calendars that are made up of descriptors. Descriptors specify a date or time:

-   [Simple date descriptor](#Simple_date_desc)
-   [Complex date descriptor](#Complex_date_desc)
-   [Simple time descriptor](#Simple_time_desc)
-   [Complex time descriptor](#Complex_time_desc)

You combine descriptors to create calendars and you combine [calendars](#Calendar) to create TEMs.

All the examples provided in this topic consist of a single line. In most instances you can force line breaks, for example to facilitate error searches.

### Complete syntax

The complete syntax for a TEM object is a date descriptor followed by a time descriptor:

**datedescriptor** `timedescriptor`

> **Note:**
>
> omitting the time descriptor may (in some cases) lead to error messages

The rest of this topic describes different forms of date and time descriptors.

<span id="Simple_date_desc"></span>

### Simple date descriptor

The simple date descriptor enables you to describe a day or set of days. It comprises four fields enclosed between brackets, the fields separated by semicolons.

To apply a time offset, you add characters after the closing brackets. For more details, refer to [Time offset](#Time_offset).

Syntax:<span class="code" style="font-weight: bold;">\[daysOfWeek;daysOfMonth;months;year\]</span>

> **Note:**
>
> On UNIX systems, semicolons must be escaped, syntax becomes:\[daysOfWeek\\;daysOfMonth\\;months\\;year\]

where:

-   <span class="code" style="font-weight: bold;">daysOfWeek</span> = a number (or numbers) representing one or more weekdays as follows:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>1 = Monday</p>         </td>
         <td><p>5 = Friday</p>         </td>
      </tr>
      <tr>
         <td><p>2 = Tuesday</p>         </td>
         <td><p>6 = Saturday</p>         </td>
      </tr>
      <tr>
         <td><p>3 = Wednesday</p>         </td>
         <td><p>7 = Sunday</p>         </td>
      </tr>
      <tr>
         <td><p>4 = Thursday</p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

Enter single days as a single integer. For example, for Saturday enter: 6

Enter intervals of days as integers separated by hyphens. For example, for Monday to Wednesday enter: 1-3

To enter all days of the week, enter: \*

To enter a periodic interval enter the period length after the slash symbol /.  
Examples:  
<span class="code">1-6/2</span> = every second day between the Monday and the Saturday beginning on Monday  
<span class="code">\*/3</span> = every 3rd day of the week beginning on Monday  

  

-   <span class="code" style="font-weight: bold;">daysOfMonth</span> = a number (or numbers) between 1 and 31 representing a day or days of the month.

Enter single dates as a single integer. For example, for the 5th day of the month enter: 5

Enter intervals of consecutive dates as two integers separated by hyphens. For example, for the 11th to the 15th enter: 11-15

To enter all dates of the category, enter: \*

To enter a periodic interval enter the period length after the slash symbol /.  
Examples:  
<span class="code">1-6/2</span> = every second date between the 1st and the 6th beginning on the 1st  
<span class="code">\*/3</span> = every 3rd date of the month beginning on the 1st  

  

-   <span class="code" style="font-weight: bold;">months</span> = a number (or numbers) representing a month (or months) as follows:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>1 = January</p>         </td>
         <td><p>7 = July</p>         </td>
      </tr>
      <tr>
         <td><p>2 = February</p>         </td>
         <td><p>8 = August</p>         </td>
      </tr>
      <tr>
         <td><p>3 = March</p>         </td>
         <td><p>9 = September</p>         </td>
      </tr>
      <tr>
         <td><p>4 = April</p>         </td>
         <td><p>10 = October</p>         </td>
      </tr>
      <tr>
         <td><p>5 = May</p>         </td>
         <td><p>11 = November</p>         </td>
      </tr>
      <tr>
         <td><p>6 = June</p>         </td>
         <td><p>12 = December</p>         </td>
      </tr>
   </tbody>
</table>

Enter single months as a single integer. For example, for March enter: 3

Enter intervals of consecutive months as two integers separated by hyphens. For example, for September to December: 9-12

To enter all months of the year, enter: \*

To enter a periodic interval enter the period length after the slash symbol /.  
Examples:  
<span class="code">1-6/2</span> = every second month between January and June beginning with January  
<span class="code">\*/3</span> = every 3rd month of the period beginning with January  

  

-   <span class="code" style="font-weight: bold;">year</span> = one or more years

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>Use the format...</p>         </td>
         <td><p>To indicate...</p>         </td>
         <td><p>Example</p>         </td>
      </tr>
      <tr>
         <td><p>yyyy</p>         </td>
         <td><p>A single year</p>         </td>
         <td><p>2009</p>         </td>
      </tr>
      <tr>
         <td><p>yyyy-yyyy</p>         </td>
         <td><p>An interval of consecutive years</p>         </td>
         <td><p>2000-2009</p>         </td>
      </tr>
      <tr>
         <td><p>*</p>         </td>
         <td><p>All years</p>         </td>
         <td><p>*</p>         </td>
      </tr>
      <tr>
         <td><p>&lt;yyyy</p>         </td>
         <td><p>Before the given year</p>         </td>
         <td><p>&lt;2009</p>         </td>
      </tr>
      <tr>
         <td><p>&gt;yyyy</p>         </td>
         <td><p>After the given year</p>         </td>
         <td><p>&gt;2009</p>         </td>
      </tr>
   </tbody>
</table>

To indicate the relation of a given year to a leap year, follow the year with the upright slash symbol (|) followed by a whole number (expressed in base 10) representing a binary four bit mask.

When the bit equals 1, the corresponding years are selected, as follows:

-   bit 1 = leap year
-   bit 2 = leap year +1 year
-   bit 3 = leap year +2 years
-   bit 4 = leap year +3 years

To calculate the bit mask from binary to base 10:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Binary</p>         </td>
         <td><p>Equivalent base 10</p>         </td>
      </tr>
      <tr>
         <td><p>0001</p>         </td>
         <td><p>1</p>         </td>
      </tr>
      <tr>
         <td><p>0010</p>         </td>
         <td><p>2</p>         </td>
      </tr>
      <tr>
         <td><p>0011</p>         </td>
         <td><p>3</p>         </td>
      </tr>
      <tr>
         <td><p>0100</p>         </td>
         <td><p>4</p>         </td>
      </tr>
      <tr>
         <td><p>0101</p>         </td>
         <td><p>5</p>         </td>
      </tr>
      <tr>
         <td><p>0110</p>         </td>
         <td><p>6</p>         </td>
      </tr>
      <tr>
         <td><p>0111</p>         </td>
         <td><p>7</p>         </td>
      </tr>
      <tr>
         <td><p>1000</p>         </td>
         <td><p>8</p>         </td>
      </tr>
      <tr>
         <td><p>1001</p>         </td>
         <td><p>9</p>         </td>
      </tr>
      <tr>
         <td><p>1010</p>         </td>
         <td><p>10</p>         </td>
      </tr>
      <tr>
         <td><p>1010</p>         </td>
         <td><p>11</p>         </td>
      </tr>
      <tr>
         <td><p>1011</p>         </td>
         <td><p>12</p>         </td>
      </tr>
      <tr>
         <td><p>1100</p>         </td>
         <td><p>12</p>         </td>
      </tr>
      <tr>
         <td><p>1101</p>         </td>
         <td><p>13</p>         </td>
      </tr>
      <tr>
         <td><p>1110</p>         </td>
         <td><p>14</p>         </td>
      </tr>
      <tr>
         <td><p>1111</p>         </td>
         <td><p>15</p>         </td>
      </tr>
   </tbody>
</table>

Example 1

<span class="code" style="font-weight: bold;">2006-2030|8</span> = <span style="font-style: italic;">all leap years between 2006 and 2030</span>

Explanation: 8 to the base 10 is expressed as <span style="font-style: italic;">1000</span> in binary. The first bit (reading left to right) of <span style="font-weight: bold;">1</span>000 is set to the value <span style="font-style: italic;">1</span>, so all leap years are selected.

Example 2

<span class="code" style="font-weight: bold;">2007-2025|9</span> = <span style="font-style: italic;">all leap years and all years preceding leap years between 2007 and 2025.</span>

Explanation: 9 to the base 10 is expressed as 1001 in binary. The first bit and the fourth bit (reading left to right) of <span style="font-weight: bold;">1</span>00<span style="font-weight: bold;">1</span> are set to the value <span style="font-style: italic;">1</span>, so all leap years and all leap years +3 are selected.

<span id="Time_offset"></span>

#### Time offset

You can offset the time expressed within the brackets of a TEM expression by a number of days.

-   To offset the expression later in time by <span style="font-style: italic;font-weight: bold;">d</span> number of days, use the syntax:

\[expression\]&gt;&gt;d

-   To offset the expression earlier in time by <span style="font-style: italic;font-weight: bold;">d</span> number of days, use the syntax:

\[expression\]&lt;&lt;d

Example:

\[\*;1-20/4;10-12,2;&lt;2010|12\]&lt;&lt;1

indicates the day before the days described by the expression inside the brackets.

#### Commented examples

A date descriptor expression describes all of the dates that satisfy all of the elements contained in the expression. The following examples illustrate how to apply the syntax.

Example 1:

<img src="/Images/Gateway/TEMexample.gif" width="435" height="105" />

Example 2:

<img src="/Images/Gateway/TEMexample2.gif" width="422" height="105" />

<span id="Complex_date_desc"></span>

### Complex date descriptor

You can use the following operators to link two or more simple date descriptors into a complex date descriptor.

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Operator</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p>+</p>         </td>
         <td><p>add</p>         </td>
      </tr>
      <tr>
         <td><p>-</p>         </td>
         <td><p>remove</p>         </td>
      </tr>
      <tr>
         <td><p>^</p>         </td>
         <td><p>keep only</p>         </td>
      </tr>
      <tr>
         <td><p>&amp;</p>         </td>
         <td><p>and</p>         </td>
      </tr>
   </tbody>
</table>

#### Commented examples

Example 1:

<img src="/Images/Gateway/TEMexample3.gif" width="435" height="111" />

Example 2:

<img src="/Images/Gateway/TEMexample4.gif" width="476" height="111" />

<span id="Simple_time_desc"></span>

### Simple time descriptor

The simple time descriptor enables you to describe a time of day or set of times of days. It comprises two fields separated by the letter <span style="font-weight: bold;">H</span> in the format:

HoursHMinutes

#### Hour and Minute field syntax

Hour and minutes fields obey the same syntactic rules. To complete the fields you can enter:

-   A single hour or minute as a single integer. For example, for 3 a.m. enter: 3
-   Intervals of consecutive hours or minutes as two integers separated by hyphens. For example, for 5 a.m. to 7 a.m. enter: 5-7
-   All times of a category. Enter: \*
-   A periodic interval. Enter the period length after the slash symbol /.  
    Examples:  
    <span class="code">1-6/2</span> = hour or minute 1, 3, 5  
    <span class="code">\*/3</span> = in the hour field indicates the hours 0, 3, 6, 9, 12, 15, 18, 21  

<span id="Complex_time_desc"></span>

### Complex time descriptor

You can link two or more simple time descriptors into a complex date descriptor. To link simple time descriptors separate them with semicolons.

#### Example

15H12 ; 12-16H30

indicates 15:12 and 12:30, 13:30, 14:30, 15:30, 16:30.

<span id="Calendar"></span>

### Calendar

A calendar is an association of a complex date descriptor and a complex time descriptor. You can create any logically valid combination of elements.

#### Example 1

\[\*;\*;\*;\*\]16H15

indicates every day at 16:15.

#### Example 2

\[1;\*;\*;\*\]-\[\*;\*;10;\*\] 16H30,50

indicates every Monday except in October at 16:30 and 16:50.

<span id="Assembling_TEMs"></span>

## Assembling the TEM

A TEM is a calendar or a combination of calendars. To combine calendars, create consecutive chains of calendar descriptors.

#### Example

\[\*;\*;\*;\*\]16H15 \[1;\*;\*;\*\]-\[\*;\*;10;\*\] 16H30,50

indicates every day at 16:15, and every Monday with the exception of Mondays in October at 16:30 and 16:50.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
