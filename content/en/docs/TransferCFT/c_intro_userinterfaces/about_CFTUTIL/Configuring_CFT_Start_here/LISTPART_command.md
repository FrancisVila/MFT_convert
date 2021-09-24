{
    "title": "LISTPART - List partner details",
    "linkTitle": "LISTPART - List partner details",
    "weight": "510"
}# <span id="kanchor20"></span><span id="Listing_partners"></span>Listing partner details

This topic describes how to use the LISTPART command to view partner
characteristics.

Use this command to view the characteristics of partners
(general or network characteristics), according to the selection criteria
indicated in the command.

In the absence of a previous CONFIG TYPE = OUTPUT command,
the execution report is written on the standard output of the CFTUTIL
program.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Parameters</p>
</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">
         <td>
            <p><a href="../../../command_summary/parameter_intro/id">ID</a> </p>
         </td>
         <td width="59.777%">
            <p>Partner or partner list identifier.</p>
            <p>Used to select a single partner or a set of partners, using 
 the special wildcard character "<b>*</b>".</p>
            <p>Example:</p>
            <p>ID = PART1: for the partner PART1 only<br/>ID = IB*: for all the partners whose identifier begins with "IB"<br/>ID = *: for all the partners</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/type">TYPE</a>
</p>
         </td>
         <td colspan="1" rowspan="1" width="59.777%">
            <p>Defines the type of characteristics to be listed.</p>
            <p>TYPE can take the predefined values indicated in the Type 
 table. </p>
         </td>
      </tr>
   </tbody>
</table>

Example 1

To view all the contents of the records of the PARTNER
file:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>LISTPART TYPE = ALL         </td>
      </tr>
   </tbody>
</table>

Example 2

To view broadcasting lists:

<table cellspacing="0">
   <col/>
      <tr>
         <td>
            <p>LISTPART TYPE = DEST</p>
         </td>
      </tr>
</table>
