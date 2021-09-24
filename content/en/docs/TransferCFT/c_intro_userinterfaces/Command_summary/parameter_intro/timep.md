{
    "title": "timep",
    "linkTitle": "timep",
    "weight": "3530"
}### <span id="timep"></span>timep

#### CFTCAT

**TIMEP = {<u>23595999</u> | HHMMSSCC}**

User-defined daily purge time.

The user can program an automatic, cyclic catalog purge.  
The default purge time is midnight.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can completely deactivate purging by defining<br/>TIMEP = 00000000. Use t<i>his option with caution</i> as no automatic purging 
 is performed (at a selected time or at midnight).         </td>
      </tr>
</table>

#### PURGE

**\[TIMEP = {<u>23595999</u> | HHMMSSCC}**

User-defined purge time.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can deactivate the next purge function by setting TIMEP = 00000000. This operation should be used with care, 
 because of the risks of catalog overloading -with a loss of performance, 
 and risk of overflow. If the next purge is part of a cycle, see the CFTCAT TIMEP parameter, 
 the whole cycle is deleted, and not just the next occurrence of this cycle.         </td>
      </tr>
</table>

 

[Return to Command index](../../)
